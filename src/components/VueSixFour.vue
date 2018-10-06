<template>
	<input type="file" v-on:change="readFile"
	  v-bind:multiple="allowMultiple" />
</template>

<script>
function data() {
	return {
		multipleFiles: [],
	};
}

function readFile(e) {
	const files = e.target.files;
	const totalFiles = files.length;
	for (let index = 0; index < totalFiles; index += 1) {
		const file = files[index];
		let reader = new FileReader();
		reader.readAsDataURL(file);
		reader.addEventListener('load', () => {
			const result = Object.assign(file, { sixFour: reader.result });
			this.multipleFiles.push(result);
			if (totalFiles === this.multipleFiles.length) {
				this.$emit(
					'vue-six-four',
					this.allowMultiple ? this.multipleFiles : this.multipleFiles[0],
				);
				this.multipleFiles = [];
			}
			reader = null;
		});
	}
}

export default {
	data,
	name: 'vue-six-four',
	methods: {
		readFile,
	},
	props: {
		allowMultiple: {
			type: Boolean,
			default: false,
		},
	},
};
</script>
