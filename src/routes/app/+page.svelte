<script lang="ts">
	import { goto } from '$app/navigation';
	import { ArrowLeft, ArrowUpRight } from '@lucide/svelte';
</script>

<svelte:head>
	<title>My IIIT App | IIIT Hyderabad Intro to Portals Guide</title>
	<meta name="description" content="My IIIT app for IIIT Hyderabad — check attendance, timetable, transcript, apply for leaves, and manage mess bookings." />
</svelte:head>

<div class="detail-overlay" style="view-transition-name: card-app">
	<div class="detail-content">
		<button class="back-link" onclick={() => goto('/')} aria-label="Go back">
			<ArrowLeft size={16} /> Back
		</button>

		<h1>My IIIT App</h1>
		<p class="subtitle">Your campus companion</p>

		<div class="section-divider"></div>

		<h2>Download</h2>
		<p>
			Grab the My IIIT app from your app store:
		</p>
		<ul class="step-list">
			<li class="step-item">
				<a href="https://play.google.com/store/apps/details?id=com.iiith.ims_app" target="_blank" rel="noopener noreferrer" class="inline-link">
					Android — Play Store <ArrowUpRight size={14} />
				</a>
			</li>
			<li class="step-item">
				<a href="https://apps.apple.com/in/app/my-iiit/id6754322138" target="_blank" rel="noopener noreferrer" class="inline-link">
					iOS — App Store <ArrowUpRight size={14} />
				</a>
			</li>
		</ul>

		<div class="section-divider"></div>

		<h2>Sign In</h2>
		<p>
			Log in with your <strong>LDAP credentials</strong> (the same ones you use for
			<a href="/ldap" class="inline-link">LDAP <ArrowUpRight size={14} /></a>).
		</p>

		<div class="section-divider"></div>

		<h2>What You Can Do</h2>
		<p>
			Once signed in, you can access all of these right from the app:
		</p>
		<ul class="step-list">
			<li class="step-item"><strong>Attendance</strong> — check your attendance on the go</li>
			<li class="step-item"><strong>Timetable</strong> — your class schedule at a glance</li>
			<li class="step-item"><strong>Transcript</strong> — view your grades and academic record</li>
			<li class="step-item"><strong>Apply for Leaves</strong> — submit leave requests</li>
			<li class="step-item"><strong>Leave Status</strong> — track pending and approved leaves</li>
			<li class="step-item"><strong>Sports Attendance</strong> — check your sports attendance</li>
            <li class="step-item"><strong>Couriers</strong> — check your couriers that are stored in Nilgiri building</li>
		</ul>

		<div class="section-divider"></div>

		<h2>Mess Integration</h2>
		<p>
			Head to the <strong>Mess</strong> tab in the app, add your
			<a href="/mess" class="inline-link">auth key <ArrowUpRight size={14} /></a>
			(from Mess portal → Menu → Settings), and you can manage everything related to
			mess — register for meals, check menus, and more — all without needing VPN.
		</p>

		<div style="margin-top: 2rem; display: flex; gap: 0.75rem; flex-wrap: wrap;">
			<button class="cta-btn" onclick={() => window.open('https://play.google.com/store/apps/details?id=com.iiith.ims_app', '_blank', 'noopener,noreferrer')}>
				Play Store
				<ArrowUpRight size={16} />
			</button>
			<button class="cta-btn" onclick={() => window.open('https://apps.apple.com/in/app/my-iiit/id6754322138', '_blank', 'noopener,noreferrer')}>
				App Store
				<ArrowUpRight size={16} />
			</button>
		</div>
	</div>
</div>