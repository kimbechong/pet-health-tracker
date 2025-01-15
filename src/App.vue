<template>
	<head>
		<meta charset="utf-8" />
		<meta name="viewport" content="width=device-width, initial-scale=1" />
		<title>Pet Health Tracker</title>
	</head>
	<body>
        <SymptomForm />
	</body>
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

<style scoped>
@import 'https://cdn.jsdelivr.net/npm/bulma@1.0.2/css/bulma.min.css';
</style>
