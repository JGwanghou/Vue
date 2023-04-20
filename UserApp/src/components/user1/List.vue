<template>
  <h4>User1 목록</h4>
  <table border="1">
    <tr>
      <th>아이디</th>
      <th>이름</th>
      <th>휴대폰</th>
      <th>나이</th>
      <th>관리</th>
    </tr>
    <tr v-for="user in users">
      <td>{{ user.uid }}</td>
      <td>{{ user.name }}</td>
      <td>{{ user.hp }}</td>
      <td>{{ user.age }}</td>
      <td>
        <a href="#" @click.prevent="modifyUser1(user)">수정</a>&nbsp;
        <a href="#" @click.prevent="deleteUser1(user)">삭제</a>
      </td>
    </tr>
  </table>
</template>
<script setup>
import axios from "axios";
import { useRouter } from "vue-router";
import { onBeforeMount } from "vue";
import { ref } from "vue";
const router = useRouter();
const users = ref([]);
// reactive({ items: [] })
onBeforeMount(() => {
  axios
    .get("http://localhost:8080/Ch09/user1s")
    .then((response) => {
      console.log(response);
      users.value = response.data;
      // users.items = response.data
    })
    .catch((error) => {
      console.log(error);
    });
});

const modifyUser1 = (user) => {
  router.push({ name: "User1Modify", params: user });
};
const deleteUser1 = (user) => {
  const result = confirm("정말 삭제하시겠습니까?");
  if (!result) {
    return;
  }

  axios
    .delete(`http://localhost:8080/Ch09/user1/${user.uid}`)
    .then((response) => {
      console.log(response);
      users.value = response.data;
      // users.items = response.data
    })
    .catch((error) => {
      console.log(error);
    });
};
</script>
<style scoped></style>
