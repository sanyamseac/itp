<script lang="ts">
	import { goto } from '$app/navigation';
	import { ArrowLeft, ArrowUpRight } from '@lucide/svelte';
</script>

<div class="detail-overlay" style="view-transition-name: card-moodle">
	<div class="detail-content">
		<button class="back-link" onclick={() => goto('/')} aria-label="Go back">
			<ArrowLeft size={16} /> Back
		</button>

		<h1>Moodle</h1>
		<p class="subtitle">The learning management system</p>

		<div class="section-divider"></div>

		<div class="info-box" style="background: #fef9c3; border-color: #facc15;">
			<p>
				<strong>Only works on campus.</strong> Moodle is only accessible from IIIT WiFi
				or LAN. Off campus?
				<a href="/vpn" class="inline-link">Connect via VPN <ArrowUpRight size={14} /></a> first.
				This applies to both the website and the mobile app.
			</p>
		</div>

		<h2>What is Moodle?</h2>
		<p>
			Moodle is IIIT's learning management system at
			<a href="https://courses.iiit.ac.in" target="_blank" rel="noopener noreferrer" class="inline-link">
				courses.iiit.ac.in <ArrowUpRight size={14} />
			</a>.
			Every course you're enrolled in will have a page here with all the materials,
			assignments, and announcements.
		</p>

		<div class="section-divider"></div>

		<h2>Announcements</h2>
		<p>
			Every course has an <strong>announcements forum</strong>. This is the main channel
			for communication — professors, TAs, and even <strong>you</strong> can post there,
			and it reaches everyone in the course instantly.
		</p>
		<p>
			<strong>Every post triggers an email</strong> to the entire class, so keep an eye
			on your inbox. If you need to tell your prof or the whole class something, post it
			on the announcements forum.
		</p>

		<div class="section-divider"></div>

		<h2>Assignments</h2>
		<p>
			Most of your assignments will be submitted through Moodle. You can either
			<strong>type them out digitally</strong> or <strong>write on paper, take a picture,</strong>
			and upload the PDF — Moodle accepts all common file formats.
		</p>
		<p>
			Assignments usually have <strong>deadlines</strong>, so keep an eye on the submission
			portal. TAs will post detailed instructions on Moodle for the first few assignments,
			including formatting guidelines and where to upload.
		</p>

		<div class="section-divider"></div>

		<h2>Moodle Mobile App</h2>
		<p>
			There's a <strong>Moodle</strong> app available on the
			<a href="https://play.google.com/store/apps/details?id=com.moodle.moodlemobile" target="_blank" rel="noopener noreferrer" class="inline-link">
				Play Store <ArrowUpRight size={14} />
			</a>
			and
			<a href="https://apps.apple.com/app/moodle/id633359593" target="_blank" rel="noopener noreferrer" class="inline-link">
				App Store <ArrowUpRight size={14} />
			</a>.
			You can link your IIIT account to it and access courses on the go. Just remember
			— the app also needs campus WiFi or VPN to login and upload data. Good thing is 
            anything opened once or downloaded remains cached on device, so you don't have to turn VPN
            on everytime.</p>

		<div style="margin-top: 2rem;">
			<button class="cta-btn" onclick={() => window.open('https://courses.iiit.ac.in', '_blank', 'noopener,noreferrer')}>
				Open Moodle
				<ArrowUpRight size={16} />
			</button>
		</div>
	</div>
</div>