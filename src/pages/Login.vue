<template>
	<v-app>
		<v-container class="d-flex align-center justify-center" style="min-height: 100vh;">
			<v-card min-width="400" class="pa-5">
				<v-card-title class="text-h5">Login</v-card-title>
				<v-card-text>
					<v-form ref="form">
						<v-card-text class="pl-0">
							<v-text-field label="E-mail" v-model="email" :rules="emailRules" variant="outlined"
								required></v-text-field>
						</v-card-text>
						<v-card-text class="pl-0">
							<v-text-field type="password" v-model="senha" :rules="passwordRules" label="Senha"
								variant="outlined" required></v-text-field>
						</v-card-text>
						<v-container class="d-flex justify-space-between pl-0 pt-0">
							<router-link to="/forget-password">
								<v-btn color="red" class="mt-4">Esqueceu a senha</v-btn>
							</router-link>
							<router-link to="/home">
								<v-btn color="red" :disabled="!isValid" class="mt-4">Entrar</v-btn>
							</router-link>
						</v-container>
					</v-form>
				</v-card-text>
			</v-card>
		</v-container>
	</v-app>
</template>

<style></style>

<script setup lang="ts">
import { ref, watch } from 'vue'

const form = ref();
const email = ref('');
const senha = ref('');
const isValid = ref(false);

const emailRules = [
	(field: string) => !!field || 'O e-mail é um campo obrigatório',
	(field: string) => /^\w+([.-]?\w+)*@\w+([.-]?\w+)*(\.\w{2,3})+$/.test(field) || 'E-mail tem que ser um campo válido.'
];

const passwordRules = [
	(field: string) => !!field || 'A senha é um campo obrigatório',
];

watch([email, senha], async () => {
	const emailValid = emailRules.every(rule => rule(email.value) === true);
	const passwordValid = passwordRules.every(rule => rule(senha.value) === true);

	isValid.value = emailValid && passwordValid;
});

</script>