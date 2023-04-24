<template>
  <v-app>
    <v-app-bar>
      <v-toolbar-title>회원가입</v-toolbar-title>
    </v-app-bar>
    <v-main>
      <v-container>
        <v-sheet max-width="800" class="mx-auto border"></v-sheet>

        <v-card>
          <v-card-item>
            <v-card-title>사이트 이용정보 입력</v-card-title>
          </v-card-item>
          <v-card-text>
            <v-row>
              <v-col cols="=5">
                <v-text-field
                  label="아이디 입력"
                  variant="outlined"
                  hide-details="true"
                  density="compact"
                ></v-text-field>
              </v-col>
              <v-col cols="=7">
                <v-btn color="warning">중복 확인</v-btn>
              </v-col>
            </v-row>
          </v-card-text>
        </v-card>

        <v-card>
          <v-card-item>
            <v-card-title>개인정보 입력</v-card-title>
          </v-card-item>
          <v-card-text>
            <v-row>
              <v-col cols="=5">
                <v-text-field
                  label="아이디 입력"
                  variant="outlined"
                  hide-details="true"
                  density="compact"
                ></v-text-field>
              </v-col>
            </v-row>
          </v-card-text>
        </v-card>

        <v-sheet class="text-center">
          <v-btn class="mr-1" @click="btnCancel">취소</v-btn>
          <v-btn color="primary" @click="btnLogin">회원가입</v-btn>
        </v-sheet>
      </v-container>
    </v-main>
  </v-app>
</template>
<script setup>
import { useRouter } from "vue-router";

const router = useRouter();

const btnCancel = () => {
  router.push("/user/login");
};
const btnLogin = () => {
  router.push("/list");
};
</script>
<style scoped></style>
