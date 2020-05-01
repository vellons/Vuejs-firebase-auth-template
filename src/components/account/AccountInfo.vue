<template>
	<div id="account-info-container">
		<div v-if="!loading" class="center">
			<p><b>Email:</b> {{email}}</p>
			<p>
				<router-link to="/">Home page</router-link>
			</p>
			<md-button class="md-raised md-primary" @click="logout">Logout</md-button>
		</div>
	</div>
</template>

<script>
	import {FirebaseAuth} from "@/firebase";

	export default {
		name: "AccountInfo",
		data() {
			return {
				loading: true,
				email: "",
			}
		},
		mounted() {
			let _this = this;
			FirebaseAuth.onAuthStateChanged((user) => {
				if (user) {
					_this.email = user.email;
					_this.loading = false;
				} else this.$router.replace('/account/login'); // User not logged
			});
		},
		methods: {
			logout: function () {
				this.loading = true;
				FirebaseAuth.signOut().then(() => {
					// Automatic redirect to login (onAuthStateChanged)
				}).catch((error) => {
					console.error("logout()", error);
				});
			}
		}
	}
</script>

<style lang="scss">
	#account-info-container {
		.center {
			text-align: center;
		}
	}
</style>
