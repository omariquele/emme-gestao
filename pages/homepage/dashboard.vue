<template>
  <v-app>
    <v-navigation-drawer v-model="isDrawerOpen" class="custom-drawer">
      <!-- White background for the logo -->
      <div class="text-center my-0 logo-container">
        <img src="./../../assets/img/logoemme.png" alt="Logo" style="max-width: 120px;">
      </div>

      <v-list>
        <v-list-item prepend-icon="mdi-home" @click="updateTitle('Dashboard')" class="white--text" dense>
          Dashboard
        </v-list-item>

        <v-list-group>
          <template v-slot:activator="{ props }">
            <v-list-item
              v-bind="props"
              prepend-icon="mdi-tow-truck"
              @click="updateTitle('Geral')"
              dense
              class="white--text"
            >
              Geral
            </v-list-item>
          </template>
          <v-list-item prepend-icon="mdi-tow-truck" class="white--text" @click="updateTitle('Viaturas Apreendidas')" dense>Viaturas Apreendidas</v-list-item>
          <v-list-item prepend-icon="mdi-parking" class="white--text" @click="updateTitle('Viaturas Parqueadas')" dense>Viaturas Parqueadas</v-list-item>
          <v-list-item prepend-icon="mdi-currency-usd" class="white--text" @click="updateTitle('Pagamentos')" dense>Pagamentos</v-list-item>
          <v-list-item prepend-icon="mdi-history" class="white--text" @click="updateTitle('Histórico de Viaturas')" dense>Histórico de Viaturas</v-list-item>
          <v-list-item prepend-icon="mdi-message-processing" class="white--text" @click="updateTitle('Envio de SMS')" dense>Envio de SMS</v-list-item>
          <v-list-item prepend-icon="mdi-at" class="white--text" @click="updateTitle('Envio de Email')" dense>Envio de Email</v-list-item>
        </v-list-group>

        <v-list-group>
          <template v-slot:activator="{ props }">
            <v-list-item
              v-bind="props"
              @click="updateTitle('Configurações')"
              dense
              class="white--text"
              prepend-icon="mdi-cog-outline"
            >Configurações
            </v-list-item>
          </template>
          <v-list-item prepend-icon="mdi-cash-multiple" class="white--text" @click="updateTitle('Preçários')" dense>Preçários</v-list-item>
          <v-list-item prepend-icon="mdi-account" class="white--text" @click="updateTitle('Utilizadores')" dense>Utilizadores</v-list-item>
          <v-list-item prepend-icon="mdi-card-account-details" class="white--text" @click="updateTitle('Permissões')" dense>Permissões</v-list-item>
          <v-list-item prepend-icon="mdi-home-city" class="white--text" @click="updateTitle('Parques EMME')" dense>Parques EMME</v-list-item>
          <v-list-item prepend-icon="mdi-bell" class="white--text" @click="updateTitle('Notificações')" dense>Notificações</v-list-item>
          <v-list-item prepend-icon="mdi-police-badge" class="white--text" @click="updateTitle('Termos e Condições')" dense>Termos e Condições</v-list-item>
          <v-list-item prepend-icon="mdi-bank-plus" class="white--text" @click="updateTitle('Políticas de Privacidade')" dense>Políticas de Privacidade</v-list-item>
        </v-list-group>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar flat class="border-b" color="black">
      <v-app-bar-nav-icon @click="isDrawerOpen = !isDrawerOpen"></v-app-bar-nav-icon>
      <v-app-bar-title class="black-bg white--text">{{ pageTitle }}</v-app-bar-title>
    </v-app-bar>
  </v-app>
</template>

<script setup>
import { ref } from 'vue';

const isDrawerOpen = ref(false);
const pageTitle = ref('DASHBOARD');

const updateTitle = (title) => {
  pageTitle.value = title;
};
</script>

<style scoped>
.custom-drawer {
  background-color: black;
  width: 500px; /* Customize the width as needed */
}

.white--text {
  color: white !important; /* Ensure text color is white */
}

.logo-container {
  width: 300px; /* Custom width */
  height: 100px; /* Custom height */
  background-color: white;
  display: flex;
  justify-content: center;
  align-items: center;
  margin: 0 auto; /* Center the box horizontally */
}

.black-bg {
  background-color: black;
  color: white;
}
</style>
