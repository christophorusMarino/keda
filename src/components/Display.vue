<template>
	<div>
		<Navbar2 />
		<br>
		<div class="container">
			<div class="row mt-5">
				<RadioButton
					id="yesNoQuestion"
					v-model="fields.radio_button"
					:options="radio_button_options"
					label="Radio Button"
				>
					<template #textField>
						<br>
						<label for="textField">Input Text : </label>
						<input
							type="text"
							id="textField"
							name="textField"
							v-model="fields.text_field"
							placeholder="Hey!"
						/>
					</template>

					<template #dateField>
						<br>
						<label for="dateField">Input Date : </label>
						<input
							type="date"
							id="dateField"
							name="dateField"
							v-model="fields.date_field"
						/>
					</template>

					<template #form>
						<br>
						<form @submit="submit">
							<label>Name : </label>
							<input type="text" name="name" placeholder="Name..." />
							<br>
							<label>Address : </label>
							<textarea name="address" placeholder="Address..."></textarea>
							<br>
							<label>Country : </label>
							<input type="text" name="country" value="Indonesia" disabled />
						</form>
					</template>
				</RadioButton>
			</div>
		</div>
	</div>
</template>

<script>
	import RadioButton from '@/components/RadioButton.vue'
	
	export default{
		components: {
			RadioButton
		},

		data(){
			return{
				fields: {
					radio_button: null,
					text_field: "",
					date_field: ""
				},
				radio_button_options: [
					{
						value: "textField",
						text: "Radio Button A",
					},
					{
						value: "dateField",
						text: "Radio Button B",
					},
					{
						value: "form",
						text: "Radio Button C"
					}
				]
			}
		}
	}
</script>