<script lang="ts">
	import Accordion from '$lib/components/Accordion.svelte';
	import ServicesMenu from '$lib/components/layout/navigation/menus/ServicesMenu.svelte';
	import ResourcesMenu from '$lib/components/layout/navigation/menus/ResourcesMenu.svelte';
	import AboutMenu from '$lib/components/layout/navigation/menus/AboutMenu.svelte';
	export let open: boolean;
	const handleMobileNav = () => (open = !open);
</script>

<aside
	class="fixed top-[100px] pt-10 pb-[200px] z-10 w-full h-screen bg-body-color-light dark:bg-body-color-dark text-body-text dark:text-body-text overflow-y-scroll"
	class:open>
	<nav class="px-8 text-xl">
		<div class="bg-body-color-light dark:bg-body-color-dark">
			<Accordion bodyClasses="px-0">
				<span slot="question">Services</span>
				<div slot="answer">
					<ServicesMenu on:click={handleMobileNav} />
				</div>
			</Accordion>
			<Accordion bodyClasses="px-0">
				<span slot="question">Resources</span>
				<div slot="answer">
					<ResourcesMenu on:click={handleMobileNav} />
				</div>
			</Accordion>
			<Accordion bodyClasses="px-0">
				<span slot="question">About</span>
				<div slot="answer">
					<AboutMenu on:click={handleMobileNav} />
				</div>
			</Accordion>
		</div>
	</nav>
</aside>

<style>
	aside {
		right: -100%;
		transition: right 0.3s ease-in-out;
	}

	.open {
		right: 0;
	}
</style>
