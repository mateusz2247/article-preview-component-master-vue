<template>
	<div class="articleImage"></div>

	<div class="articleText">
		<div class="content">
			<h1 class="articleHeader">
				Shift the overall look and feel by adding these wonderful touches to
				furniture in your home
			</h1>
			<p class="descryption">
				Ever been in a room and felt like something was missing? Perhaps it felt
				slightly bare and uninviting. I’ve got some simple tips to help you make
				any room feel complete.
			</p>
		</div>

		<div class="signatureAndShare">
			<img
				class="avatar"
				src="./images/avatar-michelle.jpg"
				alt="author avatar" />
			<div class="signatureDate">
				<p class="autorName">Michelle Appleton</p>
				<p class="date">28 Jun 2020</p>
			</div>
			<button
				@click="showShare"
				class="share"
				:class="{ shareActive: openShare }">
				<img
					class="arrow"
					:class="{ arrowActive: openShare }"
					src="./images/icon-share.svg"
					alt="share arrow" />
			</button>
		</div>
		<div class="sharingBox" :class="{ showSharingBox: openShare }">
			<p>share</p>
			<button
				class="facebookButton"
				@click="openInNewTab('https://www.facebook.com/')">
				<img src="./images/icon-facebook.svg" alt="facebook icon" />
			</button>
			<button
				class="pintrestButton"
				@click="openInNewTab('https://pl.pinterest.com/')">
				<img src="./images/icon-pinterest.svg" alt=" icon" />
			</button>
			<button
				class="twitterButton"
				@click="openInNewTab('https://twitter.com/?lang=pl')">
				<img src="./images/icon-twitter.svg" alt="facebook icon" />
			</button>
		</div>
	</div>
</template>

<script>
import { ref } from "vue";
export default {
	name: "articlePreview",
	setup() {
		let openShare = ref(false);

		function showShare() {
			openShare.value = !openShare.value;
		}
		function openInNewTab(url) {
			window.open(url, "_blank");
		}

		return { openShare, showShare, openInNewTab };
	},
};
</script>

<style>
@import url(./style.css);
@import url(./mobile.css);
</style>
