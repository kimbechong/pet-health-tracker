<template>
	<section class="section">
		<span class="icon-text">
			<img
				class="image is-32x32"
				src="../assets/images/notes-medical-solid.svg"
				alt="medical notes icon"
			/>
			<h2 class="title">New Symptom Entry</h2>
		</span>

		<div class="field">
			<label class="label">Date</label>
			<div class="control">
				<input class="input" type="date" v-model="date" />
			</div>
		</div>

		<div class="field">
			<label class="label">Time</label>
			<div class="control">
				<input class="input" type="time" v-model="time" />
			</div>
		</div>

		<div class="field">
			<label class="label">Symptom</label>
			<div class="control">
				<div class="select">
					<select v-model="selectedSymptom">
						<option
							v-for="symptom in symptomOptions"
							:key="symptom.key"
							:value="symptom.key"
						>
							{{ symptom.value }}
						</option>
					</select>
				</div>
			</div>
		</div>

		<div class="field" v-if="selectedSymptom === 'other'">
			<label class="label">Other</label>
			<div class="control">
				<input
					class="input"
					type="text"
					placeholder="Symptom"
					v-model="otherSymptom"
				/>
			</div>
		</div>

		<div class="field">
			<label class="label">Notes</label>
			<div class="control">
				<textarea
					class="textarea"
					placeholder="Notes"
					v-model="notes"
				></textarea>
			</div>
		</div>

		<div class="field is-grouped">
			<div class="control">
				<button class="button is-link" @click="submit">Submit</button>
			</div>
			<div class="control">
				<button class="button is-link is-light" @click="cancel">
					Cancel
				</button>
			</div>
		</div>
	</section>
</template>

<script>
export default {
	name: 'SymptomForm',
	data() {
		return {
			date: '',
			time: '',
			selectedSymptom: '',
			otherSymptom: '',
			notes: '',
			symptomOptions: [
				{
					key: 'fatigue',
					value: 'Fatigue',
				},
				{
					key: 'fever',
					value: 'Fever',
				},
				{
					key: 'diarrhea',
					value: 'Diarrhea',
				},
				{
					key: 'vomiting',
					value: 'Vomiting',
				},
				{
					key: 'cough',
					value: 'Cough',
				},
				{
					key: 'sneezing',
					value: 'Sneezing',
				},
				{
					key: 'itch',
					value: 'Itching',
				},
				{
					key: 'limp',
					value: 'Limping',
				},
				{
					key: 'appetite-change',
					value: 'Appetite Change',
				},
				{
					key: 'difficulty-breathing',
					value: 'Difficulty Breathing',
				},
				{
					key: 'blood-in-stool',
					value: 'Blood in Stool',
				},
				{
					key: 'seizures',
					value: 'Seizures',
				},
				{
					key: 'other',
					value: 'Other',
				},
			],
			symptomHistory: [],
		};
	},
	methods: {
		submit() {
			let symptom = '';
			if (this.selectedSymptom === 'other') {
				symptom = this.otherSymptom;
			} else {
				symptom = this.selectedSymptom;
			}
			let symptomEntry = {
				date: this.date,
				time: this.time,
				symptom: symptom,
				notes: this.notes,
			};
			this.symptomHistory.push(symptomEntry);
			this.symptomHistory.forEach((entry) => {
				console.log(entry);
			});
		},
		cancel() {
			console.log('cancel');
		},
	},
	watch: {
		selectedSymptom() {
			console.log(this.selectedSymptom);
		},
	},
};
</script>

<style scoped></style>
