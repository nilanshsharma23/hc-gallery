<script>
	let { children, link } = $props();
</script>

<a
	href={link}
	target="_blank"
	rel="noopener noreferrer"
	class="text-xl transition-opacity duration-150 hover:opacity-60">{@render children?.()}</a
>
