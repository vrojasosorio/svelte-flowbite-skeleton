<script>
	import '../app.css';

	// Flowbite-Svelte components
	import {
		Navbar,
		NavBrand,
		NavLi,
		NavUl,
		NavHamburger,
		Avatar,
		Dropdown,
		DropdownItem,
		DropdownHeader,
		DropdownGroup,
		Footer,
		FooterCopyright,
		FooterLinkGroup,
		FooterLink,
		FooterBrand,
		FooterIcon
	} from 'flowbite-svelte';

	// Flowbite-Svelte-Icons
	import { FacebookSolid, GithubSolid, DiscordSolid, TwitterSolid } from 'flowbite-svelte-icons';

	let { children } = $props();
</script>

<Navbar>
	<NavBrand href="/">
		<img src="" class="me-3 h-6 sm:h-9" alt="" />
		<span class="self-center text-xl font-semibold whitespace-nowrap dark:text-white"></span>
	</NavBrand>
	<div class="flex items-center md:order-2">
		<Avatar id="avatar-menu" src="" />
		<NavHamburger />
	</div>
	<Dropdown placement="bottom" triggeredBy="#avatar-menu">
		<DropdownHeader>
			<span class="block text-sm">Bonnie Green</span>
			<span class="block truncate text-sm font-medium">name@flowbite.com</span>
		</DropdownHeader>
		<DropdownGroup class="cursor-pointer">
			<DropdownItem>Dashboard</DropdownItem>
			<DropdownItem>Settings</DropdownItem>
			<DropdownItem>Earnings</DropdownItem>
		</DropdownGroup>
		<DropdownHeader>Sign out</DropdownHeader>
	</Dropdown>
	<NavUl>
		<NavLi href="/">Home</NavLi>
		<NavLi href="/">About</NavLi>
		<NavLi href="/">Navbar</NavLi>
		<NavLi href="/">Pricing</NavLi>
		<NavLi href="/">Contact</NavLi>
	</NavUl>
</Navbar>

{@render children()}

<Footer footerType="socialmedia">
	<div class="sm:flex sm:items-center sm:justify-between">
		<FooterBrand href="" src="" alt="" name="" />
		<FooterLinkGroup
			class="mb-6 flex flex-wrap items-center text-sm text-gray-500 sm:mb-0 dark:text-gray-400"
		>
			<FooterLink href="/">About</FooterLink>
			<FooterLink href="/">Privacy Policy</FooterLink>
			<FooterLink href="/">Licensing</FooterLink>
			<FooterLink href="/">Contact</FooterLink>
		</FooterLinkGroup>
	</div>
	<hr class="my-6 border-gray-200 sm:mx-auto lg:my-8 dark:border-gray-700" />
	<div class="sm:flex sm:items-center sm:justify-between">
		<FooterCopyright href="/" by="Flowbite™" />
		<div class="mt-4 flex space-x-6 sm:mt-0 sm:justify-center rtl:space-x-reverse">
			<FooterIcon href="/">
				<FacebookSolid
					class="h-5 w-5 text-gray-500 hover:text-gray-900 dark:text-gray-500 dark:hover:text-white"
				/>
			</FooterIcon>
			<FooterIcon href="/">
				<DiscordSolid
					class="h-5 w-5 text-gray-500 hover:text-gray-900 dark:text-gray-500 dark:hover:text-white"
				/>
			</FooterIcon>
			<FooterIcon href="/">
				<TwitterSolid
					class="h-5 w-5 text-gray-500 hover:text-gray-900 dark:text-gray-500 dark:hover:text-white"
				/>
			</FooterIcon>
			<FooterIcon href="/">
				<GithubSolid
					class="h-5 w-5 text-gray-500 hover:text-gray-900 dark:text-gray-500 dark:hover:text-white"
				/>
			</FooterIcon>
		</div>
	</div>
</Footer>
