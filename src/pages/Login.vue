<template>
	<v-app>
		<v-container class="d-flex align-center justify-center" style="min-height: 100vh;">
			<v-card min-width="400" class="pa-5">
				<v-card-title class="text-h5">Login</v-card-title>
				<v-card-text>
					<v-form>
						<v-card-text class="pl-0">
							<v-text-field label="E-mail" variant="outlined" required></v-text-field>
						</v-card-text>
						<v-card-text class="pl-0">
							<v-text-field type="password" label="Senha" variant="outlined" required></v-text-field>
						</v-card-text>
						<v-container class="d-flex justify-space-between pl-0 pt-0">
							<v-btn color="red" class="mt-4">Esqueceu a senha</v-btn>
							<v-btn color="red" class="mt-4" @click="testea">Enviar</v-btn>
						</v-container>
					</v-form>
				</v-card-text>
			</v-card>
		</v-container>
	</v-app>
</template>

<style></style>

<script setup lang="ts">
function testea() {
	console.log('Ui');
}
</script>