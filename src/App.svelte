<script>

	import page from "page";
	import Super from './pages/Super'
	import Movie from './pages/Movie'
	import Fallback from './pages/Fallback'
	import Book from './pages/Book'

	let route = null
	let params = null

	page('/movie', () => route = Movie)
	page('/movie/:id', (ctx) => {params = ctx.params; route = Movie})
	page('/super', () => route = Super)
	page('/book', () => route = Book)
	page('/*', () => route = Fallback)
	page()

</script>

<a href="/movie/23">movie/id</a><br>
<a href="/super">super</a><br>
<a href="/sad">sad</a><br>
<a href="/book">book</a><br>

<svelte:component this={route} {params}/>
