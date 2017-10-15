<template>
	<input type="file" v-on:change="readFile"
	/>
</template>

<script>

function data() {
	return {
		fr: null,
	};
}

function destroyed() {
	if (this.fr) {
		this.fr.removeEventListener('load');
	}
}

function getSixFourData(file) {
	const newFile = Object.assign(file, { sixFour: this.fr.result });
	this.$emit('vue-six-four', newFile);
}

function readFile(e) {
	const file = e.target.files[0];
	if (file) {
		this.fr = new FileReader();
		this.fr.addEventListener('load', getSixFourData.bind(this, file));
		this.fr.readAsDataURL(file);
	}
}

export default {
	data,
	name: 'vue-six-four',
	destroyed,
	methods: {
		readFile,
	},
};
</script>
