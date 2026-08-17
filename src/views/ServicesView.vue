<template>
	<div class="services">
		<!-- Title -->
		<!-- <header class="services__header">
			<h1 class="services__title">
				<span class="spark">✳</span>
				MY OFFERINGS
				<span class="spark">✳</span>
			</h1>
		</header> -->

		<section class="services__layout">
			<!-- Left: categories card -->
			<aside class="card services-menu">
				<button v-for="s in services" :key="s.key" class="menu-item"
					:class="{ 'is-active': s.key === activeKey }" type="button" @click="activeKey = s.key">
					<span class="menu-item__icon" aria-hidden="true">
						<!-- simple inline icons so you don't need extra assets -->
						<svg v-if="s.key === 'photography'" viewBox="0 0 24 24">
							<path
								d="M9 7l1.2-2h3.6L15 7h3a2 2 0 0 1 2 2v9a2 2 0 0 1-2 2H6a2 2 0 0 1-2-2V9a2 2 0 0 1 2-2h3zm3 11a4 4 0 1 0 0-8 4 4 0 0 0 0 8z"
								fill="currentColor" />
						</svg>
						<svg v-else-if="s.key === 'web'" viewBox="0 0 24 24">
							<path
								d="M4 5h16a2 2 0 0 1 2 2v10a2 2 0 0 1-2 2H4a2 2 0 0 1-2-2V7a2 2 0 0 1 2-2zm0 4v8h16V9H4zm3 2h6v2H7v-2z"
								fill="currentColor" />
						</svg>
						<svg v-else-if="s.key === 'branding'" viewBox="0 0 24 24">
							<path d="M12 2l3 6 6 .9-4.5 4.4 1 6.3L12 16.9 6.5 19.6l1-6.3L3 8.9 9 8l3-6z"
								fill="currentColor" />
						</svg>
						<svg v-else viewBox="0 0 24 24">
							<path
								d="M10 2h4v2h-4V2zM7 5h10l1 4H6l1-4zm-1 6h12l1 11H5l1-11zm4 2v7h2v-7H10zm4 0v7h2v-7h-2z"
								fill="currentColor" />
						</svg>
					</span>

					<span class="menu-item__label">{{ s.label }}</span>
				</button>
			</aside>

			<!-- Right: content cards (2x2) -->
			<div class="services-grid">
				<article class="card service-card" v-for="c in activeCards" :key="c.title">
					<h6>{{ c.kicker }}</h6>
					<h3>{{ c.title }}</h3>
					<p>{{ c.body }}</p>

					<ul class="bullets">
						<li v-for="b in c.bullets" :key="b">{{ b }}</li>
					</ul>
				</article>
			</div>
		</section>

		<!-- Bottom row like your home -->
		<section class="services__bottom">
			<ProfilesCard>
				<template #githubIcon>
					<!-- klistra in din GitHub svg här -->
					<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512" style="width: 50px;">
						<path fill="#ffffff" d="..." />
					</svg>
				</template>

				<template #linkedinIcon>
					<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512" style="width: 50px;">
						<path fill="#ffffff" d="..." />
					</svg>
				</template>

				<template #xIcon>
					<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512" style="width: 50px;">
						<path fill="#ffffff" d="..." />
					</svg>
				</template>
			</ProfilesCard>
			<LetsWork />
			<CredentialsCard />


		</section>
	</div>
</template>

<script setup>
import { computed, ref } from "vue";
import { useRouter } from "vue-router";
import CredentialsCard from "@/components/CredentialsCard.vue";
import ProfilesCard from "@/components/ProfilesCard.vue";
import LetsWork from "@/components/LetsWork.vue";

const router = useRouter();
const go = (path) => router.push(path);

const services = [
	{ key: "photography", label: "PHOTOGRAPHY" },
	{ key: "web", label: "WEB DESIGNING" },
	{ key: "branding", label: "BRANDING" },
	{ key: "development", label: "DEVELOPMENT" },
];

const activeKey = ref("web");

/**
 * Content per category (2x2 cards)
 * Byt text när du vill – layouten håller.
 */
