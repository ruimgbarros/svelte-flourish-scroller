<script>
	import FlourishScroller from '../components/FlourishScroller.svelte';
	import NewsArticle from './NewsArticle.svelte';
	let steps = [
		'Hello! this is a step in the scroller.',
		'And you can add as many as you want.',
		'You only need to make sure you have enough Flourish slides to match',
		'Pretty cool, right?',
		'Oh, and did I mention you can also add pure HTML in the steps?',
		'Like this <a href="https://www.google.com">link</a>.'
	];
</script>

<FlourishScroller flourish_id="1568021" {steps} />

<NewsArticle />
