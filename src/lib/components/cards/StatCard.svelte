<script lang="ts">
	export let color: 'primary' | 'secondary' | 'tertiary' | 'orange';

	const bgGradients = {
		primary: 'to-primary/10 dark:to-primary/10 text-primary',
		secondary: 'to-secondary/10 dark:to-secondary/10 text-secondary',
		tertiary: 'to-tertiary/10 dark:to-tertiary/10 text-tertiary',
		orange: 'to-orange/10 dark:to-orange/10 text-orange'
	};
</script>

<div
	class="p-[25px] rounded-lg bg-gradient-to-br from-secondary-bg-light dark:from-secondary-bg-dark {bgGradients[
		color
	]}">
	<h3 class="text-[32px] md:text-[36px]">
		<slot name="stat" />
	</h3>
	<h4 class="text-[20px] mb-3">
		<slot name="subtitle" />
	</h4>
	<p class="text-body-text dark:text-body-text">
		<slot name="body" />
	</p>
</div>
