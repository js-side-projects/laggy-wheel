<template>
	<div>
		<h1>Msg:</h1>
		<Hello />
		<p>Vuex (Global Data/state): {{ store.state }}</p>
		<p>Number (Local Data/state) {{ number }}</p>
		<button @click="update">Hello</button>
	</div>
</template>

<script>
	import { ref } from 'vue'
	import { useStore } from 'vuex'
	import Hello from '../components/Hello.vue'
	export default {
		components: {
			Hello,
		},
		setup() {
			const store = useStore()

			const number = ref(1)

			const update = () => {
				number.value = 2
			}

			return { Hello, number, store, update }
		},
	}
</script>
