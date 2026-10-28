<script>
	import NavbarDropdown from './NavbarDropdown.svelte';
	import NavbarDropdownMobile from './NavbarDropdownMobile.svelte';
	import NavbarLink from './NavbarLink.svelte';
	import Flag from '#lib/assets/flag-standalone.svg';

	let mobileMenuOpen = $state(false);

	const aboutOptions = [
		{
			link: 'https://hackclub.com/philosophy',
			title: 'Philosophy'
		},
		{
			link: 'https://hackclub.com/philanthropy',
			title: 'Philanthropy'
		},
		{
			link: 'https://hackclub.com/team',
			title: 'Team & Board'
		},
		{
			link: 'https://hackclub.com/jobs',
			title: 'Jobs'
		},
		{
			link: 'https://hackclub.com/brand',
			title: 'Branding Guide'
		},
		{
			link: 'https://hackclub.com/press',
			title: 'Press Inquiries'
		}
	];

	const resourcesOptions = [
		{ link: 'https://toolbox.hackclub.com/', title: 'Hacker Toolbox' },
		{ link: 'https://hackclub.com/conduct', title: 'Code of Conduct' },
		{
			link: 'https://hackclub.com/privacy-and-terms',
			title: 'Privacy & Terms'
		},
		{ link: 'https://hackclub.com/safety', title: 'Safety' }
	];
</script>

<nav class="flex h-20 flex-row items-center justify-between overflow-hidden pr-8 pl-8 lg:pr-16">
	<a href="https://hackclub.com/"> <img src={Flag} alt="" class="h-12" /></a>
	<div class="hidden flex-row items-center justify-around gap-6 lg:flex">
		<NavbarDropdown options={aboutOptions}>About</NavbarDropdown>
		<NavbarLink link="https://hackclub.com/programs">Programs</NavbarLink>
		<NavbarLink link="https://hackclub.com/clubs">Clubs</NavbarLink>
		<NavbarLink link="https://hackclub.com/hackathons">Hackathons</NavbarLink>
		<NavbarDropdown options={resourcesOptions}>Resources</NavbarDropdown>
		<NavbarLink link="https://hackclub.com/philanthropy">Donate</NavbarLink>
	</div>
	<button
		onclick={() => {
			mobileMenuOpen = !mobileMenuOpen;
		}}
		aria-label="mobile menu button"
		class="ml-auto flex h-10 w-10 transform-none cursor-pointer flex-col items-center justify-center gap-1.25 lg:hidden"
	>
		<span
			class="block h-0.75 w-6.5 bg-[#fff6eb] opacity-100 transition-all"
			class:translate-y-2={mobileMenuOpen}
			class:rotate-45={mobileMenuOpen}
		></span>
		<span
			class="block h-0.75 w-6.5 bg-[#fff6eb] opacity-100 transition-all"
			class:scale-0={mobileMenuOpen}
		></span>
		<span
			class="block h-0.75 w-6.5 bg-[#fff6eb] opacity-100 transition-all"
			class:-translate-y-2={mobileMenuOpen}
			class:-rotate-45={mobileMenuOpen}
		></span>
	</button>
</nav>
<div
	class="flex-col gap-3.5 bg-[#17171d] px-8 pt-4 pb-6"
	class:hidden={!mobileMenuOpen}
	class:flex={mobileMenuOpen}
>
	<NavbarDropdownMobile options={aboutOptions}>About</NavbarDropdownMobile>
	<a href="https://hackclub.com/programs" class="text-xl" target="_blank" rel="noopener noreferrer"
		>Programs</a
	>
	<a href="https://hackclub.com/clubs" class="text-xl" target="_blank" rel="noopener noreferrer"
		>Clubs</a
	>
	<a
		href="https://hackclub.com/fiscal-sponsorship"
		class="text-xl"
		target="_blank"
		rel="noopener noreferrer">HCB</a
	>
	<a
		href="https://hackathons.hackclub.com/"
		class="text-xl"
		target="_blank"
		rel="noopener noreferrer">Hackathons</a
	>
	<NavbarDropdownMobile options={resourcesOptions}>Resources</NavbarDropdownMobile>
	<a
		href="https://hackclub.com/philanthropy"
		class="text-xl"
		target="_blank"
		rel="noopener noreferrer">Donate</a
	>
</div>
