<script>
	import { page } from "$app/stores";
</script>

<header>
	<nav>
		<ul>
			<li aria-current={$page.url.pathname === "/" ? "page" : undefined}>
				<a href="/">Accueil</a>
			</li>
			<li
				aria-current={$page.url.pathname === "/about"
					? "page"
					: undefined}
			>
				<a href="/about">à-propos</a>
			</li>	
			<li
				aria-current={$page.url.pathname.startsWith("/liste-des-clubs")
					? "page"
					: undefined}
			>
				<a href="/liste-des-clubs">Liste des clubs</a>
			</li>
			<li
			aria-current={$page.url.pathname.startsWith("/acheter-une-licence")
				? "page"
				: undefined}
		>
			<a href="/acheter-une-licence">acheter une licence</a>
		</li>
		</ul>
	</nav>

</header>

<style>
	header {
		display: flex;
		width: 100%;
		justify-content: center;
		background-size: 100%;
		background-size: cover;
	}

	nav {
		display: flex;
		justify-content: center;
	}

	ul {
		gap: 3.5em;
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

	li[aria-current="page"]::before {
		font-weight: bold;
		--size: 11px;
		content: "";
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