const content = {
	photography: [
		{
			kicker: "PHOTOGRAPHY",
			title: "Content sessions",
			body:
				"Clean, consistent visuals for your brand. Delivered in formats that work across web and social.",
			bullets: ["Planning + shotlist", "Editing included", "Web-ready exports"],
		},
		{
			kicker: "PHOTOGRAPHY",
			title: "Product & lifestyle",
			body:
				"Show your product in a premium context that fits your aesthetic. Focus on details and clarity.",
			bullets: ["Studio or outdoor", "Detail shots", "Brand consistency"],
		},
		{
			kicker: "PHOTOGRAPHY",
			title: "Events",
			body:
				"Coverage with fast turnaround. Perfect for launches, meetups, or client events.",
			bullets: ["Highlights set", "Fast delivery", "Optional reels"],
		},
		{
			kicker: "PHOTOGRAPHY",
			title: "Retouch & grading",
			body:
				"Subtle, modern edits. Nothing over-processed — just clean and cinematic.",
			bullets: ["Skin tones", "Lighting balance", "Color grade"],
		},
	],
	web: [
		{
			kicker: "WEB DESIGNING",
			title: "Design system",
			body:
				"Reusable components and spacing rules so your site stays consistent as it grows.",
			bullets: ["Typography scale", "Components", "Responsive rules"],
		},
		{
			kicker: "WEB DESIGNING",
			title: "UX & wireframes",
			body:
				"Structure first, then visuals. We optimize flows so users find what they need fast.",
			bullets: ["User flows", "Low-fi wireframes", "Conversion focus"],
		},
		{
			kicker: "WEB DESIGNING",
			title: "High-fidelity UI",
			body:
				"Polished UI in your brand style. Clean, modern and easy to maintain.",
			bullets: ["Desktop + mobile", "Micro-interactions", "Hand-off ready"],
		},
		{
			kicker: "WEB DESIGNING",
			title: "Landing pages",
			body:
				"Fast, focused pages for campaigns and offers. Built to load quick and look premium.",
			bullets: ["Speed-first", "SEO basics", "Analytics-ready"],
		},
	],
	branding: [
		{
			kicker: "BRANDING",
			title: "Visual identity",
			body:
				"A cohesive look that works everywhere: web, social, pitch decks and products.",
			bullets: ["Logo usage", "Color system", "Type pairings"],
		},
		{
			kicker: "BRANDING",
			title: "Brand guidelines",
			body:
				"Simple rules for consistency. Helps future design stay aligned with your brand.",
			bullets: ["Do/don’t", "Components", "Examples"],
		},
		{
			kicker: "BRANDING",
			title: "Assets pack",
			body:
				"Exported assets in the right formats so you can ship faster without design friction.",
			bullets: ["SVG/PNG exports", "Social templates", "Favicons"],
		},
		{
			kicker: "BRANDING",
			title: "Messaging basics",
			body:
				"Tone, headlines, and structure that makes your offering feel clear and premium.",
			bullets: ["Headlines", "Value props", "CTA clarity"],
		},
	],
	development: [
		{
			kicker: "DEVELOPMENT",
			title: "Vue websites",
			body:
				"Component-driven builds with clean structure and reusable UI patterns.",
			bullets: ["Vue 3", "Router", "Reusable components"],
		},
		{
			kicker: "DEVELOPMENT",
			title: "Performance",
			body:
				"Fast load, smooth interactions, and sensible bundling for real-world devices.",
			bullets: ["Lazy loading", "Image optimization", "Core Web Vitals"],
		},
		{
			kicker: "DEVELOPMENT",
			title: "Integrations",
			body:
				"Connect your site to tools you already use. Forms, email, CMS, analytics.",
			bullets: ["Forms", "Tracking", "APIs"],
		},
		{
			kicker: "DEVELOPMENT",
			title: "Deploy & support",
			body:
				"Launch with confidence. I can set up hosting and keep things healthy.",
			bullets: ["Deploy setup", "Monitoring", "Updates"],
		},
	],
};

