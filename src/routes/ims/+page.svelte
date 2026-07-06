<script lang="ts">
	import { goto } from '$app/navigation';
	import { ArrowLeft, ArrowUpRight } from '@lucide/svelte';
</script>

<svelte:head>
	<title>IMS Portal | IIIT Hyderabad Intro to Portals Guide</title>
	<meta name="description" content="IMS Portal at IIIT Hyderabad — manage academics, student activities, course registration, attendance, and fee payments." />
</svelte:head>

<div class="detail-overlay" style="view-transition-name: card-ims">
	<div class="detail-content">
		<button class="back-link" onclick={() => goto('/')} aria-label="Go back">
			<ArrowLeft size={16} /> Back
		</button>

		<h1>IMS</h1>
		<p class="subtitle">The campus management system</p>

		<div class="section-divider"></div>

		<div class="info-box" style="background: #fef9c3; border-color: #facc15;">
			<p>
				<strong>Only works on campus.</strong> IMS is only accessible from IIIT WiFi or
				LAN. If you're off campus,
				<a href="/vpn" class="inline-link">connect via VPN <ArrowUpRight size={14} /></a> first.
			</p>
		</div>

		<p>
			IMS has a lot of tabs, but as a UG1 student you'll mostly live in
			<strong>My IIIT</strong> and <strong>Academics</strong>.
		</p>

		<div class="section-divider"></div>

		<h2>My IIIT</h2>
		<p>Options you'll actually use:</p>

		<div class="domain-grid">
			<div class="domain-card">
				<h3>My Transcript</h3>
				<p>View your academic transcript and grades.</p>
			</div>
			<div class="domain-card">
				<h3>Fee Payment Details</h3>
				<p>Check fee history, payment status, and pending dues.</p>
			</div>
			<div class="domain-card">
				<h3>Course Registration</h3>
				<p>Register for next semester's courses when the window opens.</p>
			</div>
			<div class="domain-card">
				<h3>Fee Payment</h3>
				<p>Pay semester fees online.</p>
			</div>
			<div class="domain-card">
				<h3>Student Activities</h3>
				<p>Applications for leave, medical claims, and other requests.</p>
			</div>
		</div>

		<div class="section-divider"></div>

		<h3>Student Activities → Applications</h3>
		<p>Two things you might actually need buried in here:</p>

		<div class="domain-grid">
			<div class="domain-card">
				<h3>Medical Claim</h3>
				<p>
					Hospitalised while on campus? You can claim up to
					<strong>₹50,000</strong>.
					<a href="https://intranet.iiit.ac.in/offices/static/files/Student_Medical_Reimbursement_Policy.pdf" target="_blank" rel="noopener noreferrer" class="inline-link">
						Policy <ArrowUpRight size={14} />
					</a>
				</p>
			</div>
			<div class="domain-card">
				<h3>Student Leave Request</h3>
				<p>
					Apply for leave through the system.
					<a href="https://intranet.iiit.ac.in/offices/static/files/Leave_Rules_for_Students.pdf" target="_blank" rel="noopener noreferrer" class="inline-link">
						Policy <ArrowUpRight size={14} />
					</a>
				</p>
			</div>
		</div>

		<p>To submit a leave request:</p>
		<ol class="step-list">
			<li class="step-item">
				<div class="step-title">Add New</div>
				<div class="step-desc">Open the application and click <strong>Add New</strong>.</div>
			</li>
			<li class="step-item">
				<div class="step-title">Fill the Form</div>
				<div class="step-desc">Enter your details, leave dates, and reason.</div>
			</li>
			<li class="step-item">
				<div class="step-title">Attach Documents</div>
				<div class="step-desc">Switch to the <strong>Attach</strong> tab and upload any required supporting docs.</div>
			</li>
			<li class="step-item">
				<div class="step-title">Submit &amp; Confirm</div>
				<div class="step-desc">Click submit. The page reloads — you'll need to <strong>confirm</strong> the submission to complete it.</div>
			</li>
		</ol>

		<div class="info-box" style="border-color: #fca5a5; background: #fef2f2;">
			<p>
				<strong>Classic IMS.</strong> The most important features are always three
				levels deep. Leave requests, medical claims — you'll find them at
				<strong>My IIIT → Student Activities → Applications</strong>.
			</p>
		</div>

		<div class="section-divider"></div>

		<h2>Academics</h2>

		<div class="domain-grid">
			<div class="domain-card">
				<h3>My Courses</h3>
				<p>Overview of all your enrolled courses for the current semester.</p>
			</div>
			<div class="domain-card">
				<h3>Sports Registration</h3>
				<p>
					<strong>Academics → Sports</strong>, click <strong>Add New</strong>,
					pick your preferred activities and time slots when registration opens.
				</p>
			</div>
			<div class="domain-card">
				<h3>Attendance Report</h3>
				<p>Head to <strong>Academics → Attendance</strong> to view your attendance details.</p>
			</div>
			<div class="domain-card">
				<h3>My Sports Attendance</h3>
				<p>Search for <strong>sports</strong> in IMS — your sports attendance tracker will show up.</p>
			</div>
		</div>

		<div style="margin-top: 2rem;">
			<button class="cta-btn" onclick={() => window.open('https://ims.iiit.ac.in', '_blank', 'noopener,noreferrer')}>
				Open IMS
				<ArrowUpRight size={16} />
			</button>
		</div>
	</div>
</div>