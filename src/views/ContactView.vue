<script setup>
import OnHoverButton from "@/components/OnHoverButton.vue";
// @ is an alias to /src
</script>

<template>
  <div class="h-100">
    <v-row justify="center">
      <v-spacer></v-spacer>
      <v-col cols="5">
        <v-card class="mt-16" variant="outlined" style="border-width: 0">
          <v-card-title>
            <v-row justify="start" no-gutters dense>
              <p class="title-text">CONTATO</p>
            </v-row>
          </v-card-title>
          <v-card-text>
            <p class="default-text">Me mande um email caso queira conversar</p>
            <v-row class="mt-10" no-gutters>
              <v-col cols="9">
                <p class="subtitle-text">Nome</p>
                <v-text-field
                  class="form-field"
                  density="compact"
                  variant="outlined"
                ></v-text-field>
                <p class="subtitle-text">Email</p>
                <v-text-field
                  class="form-field"
                  density="compact"
                  variant="outlined"
                ></v-text-field>
                <p class="subtitle-text">Mensagem</p>
                <v-textarea density="compact" variant="outlined"> </v-textarea>
              </v-col>
            </v-row>
          </v-card-text>
          <v-row justify="end">
            <v-spacer />
            <v-spacer />
            <OnHoverButton content="Enviar" />
            <v-spacer />
          </v-row>
          <v-card-actions>
            <v-row>
              <p class="subtitle-text mt-10 ml-10 text-center">
                Ou, se preferir, me mande uma mensagem no
                <a href="https://web.whatsapp.com/send?phone=5548998585899"
                  >WhatsApp!</a
                >
              </p>
            </v-row>
            <!-- <v-row>
              <p class="default-text">
                Se preferir, me mande uma mensagem pelo WhatsApp!
              </p>
            </v-row> -->
          </v-card-actions>
        </v-card>
      </v-col>
      <v-spacer></v-spacer>
    </v-row>
  </div>
</template>

<style></style>
