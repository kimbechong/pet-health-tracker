<template>
	<section class="section">
		<h1 class="title">Pet Health Tracker</h1>
        <p class="subtitle is-4">Data-driven pet healthcare</p>
	</section>
	<SymptomForm />
</template>

<script>
import SymptomForm from './components/SymptomForm.vue';

export default {
	name: 'App',
	components: {
		SymptomForm,
	},
};
</script>

<style scoped></style>
