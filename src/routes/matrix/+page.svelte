<script lang="ts">
	import { goto } from '$app/navigation';
	import { ArrowLeft, ArrowUpRight } from '@lucide/svelte';

	function openElement() {
		window.open('https://app.element.io', '_blank', 'noopener,noreferrer');
	}
</script>

<svelte:head>
	<title>Matrix | IIIT Hyderabad Intro to Portals Guide</title>
	<meta name="description" content="IIIT Hyderabad's self-hosted Matrix chat server — sign in with LDAP, join community spaces, course rooms, and interest groups." />
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
			server — a decentralized, open-source chat platform. You can use any Matrix client
			and sign in with your LDAP credentials to join campus-wide spaces, course rooms,
			and interest groups.
		</p>

		<div class="info-box">
			<p>
				<strong>Homeserver:</strong> <code>matrix.iiit.ac.in</code><br />
				<strong>Username:</strong> the part of your college email before the <code>@</code><br />
				<strong>Password:</strong> your LDAP/CAS password<br />
				<strong>Login method:</strong> Username/Password (OAuth is not supported yet)
			</p>
		</div>

		<div class="section-divider"></div>

		<h2>Getting Started</h2>

		<ol class="step-list">
			<li class="step-item">
				<div class="step-title">Pick a Client</div>
				<div class="step-desc">
					For the most stable experience, use
					<a href="https://app.element.io" target="_blank" rel="noopener noreferrer" class="inline-link">
						<code>app.element.io</code>
						<ArrowUpRight size={14} />
					</a>
					in your browser, grab
					<a href="https://element.io/download" target="_blank" rel="noopener noreferrer" class="inline-link">
						Element Desktop
						<ArrowUpRight size={14} />
					</a>
					for Windows, macOS, or Linux, or download the <strong>Element X</strong> app on your
					phone. You can also browse
					<a href="https://matrix.org/ecosystem/clients" target="_blank" rel="noopener noreferrer" class="inline-link">
						matrix.org/ecosystem/clients
						<ArrowUpRight size={14} />
					</a>
					for alternatives.
				</div>
			</li>
			<li class="step-item">
				<div class="step-title">Change the Homeserver</div>
				<div class="step-desc">
					On the sign-in screen, change the homeserver from the default
					<code>matrix.org</code> to <code>matrix.iiit.ac.in</code>. Don't skip this — otherwise
					you'll be creating an account on the public server instead.
				</div>
			</li>
			<li class="step-item">
				<div class="step-title">Allow Internal Network Access</div>
				<div class="step-desc">
					On browser clients, the website might ask for permission to access the internal
					network. Allow it, or the client won't be able to reach the IIIT homeserver. The
					server is reachable from the public internet, so you can use it off campus too.
				</div>
			</li>
			<li class="step-item">
				<div class="step-title">Sign In</div>
				<div class="step-desc">
					Choose <strong>Username/Password</strong> login (not OAuth/SSO) and enter your LDAP
					username (the part before <code>@</code> in your email) and your LDAP/CAS password.
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
					<a href="https://matrix.to/#/#community:matrix.iiit.ac.in" target="_blank" rel="noopener noreferrer" class="inline-link">
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
					<a href="https://matrix.to/#/#m26-courses:matrix.iiit.ac.in" target="_blank" rel="noopener noreferrer" class="inline-link">
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
					<a href="https://matrix.to/#/#interests:matrix.iiit.ac.in" target="_blank" rel="noopener noreferrer" class="inline-link">
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
				<strong>Important:</strong> For encrypted chats (outside groups), there is <strong>no way</strong>
				to retrieve your messages if you lose your backup key. Take utmost care of it.
			</p>
		</div>

		<div class="section-divider"></div>

		<h2>Storage &amp; Backups</h2>
		<p>Matrix stores everything on the server (encrypted), so a few limits keep storage in check:</p>

		<ol class="step-list">
			<li class="step-item">
				<div class="step-title">Media Is Deleted After 7 Days</div>
				<div class="step-desc">
					Any uploaded media is deleted after 7 days — download and save important files to
					your device. This window may be extended to 30 days in the future based on usage,
					but that's not a guarantee.
				</div>
			</li>
			<li class="step-item">
				<div class="step-title">Text Messages Are Kept</div>
				<div class="step-desc">
					Text messages won't be deleted for at least 1 year, unless there's some important
					reason to do so.
				</div>
			</li>
			<li class="step-item">
				<div class="step-title">Keep Your Own Backups</div>
				<div class="step-desc">
					Server-side backups are still being set up. Most clients cache messages on your
					device, but keep your own backup of sensitive messages just in case.
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
				Open Element Web
				<ArrowUpRight size={16} />
			</button>
			<p style="margin-top: 0.5rem; font-size: 0.8rem; color: #9ca3af;">
				Opens app.element.io in a new tab
			</p>
		</div>
	</div>
</div>
