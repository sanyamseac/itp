<script lang="ts">
	import { goto } from '$app/navigation';
	import { ArrowLeft, ArrowUpRight } from '@lucide/svelte';
</script>

<div class="detail-overlay" style="view-transition-name: card-outlook">
	<div class="detail-content">
		<button class="back-link" onclick={() => goto('/')} aria-label="Go back">
			<ArrowLeft size={16} /> Back
		</button>

		<h1>Outlook &amp; Microsoft 365</h1>
		<p class="subtitle">Your campus email and more</p>

		<div class="section-divider"></div>

		<div class="info-box" style="border-color: #dc2626; background: #fef2f2;">
			<p>
				<strong>Sign in and check this regularly.</strong> All official communications
				from IIIT come to this email. Set it up on your phone asap and keep checking.
			</p>
		</div>

		<div class="info-box" style="border-color: #fca5a5; background: #fef2f2;">
			<p>
				<strong>Important:</strong> Do not set up your IIIT email as a Windows account
				or link it to your Windows login. Keep it only for <strong>Outlook</strong>,
				<strong>Office apps</strong>, <strong>Teams</strong>, and <strong>OneDrive</strong>.
			</p>
		</div>

		<h2>Your Email</h2>
		<p>
			Every IIIT student and researcher gets a Microsoft 365 email account. For example,
			<strong>sanyam.gandhi@research.iiit.ac.in</strong>. Your full email ID and LDAP
			password are your login credentials.
		</p>

		<div class="info-box">
			<p>
				<strong>Webmail shortcut:</strong>
				<a href="https://webmail.iiit.ac.in" target="_blank" rel="noopener noreferrer" class="inline-link">
					<code>webmail.iiit.ac.in</code> <ArrowUpRight size={14} />
				</a>: logs you in directly via CAS and opens your Outlook inbox.<br />
				<strong>Full portal:</strong>
				<a href="https://outlook.cloud.microsoft" target="_blank" rel="noopener noreferrer" class="inline-link">
					<code>outlook.cloud.microsoft</code> <ArrowUpRight size={14} />
				</a>
			</p>
		</div>

		<div class="section-divider"></div>

		<h2>What's Included?</h2>
		<p>
			Your M365 subscription gives you access to the student version of the full Microsoft suite:
		</p>

		<div class="domain-grid">
			<div class="domain-card">
				<h3>Outlook</h3>
				<p>Email, calendar, and email IDs of all members on campus</p>
			</div>
			<div class="domain-card">
				<h3>Teams</h3>
				<p>Most campus meetings, club meetings, and group collaboration happen here</p>
			</div>
			<div class="domain-card">
				<h3>OneDrive</h3>
				<p>Cloud storage - clubs and teams often use this to share files</p>
			</div>
            <div class="domain-card">
                <h3>Other M365 Apps</h3>
                <p>Additional productivity tools included with your M365 subscription</p>
            </div>
		</div>

		<div class="section-divider"></div>

		<div style="margin-top: 2rem;">
			<button class="cta-btn" onclick={() => window.open('https://webmail.iiit.ac.in', '_blank', 'noopener,noreferrer')}>
				Open Webmail
				<ArrowUpRight size={16} />
			</button>
		</div>
	</div>
</div>