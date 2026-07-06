<script lang="ts">
	import { goto } from '$app/navigation';
import { ArrowLeft, ArrowUpRight } from '@lucide/svelte';
	let activeTab = $state<'ubuntu' | 'windows' | 'macos'>('ubuntu');
</script>

<svelte:head>
	<title>Ethernet | IIIT Hyderabad Intro to Portals Guide</title>
	<meta name="description" content="Set up ethernet / LAN connection in IIIT Hyderabad hostels. Static IP configuration for Windows, macOS, and Linux." />
</svelte:head>

<div class="detail-overlay" style="view-transition-name: card-ethernet">
	<div class="detail-content">
		<button class="back-link" onclick={() => goto('/')} aria-label="Go back">
			<ArrowLeft size={16} /> Back
		</button>

		<h1>Wired Ethernet</h1>
		<p class="subtitle">802.1x wired network guide</p>

		<div class="section-divider"></div>

		<h2>Campus Ethernet</h2>
		<p>
			Wired Ethernet ports in labs, classrooms, and hostels use the same 802.1x authentication
			as the campus WiFi. Plug in, authenticate, and you're online.
		</p>

		<div class="info-box">
			<p>
				<strong>Authentication:</strong> 802.1x / PEAP / MSCHAPv2<br />
				<strong>Credentials:</strong> Your email ID (not just username) and 802.1x password
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
					<div class="step-title">Plug In the Ethernet Cable</div>
					<div class="step-desc">
						Connect the cable to your laptop. Ubuntu should detect the connection
						automatically and prompt for credentials.
					</div>
				</li>
				<li class="step-item">
					<div class="step-title">Select 802.1x Enterprise</div>
					<div class="step-desc">
						In the network manager, set <strong>802.1x Security</strong> to
						<strong>WPA2/WPA3 Enterprise</strong>. Choose <strong>PEAP</strong> as the
						authentication and <strong>MSCHAPv2</strong> as Phase 2.
					</div>
				</li>
				<li class="step-item">
					<div class="step-title">Enter Credentials</div>
					<div class="step-desc">
						Enter your <strong>email ID</strong> and <strong>802.1x password</strong>.
						Leave the CA certificate as <strong>Trust on First Use</strong> or
						<strong>Don't validate</strong>.
					</div>
				</li>
				<li class="step-item">
					<div class="step-title">Connect</div>
					<div class="step-desc">
						Save and connect. You should be online immediately.
					</div>
				</li>
			</ol>
		{:else if activeTab === 'windows'}
			<ol class="step-list">
				<li class="step-item">
					<div class="step-title">Plug In the Ethernet Cable</div>
					<div class="step-desc">
						Connect the cable. Windows will identify the network and prompt you
						to sign in.
					</div>
				</li>
				<li class="step-item">
					<div class="step-title">Click the Notification</div>
					<div class="step-desc">
						Click the network pop-up in the bottom-right and select
						<strong>Connect</strong>. If nothing appears, open
						<strong>Settings &gt; Network &amp; Internet &gt; Ethernet</strong>.
					</div>
				</li>
				<li class="step-item">
					<div class="step-title">Enter Credentials</div>
					<div class="step-desc">
						Enter your <strong>email ID</strong> and <strong>802.1x password</strong>.
						If asked to trust a certificate, click <strong>Trust</strong>.
					</div>
				</li>
				<li class="step-item">
					<div class="step-title">Done</div>
					<div class="step-desc">
						You're connected. Windows should remember the credentials for next time. If it's 
                        asking you everytime to sign in, follow the guide on the <a href="https://self-help.iiit.ac.in/wiki/index.php/Wired_Network" target="_blank" rel="noopener noreferrer" class="inline-link">
                            Wired Network - Self Help <ArrowUpRight size={14} /></a> to save the credentials.
					</div>
				</li>
			</ol>
		{:else if activeTab === 'macos'}
			<ol class="step-list">
				<li class="step-item">
					<div class="step-title">Plug In</div>
					<div class="step-desc">
						Connect the Ethernet cable to your Mac.
					</div>
				</li>
                <li class="step-item">
                    <div class="step-title">Click Popup</div>
                    <div class="step-desc">
                        Mac OS X should automatically detect 802.1x and display pop up window asking username and password.
                    </div>
                </li>
				<li class="step-item">
					<div class="step-title">Enter Credentials</div>
					<div class="step-desc">
						Set <strong>Username</strong> to your email ID and
						<strong>Password</strong> to your 802.1x password. Click
						<strong>Apply</strong>.
					</div>
				</li>
				<li class="step-item">
					<div class="step-title">Hotspot? Forget It.</div>
					<div class="step-desc">
						One more thing - macOS won't let you share this wired connection as a
						hotspot either. 802.1x networks are blocked from sharing. Enjoy not being able to use campus ethernet as a hotspot. Apple is fun.
					</div>
				</li>
			</ol>
		{/if}

		<div class="section-divider"></div>

		<div class="info-box">
			<p>
				More details on the
				<a href="https://self-help.iiit.ac.in/wiki/index.php/Wired_Network" target="_blank" rel="noopener noreferrer" class="inline-link">
					Wired Network - Self Help
					<ArrowUpRight size={14} />
				</a>
				page. This wiki is only accessible from the campus WiFi or Ethernet.
			</p>
		</div>
	</div>
</div>