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
				<input class="input" type="date" />
			</div>
		</div>
		<div class="field">
			<label class="label">Time</label>
			<div class="control">
				<input class="input" type="time" />
			</div>
		</div>
        <!-- create dynamic v-for from list -->
        <div class="field">
            <label class="label">Symptom Select</label>
            <div class="control">
                <div class="select">
                    <select>
                        <option>Vomiting</option>
                        <option>Other</option>
                    </select>
                </div>
            </div>
        </div>
		<div class="field">
			<label class="label">Symptom</label>
			<div class="control">
				<input
					class="input"
					type="text"
					placeholder="Vomiting, fever, itch, sneezing, cough, etc."
				/>
			</div>
		</div>
		<div class="field">
			<label class="label">Notes</label>
			<div class="control">
				<textarea class="textarea" placeholder="Textarea"></textarea>
			</div>
		</div>
		<div class="field is-grouped">
			<div class="control">
				<button class="button is-link">Submit</button>
			</div>
			<div class="control">
				<button class="button is-link is-light">Cancel</button>
			</div>
		</div>
	</section>
</template>

<script>
export default {
	name: 'SymptomForm',
};
</script>

<style scoped></style>
