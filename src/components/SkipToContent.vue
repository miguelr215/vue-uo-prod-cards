<script setup>
import { ref } from 'vue';

const hidden = ref(true);

function toggleHidden() {
	hidden.value = !hidden.value;
}
</script>

<template>
	<a
		class="visually-hidden-focusable"
		href="#content"
		:aria-hidden="hidden"
		aria-live="off"
		@focus="toggleHidden"
		>Skip to main content</a
	>
</template>

<style scoped></style>
