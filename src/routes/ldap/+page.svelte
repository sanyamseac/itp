<script lang="ts">
	import { goto } from '$app/navigation';
	import { ArrowLeft } from '@lucide/svelte';
</script>

<div class="detail-overlay" style="view-transition-name: card-ldap">
	<div class="detail-content">
		<button class="back-link" onclick={() => goto('/')} aria-label="Go back">
			<ArrowLeft size={16} /> Back
		</button>

		<h1>What is LDAP?</h1>
		<p class="subtitle">Your digital identity at IIIT</p>

		<div class="section-divider"></div>

		<p>
			<strong>LDAP</strong> (Lightweight Directory Access Protocol) is the central identity
			system at IIIT. Think of it as your digital identity, your LDAP username and password are
			used to log in to almost every portal and service at the institute.
		</p>

		<div class="info-box">
			<p>
				<strong>Why LDAP Matters?</strong> Your LDAP credentials are the root of everything at IIIT.
				From logging into campus computers to accessing WiFi, checking grades on the IMS, submitting
				assignments on Moodle, and accessing the digital library, it all starts with LDAP.
			</p>
		</div>

		<div class="section-divider"></div>

		<h2>Understanding Your Username</h2>
		<p>
			Your LDAP username is the part of your email address <strong>before</strong> the @ symbol.
		</p>

		<div class="username-visual">
			<span class="username-part">sanyam.gandhi</span>
			<span class="at-sign">@</span>
			<span class="domain-part">research.iiit.ac.in</span>
			<span class="username-label">Your LDAP username is <strong>sanyam.gandhi</strong></span>
		</div>

		<div class="section-divider"></div>

		<h2>Email Domain Breakdown</h2>
		<p>The domain after @ depends on your degree program:</p>

		<div class="domain-grid">
			<div class="domain-card">
				<h3>@students.iiit.ac.in</h3>
				<p>For B.Tech and M.Tech students</p>
			</div>
			<div class="domain-card">
				<h3>@research.iiit.ac.in</h3>
				<p>For Dual Degree, MS by Research, and PhD research scholars</p>
			</div>
		</div>

		<div class="info-box">
			<p>
				<strong>Next step:</strong> Once you know your LDAP username, head to the password reset
				portal to set up your permanent password. Details on next card.
			</p>
		</div>
	</div>
</div>