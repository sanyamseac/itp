<script lang="ts">
	import { goto } from '$app/navigation';
	import { ArrowLeft, ArrowUpRight } from '@lucide/svelte';

	const oauthCode = `redirect(302, \`https://login.iiit.ac.in/cas/login?service=\${service}\`)`;

	const loginCode = `const tgtResponse = await fetch(\`https://login.iiit.ac.in/cas/v1/tickets\`, {
\tmethod: 'POST',
\theaders: { 'Content-Type': 'application/x-www-form-urlencoded' },
\tbody: new URLSearchParams({ username, password }),
})

const tgtUrl = tgtResponse.headers.get('Location')

const stResponse = await fetch(tgtUrl, {
\tmethod: 'POST',
\theaders: { 'Content-Type': 'application/x-www-form-urlencoded' },
\tbody: new URLSearchParams({ service: event.url.origin }),
})
const serviceTicket = await stResponse.text()

const validationUrl = \`https://login.iiit.ac.in/cas/serviceValidate?service=\${event.url.origin}&ticket=\${serviceTicket}&format=JSON\`
const response = await fetch(validationUrl)
const json = await response.json()
const details = json.serviceResponse?.authenticationSuccess?.attributes

const name = details['Name'][0]
const email = details['E-Mail'][0]
`;

	const callbackCode = `const ticket = event.url.searchParams.get('ticket')

const validationUrl = \`https://login.iiit.ac.in/cas/serviceValidate?service=\${service}&ticket=\${ticket}&format=JSON\`
const response = await fetch(validationUrl)
const json = await response.json()
const details = json.serviceResponse?.authenticationSuccess?.attributes

const name = details['Name'][0]
const email = details['E-Mail'][0]
`;
</script>

<div class="detail-overlay" style="view-transition-name: card-login">
	<div class="detail-content">
		<button class="back-link" onclick={() => goto('/')} aria-label="Go back">
			<ArrowLeft size={16} /> Back
		</button>

		<h1>Central Login</h1>
		<p class="subtitle">Your gateway to IIIT portals</p>

		<div class="section-divider"></div>

		<h2>What is CAS?</h2>
		<p>
			IIIT uses <strong>Central Authentication Service (CAS)</strong> - a single sign-on system
			that lets you log in once and access most campus portals.
		</p>
		<p>
			Your CAS login is tied directly to your <strong>LDAP account</strong>.
		</p>

		<div class="info-box">
			<p>
				<strong>Login URL:</strong>
				<a href="https://login.iiit.ac.in" target="_blank" rel="noopener noreferrer" class="inline-link">
					<code>login.iiit.ac.in</code> <ArrowUpRight size={14} />
				</a><br />
				<strong>Credentials:</strong> Your LDAP username and password
			</p>
		</div>

		<div class="section-divider"></div>
        <div style="margin-top: 2rem;">
            <p>Not sure what you will do by directly visiting the CAS portal but below is the link:</p>
			<button class="cta-btn" onclick={() => window.open('https://login.iiit.ac.in', '_blank', 'noopener,noreferrer')}>
				Open CAS Portal
				<ArrowUpRight size={16} />
			</button>
		</div>

		<div class="section-divider"></div>

		<h2>Integrating CAS in Your Apps</h2>
		<p>
			If you're building a web app that needs IIIT login, you can use CAS directly.
			Local testing works without any permissions: just point your app to
			<a href="https://login.iiit.ac.in" target="_blank" rel="noopener noreferrer" class="inline-link">
				<code>login.iiit.ac.in</code> <ArrowUpRight size={14} />
			</a>.
			For production, you'll need to contact the <strong>IT office</strong> to whitelist
			your server URL.
		</p>
		<div class="info-box" style="background: #fef9c3; border-color: #facc15;">
			<p>
				<strong>Future reference:</strong> You don't need this right now, this is for
				when you've learned enough to build your own apps. Bookmark this page and come
				back later.
			</p>
		</div>

		<h3>1. Redirect users to CAS</h3>
		<p>Send users to the CAS login page with your service URL so they come back after authenticating:</p>
		<pre><code>{@html oauthCode}</code></pre>

		<h3>2. Handle the callback</h3>
        <p>After CAS redirects back to your app with a ticket, validate it:</p>
		<pre><code>{@html callbackCode}</code></pre>
		
        <h3>Alternative Way</h3>
		<p>Your app sends the username and password to CAS to get a ticket, then validates it. It prevents any redirection and is useful for API applications.</p>
		<pre><code>{@html loginCode}</code></pre>
	</div>
</div>