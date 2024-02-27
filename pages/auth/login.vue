<template>
  <v-app id="inspire">
    <div class="image-bg"></div>
    <v-main class="d-flex justify-center align-center">
      <v-col cols="10" lg="4" md="6" xl="11" xxl="12" class="mx-auto">
        <v-card>
          <div class="text-center pa-5">
            <img src="./../../assets/img/logoemme.png" style="max-width: 150px;" />
            <v-card-title class="text-h6">
              Seja bem vindo ao 
              <br> Sistema de Gestão de Reboques de Viaturas
            </v-card-title>
          </div>
          <v-sheet max-width="400" class="mx-auto mb-0">
            <v-form fast-fail @submit.prevent="login">
              <v-card-text>
                <v-text-field
                  color="black-darken-4"
                  v-model="user.username"
                  label="Username"
                  prepend-inner-icon="mdi-account"
                ></v-text-field>

                <v-text-field
                  color="black-darken-4"
                  :type="showPassword ? 'text' : 'password'"
                  v-model="user.password"
                  prepend-inner-icon="mdi-lock"
                  :append-inner-icon="showPassword ? 'mdi-eye' : 'mdi-eye-off'"
                  @click:append-inner="showPassword = !showPassword"
                  label="Senha"
                ></v-text-field>

                <nuxt-link to="/homepage/dashboard">
                  <v-btn
                    block
                    class="mb-5 mt-1"
                    color="green-darken-2"
                    size="large"
                    variant="flat"
                    append-icon="mdi-login"
                  >
                    Entrar
                  </v-btn>
                </nuxt-link>

              </v-card-text>
            </v-form>
          </v-sheet>
          <p class="pt-0 text-center font-weight-light text-caption">
            Copyright 2024 - {{ new Date().getFullYear() }} &#169; <strong>EMME REBOQUE</strong><br>
            Desenvolvido por Vitae Consultaria e Serviços, Lda
          </p>
          <br>
        </v-card>
      </v-col>
    </v-main>
  </v-app>

  <v-dialog
    v-model="dialog"
    width="auto"
  >
    <v-card title="Erro!!!">
      <v-card-text>
        <v-alert
          color="red-darken-1"
          variant="outlined"
          type="error"
        >
          <template v-slot:title>
            Oops...
          </template>
        </v-alert>
      </v-card-text>

      <v-card-actions>
        <v-spacer></v-spacer>

        <v-btn
          text="ok"
          @click="dialog = false"
        ></v-btn>
      </v-card-actions>
    </v-card>
  </v-dialog>

</template>

<script setup>
import { ref } from 'vue';

let user = ref({
  username: '',
  password: '',
});

let showPassword = ref(false);
let dialog = ref(false);

const login = async () => {
  alert('Testando clique');
};
</script>

<style scoped>
.image-bg{
  background-image: url(./../../assets/img/logobgemme.png);
  height: 100%;
  width: 100%;
  display: block;
  position: absolute;
  top: 0px;
  background-size: cover;
}
</style>
