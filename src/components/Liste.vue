<template>
	<div>

		<div class="container">
			<div v-show="personnages.length <= 0">
				<preloader></preloader>
			</div>



			<div class="row">
				<chips :numberPersos="personnages.length"></chips>
				<collections v-for="perso in personnages" :perso="perso"> </collections>
			</div>

			<div class="row">
				<card @remove="removeList(perso)" :key="perso.id" v-for="perso in personnages" :currentPerso="perso"></card>
			</div>

			<div class="row" id="add-form">
				<addform @addPersonnage="addList($event)"></addform>
			</div>

		</div>
	</div>
</template>




<script>
	import Card from './Card.vue'
	import Preloader from './Preloader.vue'
	import Chips from './Chips.vue'
	import Collections from '@/components/Collections.vue'
	import Form from './Form.vue'

	export default {
		data: function () {
			return {
				personnages: []
			}
		},
		components: { card: Card, preloader: Preloader, chips: Chips, collections: Collections, addform: Form },
		created: function () {
			this.$http.get('https://raw.githubusercontent.com/Symfomany/angu/master/datas/got.json').then(response => {
				this.personnages = JSON.parse(response.body);
			}, response => {

			});
		},
		methods: {
			removeList: function (perso) {
				this.personnages.splice(this.personnages.indexOf(perso), 1);
			},
			addList: function (newPerso) {
				this.personnages.push(newPerso);
			}
		}
	}

</script>

<style></style>