<template>
    <div class="container">
    	<appHeader :quoteCount="quotes.length" :maxQuotes="maxQuotes" ></appHeader>
    	<appNewQuote @quoteAdded="newQuote" ></appNewQuote>
		<appQuoteGird :quotes="quotes" @quoteDeleted="deleteQuote"></appQuoteGird> 
		<div class="row">
			<div class="col-sm-12 text-center">
				<div class="alert alert-info">
					Info: Click on a Quote to delete it.
				</div>
			</div>
		</div>
    </div>
</template>

<script>
	import QuoteGrid from './components/QuoteGrid.vue';
	import NewQuote from './components/NewQuote.vue';
	import Header from './components/Header.vue';
	export default {
		data: function() {
			return {
				quotes: [
					"Test Quote"
				],
				maxQuotes: 10
			}
		},
		methods: {
			newQuote(quote) {
				if ( this.quotes.length >= this.maxQuotes ) {
					return alert("Please delete Quotes first.");
				}
				this.quotes.push(quote);
			},
			deleteQuote(index) {
				this.quotes.splice(index, 1);
			}
		},
		components: {
			appQuoteGird: QuoteGrid,
			appNewQuote: NewQuote,
			appHeader: Header,
		}
	}
</script>

<style>
</style>
