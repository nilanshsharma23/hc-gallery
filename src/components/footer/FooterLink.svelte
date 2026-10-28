<script>
	let { link, title } = $props();
</script>

<li>
	<a
		href={link}
		target="_blank"
		rel="noopener noreferrer"
		class="inline-block text-base font-medium opacity-80 transition-opacity duration-150 hover:opacity-100"
		>{title}</a
	>
</li>
