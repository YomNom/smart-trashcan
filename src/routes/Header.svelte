<script>
	import { page } from '$app/stores';
	import { UserSolid } from 'flowbite-svelte-icons';
	import { Navbar, NavBrand, NavLi, NavUl, NavHamburger, Button, Modal, Popover } from 'flowbite-svelte';
	let username = "Jane Doe"
	let profileModal = false;
</script>

<header>
	<Navbar let:NavContainer color="primary">
		<NavContainer class="border px-5 py-2 rounded-lg bg-white dark:bg-gray-600">
		  <NavBrand href="/">
			<span class="self-center whitespace-nowrap text-xl font-semibold" color="#0136BA" >Checklist</span>
		  </NavBrand>
		  <NavHamburger />
		  
		<Button id="userPopover" pill={true} outline={true} class="!p-2" size="xs"><UserSolid class="w-6 h-6 text-primary-700" /></Button>
		<Popover class="w-64 text-sm font-light " title="Hi {username}!" triggeredBy="#userPopover">
			<p>Joined September 3, 2024</p>
			<p>Today September 23, 2024</p>
		</Popover>
		</NavContainer>
	  </Navbar>
</header>

<style>
	header {
		display: flex;
		justify-content: space-between;
	}

	.corner {
		width: 3em;
		height: 3em;
	}

	.corner a {
		display: flex;
		align-items: center;
		justify-content: center;
		width: 100%;
		height: 100%;
	}

	.corner img {
		width: 2em;
		height: 2em;
		object-fit: contain;
	}

	nav {
		display: flex;
		justify-content: center;
		--background: rgba(255, 255, 255, 0.7);
	}

	svg {
		width: 2em;
		height: 3em;
		display: block;
	}

	path {
		fill: var(--background);
	}

	ul {
		position: relative;
		padding: 0;
		margin: 0;
		height: 3em;
		display: flex;
		justify-content: center;
		align-items: center;
		list-style: none;
		background: var(--background);
		background-size: contain;
	}

	li {
		position: relative;
		height: 100%;
	}

	li[aria-current='page']::before {
		--size: 6px;
		content: '';
		width: 0;
		height: 0;
		position: absolute;
		top: 0;
		left: calc(50% - var(--size));
		border: var(--size) solid transparent;
		border-top: var(--size) solid var(--color-theme-1);
	}

	nav a {
		display: flex;
		height: 100%;
		align-items: center;
		padding: 0 0.5rem;
		color: var(--color-text);
		font-weight: 700;
		font-size: 0.8rem;
		text-transform: uppercase;
		letter-spacing: 0.1em;
		text-decoration: none;
		transition: color 0.2s linear;
	}

	a:hover {
		color: var(--color-theme-1);
	}
</style>