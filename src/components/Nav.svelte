<script>
	export let segment;
</script>

<style>
	nav {
		display: flex;
		justify-content: space-between;
		border-bottom: 1px solid rgba(255,62,0,0.1);
		font-weight: 300;
		padding: 0 1em;
		background: var(--color-second);
	}

	ul {
		margin: 0;
		padding: 0;
	}

	/* clearfix */
	ul::after {
		content: '';
		display: block;
		clear: both;
	}

	li {
		display: block;
		float: left;
	}

	.nyrst:focus, .nyrst:hover,
	[aria-current] {
		position: relative;
		display: inline-block;
	}

	.nyrst:focus::after, .nyrst:hover::after,
	[aria-current]::after {
		position: absolute;
		content: '';
		width: calc(100% - 1em);
		height: 2px;
		background-color: var(--color-main);
		display: block;
		bottom: -1px;
	}

	a {
		text-decoration: none;
		padding: 1em 0.5em;
		display: block;
	}
</style>

<nav>
	<ul>
		<li><a aria-current="{segment === undefined ? 'page' : undefined}" href=".">nyrst.tools</a></li>
		<li><a aria-current="{segment === 'brrr' ? 'page' : undefined}" href="brrr">🔧 brrr</a></li>
		<li><a aria-current="{segment === 'freezer' ? 'page' : undefined}" href="freezer">❄️ freezer</a></li>
		<li><a aria-current="{segment === 'apps' ? 'page' : undefined}" href="apps">📝 apps</a></li>

		<!-- for the blog link, we're using rel=prefetch so that Sapper prefetches
		     the blog data when we hover over the link or tap it on a touchscreen -->
		<!-- <li><a rel=prefetch aria-current="{segment === 'blog' ? 'page' : undefined}" href="blog">blog</a></li> -->
	</ul>

	<a class="nyrst" href="https://github.com/nyrst/">⌨️</a>
</nav>
