<script lang="ts">
	import { goto } from '$app/navigation';
	import { ArrowLeft, ArrowUpRight } from '@lucide/svelte';
</script>
	
<svelte:head>
	<title>About | IIIT Hyderabad Intro to Portals Guide</title>
	<meta name="description" content="About the IIIT Hyderabad Intro to Portals Guide — made by Sanyam Gandhi. Open source and community-driven." />
</svelte:head>

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

		<h2>Collaborators</h2>
		<ul class="step-list">
			<li class="step-item">
				<div class="step-title">Abhyudit "Norman" Singh</div>
				<div class="step-desc">
					<a href="mailto:abhyudit.singh@research.iiit.ac.in" class="inline-link">
						abhyudit.singh@research.iiit.ac.in <ArrowUpRight size={14} />
					</a>
					·
					<a href="https://github.com/bitmap4" target="_blank" rel="noopener noreferrer" class="inline-link">
						@bitmap4 <ArrowUpRight size={14} />
					</a>
				</div>
			</li>
			<li class="step-item">
				<div class="step-title">Ishaan Romil</div>
				<div class="step-desc">
					<a href="mailto:ishaan.romil@research.iiit.ac.in" class="inline-link">
						ishaan.romil@research.iiit.ac.in <ArrowUpRight size={14} />
					</a>
					·
					<a href="https://github.com/Fane1824" target="_blank" rel="noopener noreferrer" class="inline-link">
						@Fane1824 <ArrowUpRight size={14} />
					</a>
				</div>
			</li>
			<li class="step-item">
				<div class="step-title">Manasi Mundada</div>
				<div class="step-desc">
					<a href="mailto:manasi.mundada@students.iiit.ac.in" class="inline-link">
						manasi.mundada@students.iiit.ac.in <ArrowUpRight size={14} />
					</a>
					·
					<a href="https://github.com/manasimundada" target="_blank" rel="noopener noreferrer" class="inline-link">
						@manasimundada <ArrowUpRight size={14} />
					</a>
				</div>
			</li>
		</ul>

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