<script>
	var cookies = getCookies()

	function getCookies() {
		var amount;
		var stored = localStorage.getItem('cookies')

		if (stored === null) {
			localStorage.setItem('cookies', 0)
			amount = 0
		} else {
			amount = stored
		}

		return parseInt(amount)
	}

	function setCookies(amount) {
		localStorage.setItem('cookies', parseInt(amount))
	}

	function addCookies(amount) {
		setCookies(getCookies() + amount)
		cookies = getCookies()
	}

	function removeCookies(amount) {
		setCookies(getCookies() - amount)
		cookies = getCookies()
	}
</script>

<div class="flex justify-center items-center h-screen text-center">
	<button on:click={() => {addCookies(1)}} class="pr-20">
		<img src="cookie.png" alt="Cookie">
	</button>
	<h1 class="text-6xl text-white">{cookies} Cookies</h1>
</div>