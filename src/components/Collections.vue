<template>
	<div class="col s1">
		<ul class="collection">
			<p>{{perso.prenom}} {{perso.nom}}</p>
			<li class="collection-item avatar">
				<i v-if="perso.sexe === false" class="material-icons circle cyan">rowing</i>
				<i v-else class="material-icons circle green">pool</i>
			</li>

		</ul>

	</div>
</template>


<script>
	export default {
		props: ['perso'],
	}

</script>

<style scoped>
	.collection {
		margin: auto;
	}
</style>