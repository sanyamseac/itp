<script lang="ts">
	import { goto } from '$app/navigation';
	import { ArrowLeft } from '@lucide/svelte';

	let activeTab = $state<'ubuntu' | 'windows' | 'macos'>('ubuntu');
</script>

<div class="detail-overlay" style="view-transition-name: card-wifi">
	<div class="detail-content">
		<button class="back-link" onclick={() => goto('/')} aria-label="Go back">
			<ArrowLeft size={16} /> Back
		</button>

		<h1>Connect to WiFi</h1>
		<p class="subtitle">802.1x campus WiFi guide</p>

		<div class="section-divider"></div>

		<h2>Campus WiFi</h2>
		<p>
			IIIT uses 802.1x authentication for campus WiFi. Pick your operating system below
			for step-by-step instructions.
		</p>

		<div class="info-box">
			<p>
				<strong>SSID:</strong> <code>wifi@iiith</code><br />
				<strong>EAP method:</strong> PEAP (Protected EAP)<br />
				<strong>Phase 2 auth:</strong> MSCHAPv2<br />
				<strong>CA certificate:</strong> Trust on First Use (TOFU)
			</p>
		</div>

		<div class="section-divider"></div>

		<!-- ── OS Tabs ── -->
		<div class="tabs">
			<button
				class="tab-btn {activeTab === 'ubuntu' ? 'active' : ''}"
				onclick={() => activeTab = 'ubuntu'}
			>Ubuntu / Linux</button>
			<button
				class="tab-btn {activeTab === 'windows' ? 'active' : ''}"
				onclick={() => activeTab = 'windows'}
			>Windows</button>
			<button
				class="tab-btn {activeTab === 'macos' ? 'active' : ''}"
				onclick={() => activeTab = 'macos'}
			>macOS</button>
		</div>

		{#if activeTab === 'ubuntu'}
			<ol class="step-list">
				<li class="step-item">
					<div class="step-title">Open WiFi Settings</div>
					<div class="step-desc">
						Click the network icon in the top-right corner and select
						<strong>Advanced Options &gt; WiFi Settings</strong> (GNOME) or open your
						network manager directly.
					</div>
				</li>
				<li class="step-item">
					<div class="step-title">Select wifi@iiith</div>
					<div class="step-desc">
						Find <strong>wifi@iiith</strong> in the list of available networks and click
						<strong>Connect</strong> or <strong>Configure</strong>.
					</div>
				</li>
				<li class="step-item">
					<div class="step-title">Set Security to WPA2/WPA3 Enterprise</div>
					<div class="step-desc">
						Set <strong>WiFi security</strong> to <strong>WPA2/WPA3 Enterprise</strong>.
						Authentication: <strong>PEAP</strong>.
						Phase 2 auth: <strong>MSCHAPv2</strong>.
					</div>
				</li>
				<li class="step-item">
					<div class="step-title">Set CA Certificate</div>
					<div class="step-desc">
						Set <strong>CA certificate</strong> to <strong>Trust on First Use (TOFU)</strong>.
						If that option isn't available, select <strong>Don't validate</strong> or leave it
						blank — the network uses a RADIUS server.
					</div>
				</li>
				<li class="step-item">
					<div class="step-title">Enter Credentials &amp; Connect</div>
					<div class="step-desc">
						Enter your <strong>LDAP username</strong> as the username and your
						<strong>802.1x password</strong> as the password. Leave the domain field empty.
						Save and connect.
					</div>
				</li>
			</ol>
		{:else if activeTab === 'windows'}
			<ol class="step-list">
				<li class="step-item">
					<div class="step-title">Open WiFi Settings</div>
					<div class="step-desc">
						Click the WiFi icon in the system tray and select
						<strong>Network &amp; Internet settings</strong>.
					</div>
				</li>
				<li class="step-item">
					<div class="step-title">Connect to wifi@iiith</div>
					<div class="step-desc">
						Find <strong>wifi@iiith</strong> and click <strong>Connect</strong>.
						You'll be prompted for credentials.
					</div>
				</li>
				<li class="step-item">
					<div class="step-title">Enter Credentials</div>
					<div class="step-desc">
						Enter your <strong>LDAP username</strong> and <strong>802.1x password</strong>.
						If asked about a certificate, choose <strong>Trust</strong> or
						<strong>Connect anyway</strong>.
					</div>
				</li>
				<li class="step-item">
					<div class="step-title">Done</div>
					<div class="step-desc">
						Windows will save the credentials and connect automatically from now on.
						If you need to update your password later, go to
						<strong>Manage known networks</strong> &gt; <strong>wifi@iiith</strong> &gt;
						<strong>Properties</strong>.
					</div>
				</li>
			</ol>
		{:else if activeTab === 'macos'}
			<ol class="step-list">
				<li class="step-item">
					<div class="step-title">Open System Settings</div>
					<div class="step-desc">
						Go to <strong>System Settings</strong> &gt; <strong>WiFi</strong>.
						Yes, it's buried under six layers of UI. That's Apple for you.
					</div>
				</li>
				<li class="step-item">
					<div class="step-title">Connect to wifi@iiith</div>
					<div class="step-desc">
						Find <strong>wifi@iiith</strong> and click <strong>Connect</strong>.
						Enter your <strong>LDAP username</strong> and <strong>802.1x password</strong>.
					</div>
				</li>
				<li class="step-item">
					<div class="step-title">Trust the Certificate</div>
					<div class="step-desc">
						macOS will show a scary dialog saying the certificate can't be verified.
						Click <strong>Trust</strong> or <strong>Continue</strong>. The RADIUS server is
						safe — Apple just doesn't like things it didn't manufacture.
					</div>
				</li>
				<li class="step-item">
					<div class="step-title">You're Online. Don't Drop It.</div>
					<div class="step-desc">
						You're connected. If macOS asks to "verify" the network again later, just
						click Trust again. It'll learn eventually. (Or maybe not. It's a Mac.)
					</div>
				</li>
			</ol>
		{/if}

		<div class="section-divider"></div>

		<div class="info-box" style="border-color: #fde68a; background: #fffbeb;">
			<p>
				<strong>Tip:</strong> If you forget your 802.1x password, visit
				<code>passwordreset.iiit.ac.in</code> and reset it from the 802.1x tab.
			</p>
		</div>
	</div>
</div>
