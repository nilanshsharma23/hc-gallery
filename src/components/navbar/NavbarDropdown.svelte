<script>
	let { children, options } = $props();
</script>

<div class="group float-left overflow-hidden">
	<button
		class="gap flex cursor-pointer flex-row items-center transition-opacity duration-150 hover:opacity-60"
	>
		<div class="text-xl">{@render children?.()}</div>
		<svg
			fill-rule="evenodd"
			clip-rule="evenodd"
			stroke-linejoin="round"
			stroke-miterlimit="1.414"
			xmlns="http://www.w3.org/2000/svg"
			aria-label="down-caret"
			viewBox="0 0 32 32"
			preserveAspectRatio="xMidYMid meet"
			fill="currentColor"
			width="24"
			height="24"
			><path
				d="M 0.359841 9.01822C 0.784113 9.37178 1.41467 9.31446 1.76823 8.8902C 3.14518 7.2451 6.52975 3.42464 8.25002 2.11557C 9.99919 3.44663 13.335 7.21555 14.7318 8.8902C 15.0854 9.31446 15.7159 9.37178 16.1402 9.01822C 16.5645 8.66466 16.6215 8.03371 16.2679 7.60943C 14.7363 5.76983 11.2749 1.80977 9.30351 0.408618C 8.99227 0.190441 8.64018 0 8.25002 0C 7.85987 0 7.50778 0.190441 7.19654 0.408618C 5.26486 1.78153 1.73514 5.80788 0.232849 7.60856L 0.231804 7.60982C -0.12176 8.03409 -0.0644362 8.66466 0.359841 9.01822Z"
				transform="translate(7.12506 20.6251)scale(1 -1)"
			/></svg
		>
	</button>
	<div
		class="absolute z-1 hidden min-w-55 flex-col items-start justify-center gap-2 rounded-xl bg-[#1f1f27] p-2 text-xl shadow-md shadow-black group-hover:flex"
	>
		{#each options as option}
			<a
				href={option.link}
				target="_blank"
				rel="noopener noreferrer"
				class="float-none block w-full rounded-md py-2 pl-4 transition-all hover:bg-[#2a2a33] hover:pl-6 hover:text-[#ec3750]"
				>{option.title}</a
			>
		{/each}
	</div>
</div>
