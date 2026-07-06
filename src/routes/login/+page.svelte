<script lang="ts">
	import { goto } from '$app/navigation';
	import { ArrowLeft, ArrowUpRight } from '@lucide/svelte';
</script>

<svelte:head>
	<title>Central Login (CAS) | IIIT Hyderabad Intro to Portals Guide</title>
	<meta name="description" content="Central Login Service (CAS) at IIIT Hyderabad — single sign-on for all campus portals. Developer integration guide included." />
</svelte:head>

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
		<p>Head to <a href="https://self-help.iiit.ac.in/wiki/index.php/Scripting_Login_Through_CAS" target="_blank" rel="noopener noreferrer" class="inline-link">
			self-help.iiit.ac.in/wiki/index.php/Scripting_Login_Through_CAS<ArrowUpRight size={14} /></a> (needs Wifi/VPN to access) to find more information about 
			integrating CAS into your applications.</p>
	</div>
</div>