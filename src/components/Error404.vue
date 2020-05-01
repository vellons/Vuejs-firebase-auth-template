<template>
	<div id="error-404-container">
		<md-app md-waterfall md-mode="fixed" md-theme="default">
			<md-app-toolbar class="md-primary" md-elevation="5">
				<router-link class="router-link" to="/">
					<img class="bar-logo" src="../assets/logo.png" alt="Logo"/>
					<span class="md-title">Vue.js Dashboard with Firebase</span>
				</router-link>
			</md-app-toolbar>

			<md-app-content>
				<div class="middle-center">
					<img class="logo" src="../assets/logo.png" alt="Logo">
					<h1>Error 404</h1>
				</div>
			</md-app-content>
		</md-app>
	</div>
</template>

<script>
	export default {
		name: "Error404"
	}
</script>

<style lang="scss">
	#error-404-container {
		.md-app {
			height: 100vh;

			.router-link {
				display: flex;
				align-items: center;
			}

			.bar-logo {
				width: 35px !important;
			}

			.middle-center {
				position: absolute;
				top: 50%;
				left: 50%;
				width: 300px;
				transform: translate(-50%, -50%);
				-ms-transform: translate(-50%, -50%);
				text-align: center;
			}

			.logo {
				height: 200px;
				transform: rotate(60deg);
			}
		}
	}
</style>
