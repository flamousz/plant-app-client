<script>
import { mapActions } from "pinia";
import { useUserStore } from "../stores/user";
import GreenButton from "../components/Buttons/GreenButton.vue";

export default {
	name: "LoginPage",
	data() {
		return {
			loginData: {
				email: "",
				password: "",
			},
		};
	},
	methods: {
		...mapActions(useUserStore, ["handleLogin"]),
	},
	components: { GreenButton },
};
</script>

<template>
	<div
		class="flex justify-center items-center bg-[url('../assets/homepage-wallpaper.jpg')] w-screen h-screen"
	>
		<div class="bg-[#c4e8c2] lg:w-[25%]  rounded-xl flex flex-col">
			<div
				class="bg-[#6bbd99] flex flex-col justify-center items-center lg:w-full rounded-t-xl py-4"
			>
				<img
					src="../assets/indo evergreen agro business.png"
					alt="indo evergreen agro business"
				/>
				<div class="pt-[3%] font-semibold text-2xl">
					<h1>Sign in to Plant App</h1>
				</div>
			</div>
			<div
				class="flex flex-col lg:w-full my-4  rounded-b-xl"
			>
				<form @submit.prevent="handleLogin(loginData)">
					<div class="flex flex-col px-6 pt-4 h-full w-[100%] gap-2 ">
						<div class="flex flex-row justify-between">
							<label
								for="email"
								class="flex justify-start items-center lg:w-[23%]"
								>Email:</label
							>
							<input
								class="placeholder:text-xs text-sm p-[6px] border border-gray-300 rounded-md  w-2/3"
								placeholder="Email Address"
								name="email"
								type="email"
								id="email"
								v-model="loginData.email"
							/>
						</div>
						<div class="flex flex-row justify-between">
							<label
								for="password"
								class="lg:w-[23%] flex justify-start items-center"
								>Password:
							</label>
							<input
								id="password"
								class="placeholder:text-xs p-[6px] border w-2/3 border-gray-300 rounded-md bg-green-100"
								placeholder="Password"
								name="password"
								type="password"
								v-model="loginData.password"
							/>
						</div>
						<div class="flex justify-end ">
							<GreenButton :type="'submit'" :text="'Click to Sign in'" />
						</div>
					</div>
				</form>
			</div>
		</div>
	</div>
</template>
