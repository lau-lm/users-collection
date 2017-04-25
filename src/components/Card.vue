<template>
	<div>


		<div class="col s4">
			<div class="card">
				<div class="card-image">
					<img :src="currentPerso.photo">


					<span class="card-title">{{currentPerso.prenom}} {{currentPerso.nom}}</span>
					<a class="btn-floating halfway-fab waves-effect waves-light red"><i class="material-icons">add</i></a>
					<a @click="removePerso(perso)" class="btn-floating halfway-fab waves-effect waves-light red"><i class="material-icons">delete</i></a>
				</div>
				<div class="card-content" :class="{amber: isBaratheon}">
					<p>{{currentPerso.biographie}}</p>
				</div>
				<div class="card-action">
					<a href="#">Age : {{currentPerso.age}}</a>
					<a href="#">{{currentPerso.sexe | sexe}}</a>
				</div>
			</div>
		</div>


	</div>
</template>


<script>
	export default {
		props: ['currentPerso'],
		filters: {
			sexe: function (persoSexe) {
				if (persoSexe === false) {
					return "Femme"
				} else {
					return "Homme"
				}
			}
		},
		computed: {
			isBaratheon: function () {
				return /baratheon/gi.test(this.currentPerso.nom)
			}
		},
		methods: {
			removePerso: function () {
				// j'emets un événement parent qui s'appelle 'remove'
				this.$emit('remove');
			}
		}


	}

</script>


<style scoped>

</style>