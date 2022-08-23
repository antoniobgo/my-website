<script setup>
import { ref } from "vue";
import OnHoverButton from "@/components/OnHoverButton.vue";
import router from "../router/index.js";
import axios from "axios";

const emailInfos = ref({});
const isLoading = ref(false);
const showErrorMessage = ref(false);
const pattern =
  /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
function isButtonDisabled() {
  if (
    !emailInfos.value.from_name ||
    !emailInfos.value.reply_to ||
    !emailInfos.value.message
  )
    return true;
  return !pattern.test(emailInfos.value.reply_to);
}
const rules = {
  required: (value) => !!value || "Campo obrigatório.",
  counter: (value) => value.length <= 20 || "Max 20 characters",
  email: (value) => {
    return pattern.test(value) || "E-mail inválido.";
  },
};

const onSendEmailClick = () => {
  isLoading.value = true;
  axios
    .post("https://api.emailjs.com/api/v1.0/email/send", {
      service_id: "service_qlhnalf",
      template_id: "template_duey9ac",
      user_id: "mpUBQi_YKZSGRfpYd",
      template_params: emailInfos.value,
    })
    .then((res) => {
      console.log(res);
      if (res.status === 200) {
        router.push({ name: "home" });
        showErrorMessage.value = false;
      }
    })
    .catch((error) => {
      showErrorMessage.value = true;
    })
    .then(() => {
      emailInfos.value = {};
      isLoading.value = false;
    });
};
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
            <p class="default-text">
              Me mande um email caso queira conversar :)
            </p>
            <v-row class="mt-10" no-gutters>
              <v-col cols="9">
                <p class="subtitle-text">Nome</p>
                <v-text-field
                  v-model="emailInfos.from_name"
                  :rules="[rules.required]"
                  class="form-field"
                  variant="outlined"
                  density="compact"
                ></v-text-field>
                <p class="subtitle-text">Email</p>
                <v-text-field
                  v-model="emailInfos.reply_to"
                  :rules="[rules.required, rules.email]"
                  class="form-field"
                  density="compact"
                  variant="outlined"
                ></v-text-field>
                <p class="subtitle-text">Mensagem</p>
                <v-textarea
                  :rules="[rules.required]"
                  v-model="emailInfos.message"
                  density="compact"
                  variant="outlined"
                >
                </v-textarea>
              </v-col>
            </v-row>
          </v-card-text>
          <v-row justify="end">
            <v-row no-gutters dense justify="start">
              <p v-if="showErrorMessage" class="subtitle-text">
                Ops, parece que algo deu errado. Por favor, tente novamente.
              </p>
            </v-row>
            <v-spacer />
            <v-spacer />
            <div>
              <v-btn
                @click="onSendEmailClick"
                :disabled="isButtonDisabled()"
                :loading="isLoading"
              >
                Enviar
              </v-btn>
            </div>
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
