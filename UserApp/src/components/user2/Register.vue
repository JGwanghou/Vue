<template>
  <h4>User2 등록</h4>
  <form>
    <table border="1">
      <tr>
        <td>아이디</td>
        <td><input type="text" v-model="user.uid" /></td>
      </tr>
      <tr>
        <td>이름</td>
        <td><input type="text" v-model="user.name" /></td>
      </tr>
      <tr>
        <td>휴대폰</td>
        <td><input type="text" v-model="user.hp" /></td>
      </tr>
      <tr>
        <td>나이</td>
        <td><input type="text" v-model="user.age" /></td>
      </tr>
      <tr>
        <td colspan="2" align="right">
          <input type="submit" value="등록" />
        </td>
      </tr>
    </table>
  </form>
</template>
<script setup></script>
<style scoped></style>
