<template>
	<div>

		<form class="col s12">
			<h4>Add a character</h4>
			<div class="row">
				<div class="input-field col s6">
					<input id="nom" type="text" class="validate" v-model=newPerso.nom>
					<label for="nom">First name</label>
				</div>

				<div class="input-field col s6">
					<input id="prenom" type="text" class="validate" v-model=newPerso.prenom>
					<label for="prenom">Last name</label>
				</div>

			</div>
			<div class="row">
				<div class="input-field col s6">
					<input id="ville" type="text" class="validate" v-model=newPerso.ville>
					<label for="ville">City</label>
				</div>


				<form action="#">
					<p>
						<input name="group1" type="radio" id="femme" v-model="newPerso.sexe" :value="false" />
						<label for="femme">Woman</label>
					</p>
					<p>
						<input name="group1" type="radio" id="homme" v-model="newPerso.sexe" :value="true" />
						<label for="homme">Man</label>
					</p>
				</form>
			</div>

			<div class="row">
				<div class="input-field col s6">
					<input id="ville" type="text" class="validate" v-model=newPerso.photo>
					<label for="ville">Photo</label>
				</div>
			</div>






			<div class="row">

				<div class="input-field col s12">
					<textarea id="textarea1" class="materialize-textarea" data-length="120" v-model=newPerso.biographie></textarea>
					<label for="textarea1">Biography</label>
				</div>
			</div>
			<a class="waves-effect waves-light btn" @click="add"><i class="material-icons left">add</i>Add a character</a>

		</form>
	</div>
</template>



<script>
	export default {
		name: 'form',
		data: function () {
			return {
				newPerso: {
					nom: '',
					prenom: '',
					ville: '',
					sexe: true,
					biographie: '',
					photo: ''
				}
			}
		},
		methods: {
			add() {
				this.$emit('addPersonnage', this.newPerso);
				this.newPerso = {};
			}
		}
	}

</script>


<style scoped>
	form {
		margin: 40px auto;
	}
</style>