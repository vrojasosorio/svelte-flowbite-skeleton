<script>
	// UI Components
	import {
		Carousel,
		Controls,
		Indicators,
		CardPlaceholder,
		TestimonialPlaceholder,
		VideoPlaceholder,
		Heading,
		P,
		Button,
		Drawer,
		CloseButton,
		Label,
		Input,
		Textarea,
		A
	} from 'flowbite-svelte';

	// Icons
	import { InfoCircleSolid } from 'flowbite-svelte-icons';

	let hidden = $state(true);

	// Image data for carousel
	const images = [
		{
			alt: 'Mountain landscape with sunset view',
			src: '/img.png'
		},
		{
			alt: 'Mountain landscape with sunset view',
			src: '/img.png'
		},
		{
			alt: 'Mountain landscape with sunset view',
			src: '/img.png'
		}
	];

	let image;
</script>

<div class="container mx-auto space-y-12 p-4">
	<div class="text-center">
		<Heading tag="h1" class="mb-4 text-4xl font-extrabold md:text-5xl lg:text-6xl"
			>Building a digital vision
		</Heading>
		<P class="mb-6 text-lg sm:px-16 lg:text-xl xl:px-48 dark:text-gray-400"
			>I focus on projects where technology, creativity, and smart planning can create lasting value
			and drive innovative solutions for tomorrow's challenges.</P
		>
		<Button onclick={() => (hidden = false)}>Contact Us</Button>
	</div>
	<div class="space-y-4">
		<Carousel {images} onchange={(detail) => (image = detail)}>
			<Controls />
			<Indicators />
		</Carousel>
	</div>
	<div class="flex justify-between">
		<CardPlaceholder />
		<CardPlaceholder />
		<CardPlaceholder />
	</div>
	<div class="grid md:grid-cols-2">
		<VideoPlaceholder size="md" />
		<div class="my-auto flex flex-col space-y-4 md:space-y-6">
			<TestimonialPlaceholder />
			<TestimonialPlaceholder />
		</div>
	</div>
</div>

<Drawer backdropClass="bg-gray-900/70" bind:hidden>
	<div class="flex items-center justify-between">
		<h5
			id="drawer-label"
			class="mb-6 inline-flex items-center text-base font-semibold text-gray-500 uppercase dark:text-gray-400"
		>
			<InfoCircleSolid class="me-2.5 h-5 w-5" />
			Contact us
		</h5>
		<CloseButton onclick={() => (hidden = true)} class="mb-4 dark:text-white" />
	</div>
	<form action="#" class="mb-6">
		<div class="mb-6">
			<Label for="email" class="mb-2 block">Your email</Label>
			<Input id="email" name="email" required placeholder="name@company.com" />
		</div>
		<div class="mb-6">
			<Label for="subject" class="mb-2 block">Subject</Label>
			<Input id="subject" name="subject" required placeholder="Let us know how we can help you" />
		</div>
		<div class="mb-6">
			<Label for="message" class="mb-2">Your message</Label>
			<Textarea id="message" placeholder="Your message..." rows={4} name="message" />
		</div>
		<Button type="submit" class="w-full">Send message</Button>
	</form>
	<P class="mb-2 text-sm text-gray-500 dark:text-gray-400">
		<A href="/" class="text-primary-600 dark:text-primary-500 hover:underline">info@company.com</A>
	</P>
	<P class="text-sm text-gray-500 dark:text-gray-400">
		<A href="/" class="text-primary-600 dark:text-primary-500 hover:underline">212-456-7890</A>
	</P>
</Drawer>
