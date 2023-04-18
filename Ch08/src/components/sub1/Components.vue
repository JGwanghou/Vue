<template>
  <h4>Vuetity Components 실습</h4>

  <div>
    <h4>Icons</h4>
    <v-icon color="warning" icon="mdi-wifi" size="x-large"></v-icon>
    <v-icon color="info" icon="mdi-check-circle" size="x-large"></v-icon>
    <v-icon icon="mdi-cat"></v-icon>
    <hr />
    <h4>Images</h4>
    <v-img
      :width="324"
      aspect-ratio="16/9"
      cover
      src="https://cdn.vuetifyjs.com/images/parallax/material.jpg"
    ></v-img>
    <v-img
      :width="397"
      aspect-ratio="1/1"
      cover
      src="https://cdn.vuetifyjs.com/images/parallax/material.jpg"
    ></v-img>
    <hr />
    <h4>Buttons</h4>
    <v-btn variant="elevated" color="primary"> 구입 </v-btn>
    <v-btn prepend-icon="mdi-cat" variant="outlined"> Button </v-btn>
    <v-btn block>Block Button</v-btn>
    <v-btn color="secondary">Button4</v-btn>
    <v-btn color="success">Button5</v-btn>
    <v-btn color="warning">Button6</v-btn>
    <hr />
    <h4>Card</h4>
    <v-card
      loading
      title="제목입니다"
      subtitle="부제목입니다"
      text="내용입니다."
    >
      <v-card-actions>
        <v-btn>확인</v-btn>
      </v-card-actions>
    </v-card>

    <v-card
      loading
      width="400"
      title="제목입니다"
      subtitle="부제목입니다"
      text="내용입니다."
      class="border mt-2"
    >
      <v-card-actions>
        <v-btn>확인</v-btn>
      </v-card-actions>
    </v-card>

    <v-card width="400">
      <v-img
        height="200"
        src="https://cdn.pixabay.com/photo/2020/07/12/07/47/bee-5396362_1280.jpg"
        cover
        class="text-white my-10"
      >
        <v-card-item>
          <v-card-title>제목입니다</v-card-title>

          <v-card-subtitle>부제목입니다</v-card-subtitle>
        </v-card-item>
      </v-img>

      <v-card-text> 여기는 내용입니다.</v-card-text>
    </v-card>
    <hr />
  </div>
</template>
<script setup></script>
<style scoped></style>
