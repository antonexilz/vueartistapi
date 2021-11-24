<template>
	<div class="search-form">
		<form class="search-form__form" @submit.prevent="onFormSubmit">
			<input
				class="search-form__input"
				v-model="artist"
				type="text"
				placeholder="Type artist name"
				required
			/>
			<button class="search-form__button">Search</button>
		</form>
	</div>
</template>

<script>
	export default {
		emits: ['form-submit'],

		data() {
			return {
				artist: '',
			};
		},

		methods: {
			onFormSubmit() {
				this.$emit('form-submit', this.artist);
			},
		},
	};
</script>

<style lang="scss" scoped>
	.search-form {
		&__form {
			display: grid;
			grid-template-columns: 1fr auto;
			grid-gap: 1rem;
		}

		&__input {
			font-family: inherit;
			font-size: 1.6rem;
			color: #191c2b;
			display: block;
			width: 100%;
			height: 4rem;
			padding: 0.8rem 1.3rem;
			border: 0.1rem solid #ccc;
			border-radius: 0.6rem;
			background: none;
			outline: none;
			margin: 0;
		}

		&__button {
			font-family: inherit;
			font-size: 1.3rem;
			color: #191c2b;
			text-align: center;
			text-transform: uppercase;
			letter-spacing: 0.1rem;
			display: inline-flex;
			align-items: center;
			justify-content: center;
			min-width: 125px;
			min-height: 40px;
			padding: 5px 15px;
			border: 0.1rem solid #191c2b;
			border-radius: 0.6rem;
			background: none;
			outline: none;
			appearance: none;
			user-select: none;
			cursor: pointer;
			margin: 0;
		}
	}
</style>
