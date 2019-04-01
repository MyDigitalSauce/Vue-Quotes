<template>
	<div class="row">
		<form>
			<div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3">
				<div class="form-group">
					<label for="">Quote</label>
					<textarea required name="" id="" rows="3" class="form-control" v-model="quote"></textarea>
				</div>
				<div class="form-group">
					<button type="submit" class="btn btn-primary" @click.prevent="createNew" >Add Quote</button>
				</div>
			</div>
		</form>
	</div>
</template>

<script>
	import QuoteGrid from './QuoteGrid.vue';
	export default {
		data: function() {
			return {
				quote: ""
			};
		},
		methods: {
			createNew() {
				this.$emit( 'quoteAdded', this.quote );
				this.quote = "";
			}
		}
	}
</script>