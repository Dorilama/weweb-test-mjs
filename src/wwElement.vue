<template>
	<div class="my-element">
		<p :style="textStyle">I am a custom element !</p>
	</div>
</template>

<script>
import { useBluetooth } from "@vueuse/core";

useBluetooth();

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
};
</script>

<style lang="scss" scoped>
.my-element {
	p {
		font-size: 18px;
	}
}
</style>
