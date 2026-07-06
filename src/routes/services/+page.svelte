<script lang="ts">
	import { goto } from '$app/navigation';
	import { ArrowLeft, ArrowUpRight } from '@lucide/svelte';
</script>

<svelte:head>
	<title>Services | IIIT Hyderabad Intro to Portals Guide</title>
	<meta name="description" content="IIIT Hyderabad Service Payments portal — semester transcript, ID card replacement, electricity and water bill payments." />
</svelte:head>

<div class="detail-overlay" style="view-transition-name: card-services">
	<div class="detail-content">
		<button class="back-link" onclick={() => goto('/')} aria-label="Go back">
			<ArrowLeft size={16} /> Back
		</button>

		<h1>Services</h1>
		<p class="subtitle">Service Payments Portal</p>

		<div class="section-divider"></div>

		<h2>What is it?</h2>
		<p>
			<a href="https://ims-extr.iiit.ac.in/office_payments.php" target="_blank" rel="noopener noreferrer" class="inline-link">
				Service Payments Portal <ArrowUpRight size={14} /></a>
			lets current students pay for and avail various campus services.
		</p>

		<div class="section-divider"></div>

		<h2>Available Services</h2>
		<ul class="step-list">
			<li class="step-item"><strong>Semester Transcript</strong> — get an official copy of your transcript</li>
			<li class="step-item"><strong>Desert Cooler charges</strong> — pay electricity and water bills if you're using desert coolers</li>
			<li class="step-item"><strong>New ID Card</strong> — replace a lost or damaged ID card</li>
			<li class="step-item"><strong>And more</strong> — other administrative services are available too</li>
		</ul>

		<div style="margin-top: 2rem;">
			<button class="cta-btn" onclick={() => window.open('https://ims-extr.iiit.ac.in/office_payments.php', '_blank', 'noopener,noreferrer')}>
				Open Services Portal
				<ArrowUpRight size={16} />
			</button>
		</div>
	</div>
</div>