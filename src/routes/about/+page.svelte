<script lang="ts">
	import { goto } from '$app/navigation';
	import { ArrowLeft, ArrowUpRight } from '@lucide/svelte';
</script>

<div class="detail-overlay" style="view-transition-name: card-about">
	<div class="detail-content">
		<button class="back-link" onclick={() => goto('/')} aria-label="Go back">
			<ArrowLeft size={16} /> Back
		</button>

		<h1>About</h1>
		<p class="subtitle">Hope you liked it!</p>

		<div class="section-divider"></div>

		<p>
			Made with care by <strong>Sanyam Gandhi</strong>.
		</p>

		<ul class="step-list">
			<li class="step-item">
				GitHub: <a href="https://github.com/sanyamseac" target="_blank" rel="noopener noreferrer" class="inline-link">
					@sanyamseac <ArrowUpRight size={14} />
				</a>
			</li>
			<li class="step-item">
				Email: <a href="mailto:sanyam.gandhi@research.iiit.ac.in" class="inline-link">
					sanyam.gandhi@research.iiit.ac.in <ArrowUpRight size={14} />
				</a>
			</li>
		</ul>

		<p>
			Feel free to reach out if you spot any wrong info or have something you'd like
			to add to this website.
		</p>

		<div class="section-divider"></div>

		<h2>Contributors</h2>
		<p>None as of now.</p>

		<div class="section-divider"></div>

		<h2>Source Code</h2>
		<p>
			This website is open source! Find the repo at
			<a href="https://github.com/sanyamseac/itp" target="_blank" rel="noopener noreferrer" class="inline-link">
				github.com/sanyamseac/itp <ArrowUpRight size={14} />
			</a>.
			Contributions and suggestions are welcome.
		</p>

		<div style="margin-top: 2rem;">
			<button class="cta-btn" onclick={() => goto('/')}>
				Back to Home
			</button>
		</div>
	</div>
</div>