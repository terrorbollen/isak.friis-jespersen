<script lang="ts">
	import { Menu } from 'lucide-svelte';
	import LinkedIn from '$lib/logos/LinkedIn.svelte';
	import Github from '$lib/logos/Github.svelte';
	import { scrollIntoView } from '$lib/utils/scrollTo';

	let isOpen = false;
</script>

<navbar class="fixed w-full bg-[#18262b] border-b border-black z-10 text-cyan-50">
	<div class="flex justify-between p-5 w-full desktop:text-md">
		<div class="flex items-start space-x-3 tablet:space-x-4">
			<button type="button" on:click={() => scrollIntoView('#about')} class="hover:text-orange-600">About</button>
			<button type="button" on:click={() => scrollIntoView('#projects')} class="hover:text-orange-600">Projects</button>
			<button type="button" on:click={() => scrollIntoView('#experience')} class="hover:text-orange-600"
				>Experience</button
			>
			<button type="button" on:click={() => scrollIntoView('#skills')} class="hover:text-orange-600">Skills</button>
			<!-- <button type="button" on:click={() => scrollIntoView('#contact')} class="hover:text-orange-600">Contact</button> -->
		</div>
		<div class="space-y-2 tablet:space-y-0 flex flex-col items-end">
			<button on:click={() => (isOpen = !isOpen)}>
				<Menu
					role="button"
					class="tablet:hidden border rounded-md w-6 h-6 tablet:w-12 tablet:h-12 desktop:h-8 desktop:w-8 p-1"
				/>
			</button>
			<div
				class="flex flex-col tablet:flex-row space-y-2 tablet:space-x-4 tablet:space-y-0 tablet:data-[hidden=false]:flex data-[hidden=false]:hidden"
				data-hidden={isOpen}
			>
				<a href="https://github.com/IsakFriisJespersen2" target="”_blank”" class="flex items-center"
					><Github className="w-5 h-5 fill-orange-600 mr-1" />Github</a
				>
				<a
					href="https://www.linkedin.com/in/isak-friis-jespersen-9abb4915a/"
					target="”_blank”"
					class="flex items-center"><LinkedIn className="w-4 h-4 fill-orange-600 mr-1" />Linkedin</a
				>
			</div>
		</div>
	</div>
</navbar>
