<script>
	export let segment
</script>

<style>
	a {
		border-bottom: 1px solid white;
	}

 .is-active {
	 border-bottom: 1px solid black;
 }
</style>

<nav class="navbar">
  <div class="navbar-brand">
    <a class="navbar-item" class:is-active={segment === undefined} href=".">
			home
		</a>
		<a class="navbar-item" class:is-active={segment === 'yearSelect'} href="yearSelect">
			Year Selection
		</a>
		<a class="navbar-item" class:is-active={segment === 'twelveChoices'} href="twelveChoices">
			Year Twelve Selection
		</a>
		<a class="navbar-item" class:is-active={segment === 'output'} href="output">
			username test
		</a>
		<a class="navbar-item" class:is-active={segment === 'thirteenChoices'} href="thirteenChoices">
			Year Thirteen Selection
		</a>
  </div>
</nav>