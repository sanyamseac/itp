<script lang="ts">
	import { goto } from '$app/navigation';
	import { ArrowLeft, ArrowUpRight } from '@lucide/svelte';
</script>

<div class="detail-overlay" style="view-transition-name: card-mess">
	<div class="detail-content">
		<button class="back-link" onclick={() => goto('/')} aria-label="Go back">
			<ArrowLeft size={16} /> Back
		</button>

		<h1>Mess</h1>
		<p class="subtitle">Meal booking system</p>

		<div class="section-divider"></div>

		<div class="info-box" style="background: #fef9c3; border-color: #facc15;">
			<p>
				<strong>Only works on campus.</strong> Mess portal is accessible from IIIT WiFi
				or LAN. Off campus?
				<a href="/vpn" class="inline-link">Connect via VPN <ArrowUpRight size={14} /></a> first.
				You'll also need to log in with your
				<a href="/login" class="inline-link">CAS credentials <ArrowUpRight size={14} /></a>.
			</p>
		</div>

		<h2>Overview</h2>
		<p>
			<a href="https://mess.iiit.ac.in" target="_blank" rel="noopener noreferrer" class="inline-link">
				mess.iiit.ac.in <ArrowUpRight size={14} /></a>
			is the meal booking portal. Once you log in via CAS, you can register for a dining
			hall and start booking meals.
		</p>

		<div class="section-divider"></div>

		<h2>Booking Meals</h2>
		<p>
			After registering for a specific dining hall, you can book a <strong>different
			dining hall</strong> for each meal if you want. There's also an option to book
			extra items along with your meal.
		</p>
		<p>
			<strong>Heads up:</strong> if you don't book a meal at least <strong>4 days</strong>{' '}
			in advance, you'll be auto-assigned a <strong>veg meal</strong>.
		</p>

		<h2>Menu</h2>
		<p>
			You can view the menu by directly <strong>clicking on a date</strong> in the
			calendar, or by going to the <strong>Mess</strong> option from the navbar.
		</p>

		<div class="section-divider"></div>

		<h2>Bulk Registration</h2>
		<p>
			Need to register for multiple dates at once? Go to
			<strong>Menu → Range Registrations</strong>. There's a usage guide right there
			in the same menu to help you out.
		</p>

		<div class="section-divider"></div>

		<h2>Auth Key &amp; Settings</h2>
		<p>
			Head to <strong>Menu → Settings</strong> to create an <strong>auth key</strong>
			and manage your preferences. This auth key lets the
			<a href="/app" class="inline-link">My IIIT app <ArrowUpRight size={14} /></a>
			register for mess on your behalf without needing VPN.
		</p>
		<p style="font-style: italic; color: #666; margin-top: 0.5rem;">
			Managing auth / API keys is the first real proof that you've joined IIIT.
		</p>

		<div class="section-divider"></div>

		<h2>API Docs</h2>
		<p>
			Feeling adventurous? Check out
			<a href="https://mess.iiit.ac.in/api/docs" target="_blank" rel="noopener noreferrer" class="inline-link">
				mess.iiit.ac.in/api/docs <ArrowUpRight size={14} /></a>
			and build your own app to do whatever you want.
		</p>

		<div style="margin-top: 2rem;">
			<button class="cta-btn" onclick={() => window.open('https://mess.iiit.ac.in', '_blank', 'noopener,noreferrer')}>
				Open Mess Portal
				<ArrowUpRight size={16} />
			</button>
		</div>
	</div>
</div>