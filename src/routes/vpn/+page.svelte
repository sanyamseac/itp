<script lang="ts">
	import { goto } from '$app/navigation';
	import { ArrowLeft, ArrowUpRight } from '@lucide/svelte';

	let activeTab = $state<'windows' | 'linux' | 'macos' | 'ios' | 'android'>('windows');
</script>

<div class="detail-overlay" style="view-transition-name: card-vpn">
	<div class="detail-content">
		<button class="back-link" onclick={() => goto('/')} aria-label="Go back">
			<ArrowLeft size={16} /> Back
		</button>

		<h1>VPN Access</h1>
		<p class="subtitle">Connect to campus from outside</p>

		<div class="section-divider"></div>

		<h2>About the VPN</h2>
		<p>
			IIIT's VPN uses <strong>OpenVPN</strong> to let you access campus resources
			(portals, library journals, file shares, etc.) from outside the campus network.
			It <strong>only works outside campus</strong> — if you're on campus WiFi or Ethernet,
			the VPN will not connect.
		</p>

		<div class="info-box">
			<p>
				<strong>Server:</strong> <code>vpn2.iiit.ac.in</code><br />
				<strong>Protocol:</strong> OpenVPN (SSL/TLS)<br />
				<strong>Credentials:</strong> Your full email ID and LDAP password<br />
				<strong>Config file:</strong> <code>.ovpn</code> (download per device)
			</p>
		</div>

		<div class="section-divider"></div>

		<!-- ── OS Tabs ── -->
		<div class="tabs">
			<button
				class="tab-btn {activeTab === 'linux' ? 'active' : ''}"
				onclick={() => activeTab = 'linux'}
			>Linux</button>
			<button
				class="tab-btn {activeTab === 'windows' ? 'active' : ''}"
				onclick={() => activeTab = 'windows'}
			>Windows</button>
            <button
				class="tab-btn {activeTab === 'android' ? 'active' : ''}"
				onclick={() => activeTab = 'android'}
			>Android</button>
			<button
				class="tab-btn {activeTab === 'macos' ? 'active' : ''}"
				onclick={() => activeTab = 'macos'}
			>macOS</button>
			<button
				class="tab-btn {activeTab === 'ios' ? 'active' : ''}"
				onclick={() => activeTab = 'ios'}
			>iOS</button>
		</div>

		{#if activeTab === 'windows'}
			<ol class="step-list">
				<li class="step-item">
					<div class="step-title">Download OpenVPN Client</div>
					<div class="step-desc">
						Download the OpenVPN client from
						<a href="https://openvpn.net/community-downloads" target="_blank" rel="noopener noreferrer" class="inline-link">
							openvpn.net/community-downloads
							<ArrowUpRight size={14} />
						</a>
						. Install it by right-clicking the installer and choosing
						<strong>Run as administrator</strong>.
					</div>
				</li>
				<li class="step-item">
					<div class="step-title">Download the .ovpn Config</div>
					<div class="step-desc">
						Visit <a href="https://vpn.iiit.ac.in" target="_blank" rel="noopener noreferrer" class="inline-link">
							vpn.iiit.ac.in<ArrowUpRight size={14} />
						</a>
						and download the <strong>Windows config</strong> file. You'll need to enter your
						<strong>full email ID</strong> to download it.
					</div>
				</li>
				<li class="step-item">
					<div class="step-title">Import the Config</div>
					<div class="step-desc">
						Open the OpenVPN GUI (look for the monitor icon in the system tray).
						Right-click the icon and select <strong>Import</strong>, then choose the
						<code>.ovpn</code> file you downloaded.
					</div>
				</li>
				<li class="step-item">
					<div class="step-title">Connect</div>
					<div class="step-desc">
						Right-click the OpenVPN icon again and select <strong>Connect</strong>.
						Enter your <strong>full email ID</strong> and <strong>LDAP password</strong>.
						The icon will turn <strong>green</strong> when connected.
					</div>
				</li>
			</ol>
		{:else if activeTab === 'linux'}
			<ol class="step-list">
				<li class="step-item">
					<div class="step-title">Install OpenVPN</div>
					<div class="step-desc">
						Install OpenVPN from your package manager:
						<br /><code>sudo apt install openvpn</code> (Debian/Ubuntu)
						<br /><code>sudo pacman -S openvpn</code> (Arch)
					</div>
				</li>
				<li class="step-item">
					<div class="step-title">Download the .ovpn Config</div>
					<div class="step-desc">
						Visit <a href="https://vpn.iiit.ac.in" target="_blank" rel="noopener noreferrer" class="inline-link">
							vpn.iiit.ac.in<ArrowUpRight size={14} />
						</a>
						and download the <strong>Linux config</strong> file. You'll need your full email ID.
					</div>
				</li>
				<li class="step-item">
					<div class="step-title">Connect via Terminal</div>
					<div class="step-desc">
						Run: <code>sudo openvpn --config /path/to/config.ovpn</code>
						<br />Enter your <strong>full email ID</strong> and <strong>LDAP password</strong>
						when prompted. Leave the terminal open to stay connected.
					</div>
				</li>
			</ol>
		{:else if activeTab === 'macos'}
			<ol class="step-list">
				<li class="step-item">
					<div class="step-title">Install Tunnelblick</div>
					<div class="step-desc">
						Download Tunnelblick from
						<a href="https://tunnelblick.net" target="_blank" rel="noopener noreferrer" class="inline-link">
							tunnelblick.net<ArrowUpRight size={14} />
						</a>
						and install it.
					</div>
				</li>
				<li class="step-item">
					<div class="step-title">Download the .ovpn Config</div>
					<div class="step-desc">
						Visit <a href="https://vpn.iiit.ac.in" target="_blank" rel="noopener noreferrer" class="inline-link">
							vpn.iiit.ac.in<ArrowUpRight size={14} />
						</a>
						and download the <strong>macOS config</strong> file.
					</div>
				</li>
				<li class="step-item">
					<div class="step-title">Import &amp; Connect</div>
					<div class="step-desc">
						Double-click the downloaded <code>.ovpn</code> file — Tunnelblick will
						import it automatically. Click the Tunnelblick icon in the menu bar and
						select <strong>Connect</strong>. Enter your full email ID and LDAP password.
					</div>
				</li>
			</ol>
		{:else if activeTab === 'ios'}
			<ol class="step-list">
				<li class="step-item">
					<div class="step-title">Install OpenVPN Connect</div>
					<div class="step-desc">
						Download <strong>OpenVPN Connect</strong> from the App Store.
						It's free and official.
					</div>
				</li>
				<li class="step-item">
					<div class="step-title">Download the .ovpn Config</div>
					<div class="step-desc">
						Visit <a href="https://vpn.iiit.ac.in" target="_blank" rel="noopener noreferrer" class="inline-link">
							vpn.iiit.ac.in<ArrowUpRight size={14} />
						</a>
						on your device and download the <strong>iOS config</strong> file.
					</div>
				</li>
				<li class="step-item">
					<div class="step-title">Import &amp; Connect</div>
					<div class="step-desc">
						Open the downloaded file with OpenVPN Connect. Tap <strong>Add</strong>,
						then tap <strong>Connect</strong>. Enter your full email ID and LDAP password.
					</div>
				</li>
			</ol>
		{:else if activeTab === 'android'}
			<ol class="step-list">
				<li class="step-item">
					<div class="step-title">Install OpenVPN Connect</div>
					<div class="step-desc">
						Download <strong>OpenVPN Connect</strong> from the Play Store.
						It's free and open source.
					</div>
				</li>
				<li class="step-item">
					<div class="step-title">Download the .ovpn Config</div>
					<div class="step-desc">
						Visit <a href="https://vpn.iiit.ac.in" target="_blank" rel="noopener noreferrer" class="inline-link">
							vpn.iiit.ac.in<ArrowUpRight size={14} />
						</a>
						on your device and download the <strong>Android config</strong> file.
					</div>
				</li>
				<li class="step-item">
					<div class="step-title">Import &amp; Connect</div>
					<div class="step-desc">
						Open the downloaded file — it should launch OpenVPN Connect.
						Tap <strong>Import</strong>, then tap <strong>Connect</strong>.
						Enter your full email ID and LDAP password.
					</div>
				</li>
			</ol>
		{/if}

		<div class="section-divider"></div>

		<div class="info-box">
			<p>
				For detailed instructions and the latest config files, visit
				<a href="https://vpn.iiit.ac.in" target="_blank" rel="noopener noreferrer" class="inline-link">
					vpn.iiit.ac.in
					<ArrowUpRight size={14} />
				</a>
			</p>
		</div>
	</div>
</div>