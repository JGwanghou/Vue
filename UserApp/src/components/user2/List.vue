<template>
  <h4>User2 목록</h4>
  <table border="1">
    <tr>
      <th>아이디</th>
      <th>이름</th>
      <th>휴대폰</th>
      <th>나이</th>
      <th>관리</th>
    </tr>
    <tr>
      <td>1</td>
      <td>2</td>
      <td>3</td>
      <td>4</td>
      <td>
        <a href="#">수정</a>&nbsp;
        <a href="#">삭제</a>
      </td>
    </tr>
  </table>
</template>
<script setup>
import { onBeforeMount } from "vue";
import axios from "axios";
onBeforeMount(() => {
  axios
    .get("http://localhost:8080/Ch07/user2/list")
    .then((response) => {
      console.log(response);
    })
    .catch((error) => {
      console.log(error);
    });
});
</script>
<style scoped></style>
