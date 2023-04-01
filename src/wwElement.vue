<template>
	<div class="my-element">
		<p :style="textStyle">I am a custom element !</p>
		<button @click="test">click me</button>
	</div>
</template>

<script>
import { useDebounceFn } from "@vueuse/core";

export default {
	props: {
		content: { type: Object, required: true },
	},
	computed: {
		textStyle() {
			return {
				color: this.content.textColor,
			};
		},
	},
	methods: {
		test: useDebounceFn(() => {
			console.log("clicked");
		}, 2000),
	},
};
</script>

<style lang="scss" scoped>
.my-element {
	p {
		font-size: 18px;
	}
}
button {
	padding: 15px;
	border: 1px black solid;
}
button:active {
	background: chartreuse;
}
</style>