const activeCards = computed(() => content[activeKey.value] ?? content.web);
</script>

<style scoped>
.services {
	padding: 8px 0 18px;
}

/* Title */
.services__header {
	display: flex;
	justify-content: center;
	margin: 8px 0 18px;
}

.services__title {
	margin: 0;
	font-weight: 900;
	letter-spacing: 0.04em;
	font-size: clamp(34px, 5vw, 56px);
	text-align: center;
}

.spark {
	opacity: 0.6;
	margin: 0 10px;
}

/* Layout: left menu + right grid */
.services__layout {
	display: grid;
	grid-template-columns: 360px 1fr;
	gap: 20px;
	align-items: stretch;
}

/* Left menu card */
.services-menu {
	padding: 24px;
	display: flex;
	flex-direction: column;
	gap: 14px;
	min-height: 520px;
}

.menu-item {
	display: grid;
	grid-template-columns: 42px 1fr;
	align-items: center;
	gap: 14px;

	width: 100%;
	border: 0;
	background: transparent;
	color: inherit;
	text-align: left;

	padding: 14px 12px;
	border-radius: 16px;
	cursor: pointer;
	transition: transform 180ms ease, background-color 180ms ease, opacity 180ms ease;
	opacity: 0.85;
}

.menu-item:hover {
	transform: translateY(-1px);
	opacity: 1;
	background: rgba(255, 255, 255, 0.04);
}

.menu-item.is-active {
	opacity: 1;
	background: rgba(255, 255, 255, 0.06);
}

.menu-item__icon {
	width: 34px;
	height: 34px;
	display: grid;
	place-items: center;
	opacity: 0.9;
}

.menu-item__icon svg {
	width: 22px;
	height: 22px;
}

.menu-item__label {
	font-size: 13px;
	letter-spacing: 0.08em;
	font-weight: 700;
}

/* Right cards */
.services-grid {
	display: grid;
	grid-template-columns: repeat(2, minmax(0, 1fr));
	gap: 20px;
}

.service-card {
	padding: 24px;
	min-height: 240px;
}

.service-card h6 {
	margin: 0 0 10px;
	opacity: 0.6;
	letter-spacing: 0.08em;
	text-transform: uppercase;
	font-weight: 600;
	font-size: 11px;
}

.service-card h3 {
	margin: 0 0 10px;
	font-size: 18px;
}

.service-card p {
	margin: 0 0 12px;
	opacity: 0.85;
	line-height: 1.55;
}

.bullets {
	margin: 0;
	padding-left: 18px;
	opacity: 0.85;
	line-height: 1.45;
}

/* Bottom row */
.services__bottom {
	margin-top: 20px;
	display: grid;
	grid-template-columns: 300px 1fr 300px;
	gap: 20px;
}

.bottom-card {
	padding: 22px;
	position: relative;
}

.bottom-card h6 {
	margin: 0 0 10px;
	opacity: 0.6;
	text-transform: uppercase;
	letter-spacing: 0.08em;
	font-size: 11px;
}

.bottom-card h3 {
	margin: 0 0 6px;
	font-size: 18px;
}

.bottom-card p {
	margin: 0;
	opacity: 0.75;
}

.arrow {
	position: absolute;
	right: 18px;
	bottom: 16px;
	opacity: 0.5;
}

.bottom-card--cta {
	display: flex;
	flex-direction: column;
	justify-content: center;
}

.cta-title {
	margin: 0 0 10px;
	font-size: 34px;
	line-height: 1.05;
}

.accent {
	color: #28517c;
}

.cta-sub {
	opacity: 0.75;
}

/* Responsive */
@media (max-width: 1100px) {
	.services__layout {
		grid-template-columns: 320px 1fr;
	}

	.services__bottom {
		grid-template-columns: 1fr;
	}
}

@media (max-width: 900px) {
	.services__layout {
		grid-template-columns: 1fr;
	}

	.services-menu {
		min-height: auto;
	}

	.services-grid {
		grid-template-columns: 1fr;
	}
}
</style>