<template>
  <v-app>
    <v-app-bar>
      <v-app-bar-title>글쓰기</v-app-bar-title>
    </v-app-bar>
    <v-main>
      <v-container>
        <v-sheet class="mx-auto" max-width="800">
          <v-text-field
            label="제목입력"
            variant="outlined"
            v-model="article.title"
          ></v-text-field>
          <v-textarea
            label="내용입력"
            variant="outlined"
            rows="12"
            v-model="article.content"
          ></v-textarea>
          <v-file-input label="파일첨부" variant="outlined"></v-file-input>
          <v-sheet class="text-right">
            <v-btn @click="btnCancel">취소</v-btn>
            <v-btn color="primary" @click="btnWrite" class="ml-2">글등록</v-btn>
          </v-sheet>
        </v-sheet>
        <v-dialog v-model="dialog" width="auto">
          <v-card>
            <v-card-text> 글 작성이 완료되었습니다. </v-card-text>
            <v-card-actions>
              <v-btn color="primary" block @click="dialog = false">확인</v-btn>
            </v-card-actions>
          </v-card>
        </v-dialog>
      </v-container>
    </v-main>
  </v-app>
</template>
<script setup>
import { useRouter } from "vue-router";
import { reactive } from "vue";
import axios from "axios";
import { useStore } from "vuex";
import { ref } from "vue";

const router = useRouter();
const store = useStore();

const article = reactive({
  title: null,
  content: null,
  uid: store.getters.user.uid,
});
const dialog = ref(false);

const btnCancel = () => {
  router.push("/list");
};
const btnWrite = () => {
  console.log(article);

  axios
    .post("http://localhost:8080/Voard/article/register", article)

    .then((response) => {
      console.log(response);

      dialog.value = true;
    })
    .catch((error) => {
      console.log(error);
    });
};
</script>
<style scoped></style>
