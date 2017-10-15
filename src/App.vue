<template>
	<div id="app">
		<header>
			<h1>Vue SixFour Component</h1>
		</header>
		<main>
			<div class="example">
				<header>
					<h2>Single File</h2>
				</header>
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
			</div>
			<div class="example">
				<header>
					<h2>Multiple File</h2>
				</header>
				<vue-six-four v-on:vue-six-four="getFiles"
				  v-bind:allow-multiple="true" />
				<div class="image-container" v-for="image in images"
				  v-bind:key="image.name">
					<img v-bind:src="image.sixFour" width="200"
					  height="200" alt="Vue Six Four" />
					<div class="file-info">
						<pre>Name: {{image.name}}</pre>
						<pre>Type: {{image.type}}</pre>
						<pre>Size: {{image.size}}</pre>
						<pre class="six-four">SixFour: {{image.sixFour}}</pre>
					</div>
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

function getFiles(files) {
	this.images = files;
}

export default {
	name: 'app',
	components: {
		VueSixFour,
	},
	data() {
		return {
			file64: {},
			images: [],
		};
	},
	methods: {
		getFileInfo,
		getFiles,
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
