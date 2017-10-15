<template>
	<div id="app">
		<header>
			<h1>Vue SixFour Component</h1>
		</header>
		<main>
			<vue-six-four v-on:vue-six-four="getFileInfo"
			/>
			<div class="image-container">
				<img v-bind:src="file64.sixFour" width="200"
				  height="200" alt="Vue Six Four" />
				<div class="file-info">
					<pre>Name: {{file64.name}}</pre>
					<pre>Type: {{file64.type}}</pre>
					<pre>Size: {{file64.size}}</pre>
					<pre class="six-four">SixFour: {{file64.sixFour}}</pre>
				</div>
			</div>
		</main>
	</div>
</template>

<script>
import VueSixFour from './components/VueSixFour';

function getFileInfo(fileInfo) {
	this.file64 = fileInfo;
}

export default {
	name: 'app',
	components: {
		VueSixFour,
	},
	data() {
		return {
			file64: {},
		};
	},
	methods: {
		getFileInfo,
	},
};
</script>

<style lang="scss">
.image-container {
	display: flex;
	justify-content: center;
	.file-info {
		padding: 1%;
		.six-four {
			max-width: 50px;
		}
	}
}
</style>
