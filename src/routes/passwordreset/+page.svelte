<script lang="ts">
	import { goto } from '$app/navigation';
	import { ArrowLeft, ArrowUpRight } from '@lucide/svelte';

	function openResetPortal() {
		window.open('https://passwordreset.iiit.ac.in', '_blank', 'noopener,noreferrer');
	}
</script>

<svelte:head>
	<title>Password Reset | IIIT Hyderabad Intro to Portals Guide</title>
	<meta name="description" content="How to reset your LDAP password at IIIT Hyderabad through the password reset portal." />
</svelte:head>

<div class="detail-overlay" style="view-transition-name: card-passwordreset">
	<div class="detail-content">
		<button class="back-link" onclick={() => goto('/')} aria-label="Go back">
			<ArrowLeft size={16} /> Back
		</button>

		<h1>Reset Your Password</h1>
		<p class="subtitle">LDAP &amp; 802.1x password guide</p>

		<div class="section-divider"></div>

		<div class="info-box">
			<p>
				<strong>Security notice:</strong> Do not share your password with anyone. Use a strong,
				unique password that you don't use elsewhere.
			</p>
		</div>

		<div class="section-divider"></div>

		<h2>What You'll Find</h2>
		<p>
			When you visit the password reset portal and log in with CAS, you'll see two tabs:
		</p>

		<div class="domain-grid">
			<div class="domain-card">
				<h3>LDAP</h3>
				<p>Your main account, used for email, Moodle, IMS, library, and most campus services.</p>
			</div>
			<div class="domain-card">
				<h3>802.1x</h3>
				<p>Your network authentication, used for WiFi and wired Ethernet on campus.</p>
			</div>
		</div>

		<div class="info-box" style="border-color: #fde68a; background: #fffbeb;">
			<p>
				<strong>Important:</strong> 802.1x passwords are stored in plain text and can be viewed
				by portal maintainers. <strong>Never use your LDAP password for 802.1x</strong>, always
				choose something different.
			</p>
		</div>

		<div class="section-divider"></div>

		<h2>Step-by-Step Guide</h2>
		<p>You'll need to reset both passwords:</p>

		<ol class="step-list">
			<li class="step-item">
				<div class="step-title">Log in with CAS</div>
				<div class="step-desc">
					Open your browser and go to
					<a href="https://passwordreset.iiit.ac.in" target="_blank" rel="noopener noreferrer" class="inline-link">
						<code>passwordreset.iiit.ac.in</code>
						<ArrowUpRight size={14} />
					</a>.
					You'll be prompted to log in using CAS. Enter your temporary LDAP credentials.
				</div>
			</li>
			<li class="step-item">
				<div class="step-title">Reset LDAP Password</div>
				<div class="step-desc">
					The <strong>LDAP</strong> tab is selected by default. Enter your current password and then
					your new password. Make sure it's at least 8 characters with a mix of uppercase, lowercase,
					numbers, and special characters.
				</div>
			</li>
			<li class="step-item">
				<div class="step-title">You May Be Logged Out</div>
				<div class="step-desc">
					After resetting your LDAP password, the portal may log you out. That's normal, your session
					needs to refresh with the new credentials.
				</div>
			</li>
			<li class="step-item">
				<div class="step-title">Visit Again to Reset 802.1x</div>
				<div class="step-desc">
					Go back to
					<a href="https://passwordreset.iiit.ac.in" target="_blank" rel="noopener noreferrer" class="inline-link">
						<code>passwordreset.iiit.ac.in</code>
						<ArrowUpRight size={14} />
					</a>
					and log in again with your <strong>new</strong> LDAP password. This time, switch to the
					<strong>802.1x</strong> tab.
				</div>
			</li>
			<li class="step-item">
				<div class="step-title">Set Your 802.1x Password</div>
				<div class="step-desc">
					Enter your current LDAP password and a new password for 802.1x. This will be used to
					authenticate on campus WiFi and wired Ethernet connections.
				</div>
			</li>
			<li class="step-item">
				<div class="step-title">Set an Alternate Email</div>
				<div class="step-desc">
					In the page header, find the <strong>alternate email</strong> change option and set your
					personal email address. This is critical, if you ever forget your password, this is the
					<strong>only way</strong> to recover it.
				</div>
			</li>
		</ol>

		<div style="margin-top: 2rem; display: flex; flex-direction: column; align-items: flex-start;">
			<button class="cta-btn" onclick={openResetPortal}>
				Open Password Reset Portal
				<ArrowUpRight size={16} />
			</button>
			<p style="margin-top: 0.5rem; font-size: 0.8rem; color: #9ca3af;">
				Opens passwordreset.iiit.ac.in in a new tab
			</p>
		</div>
	</div>
</div>