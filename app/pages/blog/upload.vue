<template>
  <v-row justify="center">
    <v-col
      sm="12"
      md="11"
      lg="9"
      xl="6"
    >
      <h2 class="mt-6 mb-6">UPLOAD</h2>
      <v-divider></v-divider>

      <v-sheet class="pa-3">
        <v-form ref="form">
          <v-label>タイトル</v-label>
          <v-text-field></v-text-field>
          <v-label>イメージ画像を選択</v-label>
          <v-file-input
            v-model="input_image"
            accept="image/*"
            show-size
            label="512×512のサイズで表示されます"
            prepend-icon="mdi-image"
            @change="onImagePicked"
          ></v-file-input>
          <v-img
            v-if="uploadImageUrl"
            :src="uploadImageUrl"
          />
          <v-label>本文</v-label>
          <v-textarea></v-textarea>
        </v-form>
      </v-sheet>
    </v-col>
  </v-row>
</template>

<script>
// 画像プレビュー
// 参考: https://qiita.com/Yoshihiro-Hirose/items/82b9dccdf270551db887
export default {
  data() {
    return {
      input_image: null,
      uploadImageUrl: '',
    };
  },
  methods: {
    onImagePicked(file) {
      if (file !== undefined && file !== null) {
        if (file.name.lastIndexOf('.') <= 0) {
          return;
        }
        const fr = new FileReader();
        fr.readAsDataURL(file);
        fr.addEventListener('load', () => {
          this.uploadImageUrl = fr.result;
        });
      } else {
        this.uploadImageUrl = '';
      }
    },
  },
};
</script>
