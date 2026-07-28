<script lang="ts">
	import { goto } from '$app/navigation';
	import { ArrowLeft, ArrowUpRight } from '@lucide/svelte';

	function openElement() {
		window.open('https://matrix.iiit.ac.in', '_blank', 'noopener,noreferrer');
	}
</script>

<svelte:head>
	<title>Matrix | IIIT Hyderabad Intro to Portals Guide</title>
	<meta name="description" content="IIIT Hyderabad's self-hosted Matrix chat server — sign in with IIIT CAS, join community spaces, course rooms, and interest groups." />
</svelte:head>

<div class="detail-overlay" style="view-transition-name: card-matrix">
	<div class="detail-content">
		<button class="back-link" onclick={() => goto('/')} aria-label="Go back">
			<ArrowLeft size={16} /> Back
		</button>

		<h1>Matrix Chat</h1>
		<p class="subtitle">IIIT's self-hosted messaging platform</p>

		<div class="section-divider"></div>

		<p>
			IIIT runs its own <a href="https://matrix.org" target="_blank" rel="noopener noreferrer" class="inline-link">Matrix <ArrowUpRight size={14} /></a>
			server — a decentralized, open-source chat platform, now fully live on the public
			internet. You can use any Matrix client and sign in with your <strong>IIIT CAS</strong>
			login to join campus-wide spaces, course rooms, and interest groups.
		</p>

		<div class="info-box">
			<p>
				<strong>Homeserver:</strong> <code>matrix.iiit.ac.in</code><br />
				<strong>Web client:</strong> <a href="https://matrix.iiit.ac.in" target="_blank" rel="noopener noreferrer" class="inline-link">matrix.iiit.ac.in <ArrowUpRight size={14} /></a> (IIIT-hosted, no setup needed)<br />
				<strong>Login method:</strong> IIIT CAS — the same login you use for other campus portals
			</p>
		</div>

		<div class="section-divider"></div>

		<h2>Getting Started</h2>

		<ol class="step-list">
			<li class="step-item">
				<div class="step-title">Pick a Client</div>
				<div class="step-desc">
					The easiest way in is the IIIT-hosted web client at
					<a href="https://matrix.iiit.ac.in" target="_blank" rel="noopener noreferrer" class="inline-link">
						<code>matrix.iiit.ac.in</code>
						<ArrowUpRight size={14} />
					</a>
					— it's a hosted build of Element that already points at our server, so there's no
					provider to select. On mobile, install the <strong>Element X</strong> app; on desktop,
					grab
					<a href="https://element.io/download" target="_blank" rel="noopener noreferrer" class="inline-link">
						Element Desktop
						<ArrowUpRight size={14} />
					</a>
					for Windows, macOS, or Linux. You can also browse
					<a href="https://matrix.org/ecosystem/clients" target="_blank" rel="noopener noreferrer" class="inline-link">
						matrix.org/ecosystem/clients
						<ArrowUpRight size={14} />
					</a>
					for alternatives.
				</div>
			</li>
			<li class="step-item">
				<div class="step-title">Set the Homeserver</div>
				<div class="step-desc">
					If you're using an app rather than the IIIT web client, change the homeserver (a.k.a.
					provider) from the default <code>matrix.org</code> to <code>matrix.iiit.ac.in</code> on
					the sign-in screen. The web client at <code>matrix.iiit.ac.in</code> already has this set.
				</div>
			</li>
			<li class="step-item">
				<div class="step-title">Sign In with CAS</div>
				<div class="step-desc">
					Log in with <strong>IIIT CAS</strong> — the same single sign-on you use for other campus
					portals. (Username/password login is being phased out, so use CAS.)
				</div>
			</li>
			<li class="step-item">
				<div class="step-title">Add More Devices with QR</div>
				<div class="step-desc">
					Already signed in somewhere? You can log in on a new device by scanning a
					<strong>QR code</strong> from an existing session — no need to re-enter credentials or
					re-verify from scratch.
				</div>
			</li>
		</ol>

		<p>
			Prefer a walkthrough? Watch this
			<a href="https://www.youtube.com/watch?v=dzCMZwZVqLw" target="_blank" rel="noopener noreferrer" class="inline-link">
				video tutorial
				<ArrowUpRight size={14} />
			</a>
			on getting set up.
		</p>

		<div class="section-divider"></div>

		<h2>Spaces</h2>
		<p>
			The Interests space is listed in the public room directory, so you can find it by
			searching in your client. The Community space and course rooms aren't listed since
			they're student-only — use the links below to join those:
		</p>

		<div class="domain-grid">
			<div class="domain-card">
				<h3>
					<a href="https://matrix.iiit.ac.in/share/#/#community:matrix.iiit.ac.in" target="_blank" rel="noopener noreferrer" class="inline-link">
						Community Space <ArrowUpRight size={14} />
					</a>
				</h3>
				<p>
					Helpful groups like <strong>Cab Sharing</strong> (find cabs to and from the railway
					station, airport, etc.), <strong>Buy/Sell/Rent</strong>, <strong>Jobs/Internships/Freelancing</strong>,
					<strong>Lost and Found</strong>, and <strong>Common Room</strong> — home to plenty of
					random discussions about developments in college, elective recommendations, and more.
					There are plenty of others, so feel free to explore.
				</p>
			</div>
			<div class="domain-card">
				<h3>
					<a href="https://matrix.iiit.ac.in/share/#/#m26-courses:matrix.iiit.ac.in" target="_blank" rel="noopener noreferrer" class="inline-link">
						M'26 Course Rooms <ArrowUpRight size={14} />
					</a>
				</h3>
				<p>
					Rooms for each course, with TAs present. It's an unofficial platform you can use to
					communicate with TAs, receive course updates, and discuss coursework — though official
					announcements will still be sent on Moodle as well.
				</p>
			</div>
			<div class="domain-card">
				<h3>
					<a href="https://matrix.iiit.ac.in/share/#/#interests:matrix.iiit.ac.in" target="_blank" rel="noopener noreferrer" class="inline-link">
						Interests Space <ArrowUpRight size={14} />
					</a>
				</h3>
				<p>
					Groups for a variety of interests — books, movies, food, comics, games, Roblox, anime,
					and basically anything else. This one's public, so you can also find it by searching
					the room directory. Want something added? Just message the space mods.
				</p>
			</div>
		</div>

		<div class="section-divider"></div>

		<h2>Privacy &amp; Encryption</h2>
		<p>
			The Matrix protocol allows server admins to see users, the groups they are part of, and
			message metadata (from, to, time) — but not message contents, <strong>unless the chat is
			unencrypted</strong>. Administrators can access unencrypted chats via the database, so use
			encrypted chats as much as possible.
		</p>

		<div class="info-box" style="border-color: #fde68a; background: #fffbeb;">
			<p>
				<strong>Back up your encryption key.</strong> Your encrypted messages can only be read on a
				device that holds the key. Save your recovery/backup key somewhere safe — you'll need it to
				read your history when you switch or add a device, and there is <strong>no way</strong> to
				recover encrypted chats without it.
			</p>
		</div>

		<div class="section-divider"></div>

		<h2>Calling</h2>
		<p>
			Voice and video calls are <strong>disabled over the public internet for now</strong>. The
			team plans to enable them soon.
		</p>

		<div class="section-divider"></div>

		<h2>Storage &amp; Backups</h2>
		<p>Matrix stores everything on the server (encrypted), so a few limits keep storage in check:</p>

		<ol class="step-list">
			<li class="step-item">
				<div class="step-title">Messages Are Kept at Least 1 Year</div>
				<div class="step-desc">
					Text messages stay on the server for at least a year, unless there's a necessary
					reason to remove them earlier.
				</div>
			</li>
			<li class="step-item">
				<div class="step-title">Media Is Kept at Least 1 Month</div>
				<div class="step-desc">
					Uploaded media is kept for at least a month before it may be deleted — download and
					save important files to your device so you don't lose them.
				</div>
			</li>
			<li class="step-item">
				<div class="step-title">Backups &amp; Reporting Issues</div>
				<div class="step-desc">
					There are a few message backups on the server, and cloud backups are in the works.
					There's <strong>no media backup planned</strong> for now. If you notice a message
					issue, report it within <strong>2 hours</strong> so the team can recover it easily.
				</div>
			</li>
		</ol>

		<div class="section-divider"></div>

		<h2>Questions?</h2>
		<p>
			Any questions related to Matrix or the IIIT server can be sent to
			<strong>Sanyam</strong> or <strong>Vedant</strong>, who have deployed the service.
		</p>

		<div style="margin-top: 2rem; display: flex; flex-direction: column; align-items: flex-start;">
			<button class="cta-btn" onclick={openElement}>
				Open IIIT Matrix
				<ArrowUpRight size={16} />
			</button>
			<p style="margin-top: 0.5rem; font-size: 0.8rem; color: #9ca3af;">
				Opens matrix.iiit.ac.in in a new tab
			</p>
		</div>
	</div>
</div>
