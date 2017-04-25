<template>
	<div>

		<div class="chip" :class="{cyan:cyan, 'red lighten-1': red}">
			<span v-if="numberPersos > 0"> {{numberPersos}} personnage<span v-if="numberPersos > 1">s</span></span>
			<span v-if="numberPersos === 0">Il n'y a aucun personnage</span>
		</div>

	</div>
</template>




<script>
	export default {
		props: ['numberPersos'],
		computed: {
			cyan: function () {
				return this.numberPersos >= 7
			},
			red: function () {
				return this.numberPersos < 3
			}
		}
	}

</script>

<style scoped>
	.chip {
		margin: 30px 0;
	}
</style>