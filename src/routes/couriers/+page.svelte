<script lang="ts">
	import { goto } from '$app/navigation';
	import { ArrowLeft, ArrowUpRight } from '@lucide/svelte';
</script>

<div class="detail-overlay" style="view-transition-name: card-couriers">
	<div class="detail-content">
		<button class="back-link" onclick={() => goto('/')} aria-label="Go back">
			<ArrowLeft size={16} /> Back
		</button>

		<h1>Couriers</h1>
		<p class="subtitle">couriers.iiit.ac.in</p>

		<div class="section-divider"></div>

		<div class="info-box" style="background: #fef9c3; border-color: #facc15;">
			<p>
				<strong>Only works on campus.</strong> The courier portal is accessible from IIIT WiFi
				or LAN. Off campus?
				<a href="/vpn" class="inline-link">Connect via VPN <ArrowUpRight size={14} /></a> first.
			</p>
		</div>

		<h2>What is it?</h2>
		<p>
			<a href="https://couriers.iiit.ac.in" target="_blank" rel="noopener noreferrer" class="inline-link">
				couriers.iiit.ac.in <ArrowUpRight size={14} /></a>
			is the repository of all couriers currently at <strong>Nilgiri</strong>. If you're in class 
            or unavailable when your delivery arrives, the delivery person drops it at Nilgiri for you to collect later.
		</p>
		<p>
			<strong>Note:</strong> this doesn't apply to quick commerce deliveries (Swiggy,
			Zomato, Blinkit, etc.).
		</p>

		<div class="section-divider"></div>

		<h2>How to Use</h2>
		<p>
			Just check the portal to see if your courier has been delivered, then head to
			Nilgiri and collect it.
		</p>

		<div style="margin-top: 2rem;">
			<button class="cta-btn" onclick={() => window.open('https://couriers.iiit.ac.in', '_blank', 'noopener,noreferrer')}>
				Open Couriers Portal
				<ArrowUpRight size={16} />
			</button>
		</div>
	</div>
</div>