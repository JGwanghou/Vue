<template>
  <v-app>
    <v-app-bar>
      <v-toolbar-title>약관</v-toolbar-title>
    </v-app-bar>
    <v-main>
      <v-container>
        <v-sheet max-width="800" class="mx-auto">
          <v-textarea
            label="이용약관"
            variant="outlined"
            rows="10"
            readonly=""
            hide-details="true"
            v-model="value.terms"
          ></v-textarea>
          <v-checkbox
            label="동의합니다."
            class="d-flex justify-end"
            v-model="isCheck1"
          ></v-checkbox>

          <v-textarea
            label="개인정보 취급방침"
            variant="outlined"
            readonly="readonly"
            rows="10"
            hide-details="true"
            v-model="value.privacy"
          ></v-textarea>
          <v-checkbox
            label="동의합니다."
            class="d-flex justify-end"
            v-model="isCheck2"
          ></v-checkbox>
          <v-sheet class="text-center">
            <v-btn class="mr-1" @click="btnCancel">취소</v-btn>
            <v-btn color="primary" @click="btnNext">다음</v-btn>
          </v-sheet>
        </v-sheet>
      </v-container>
    </v-main>
  </v-app>
</template>
<script setup>
import axios from "axios";
import { useRouter } from "vue-router";
import { reactive } from "vue";
import { onBeforeMount } from "vue";
import { ref } from "vue";
const router = useRouter();

const isCheck1 = ref(false);
const isCheck2 = ref(false);

const btnCancel = () => {
  router.push("/user/login");
};
const btnNext = () => {
  if (isCheck1.value && isCheck2.value) {
    router.push("/user/register");
  } else {
    alert("동의 체크를 하십시오.");
  }
};

const value = reactive({
  terms: null,
  privacy: null,
});
onBeforeMount(() => {
  axios
    .get("http://localhost:8080/Voard/user/terms")
    .then((response) => {
      console.log(response);
      value.terms = response.data.terms;
      value.privacy = response.data.privacy;
    })
    .catch((error) => {
      console.log(error);
    });
});
</script>
<style scoped></style>
