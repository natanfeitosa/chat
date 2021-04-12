<template>
  <b-card
    class="p-2 mt-5 bg-light shadow"
    style="width: min(350px, 98%); margin: auto"
  >
    <b-form>
      <b-form-group class="text-center mb-4">
        <Avatar
          ref="previewAvatar"
          size="170px"
          :src="avatar"
          @click="loadAvatar()"
          @mouseover="show = true"
          @mouseout="toggleHide"
        >
          <b-icon
            v-if="show"
            icon="camera"
            font-scale="2.2"
            variant="light"
          ></b-icon>
        </Avatar>
        <b-form-file
          ref="imageInput"
          plain
          class="d-none"
          @change="changeInputFile"
        ></b-form-file>
      </b-form-group>

      <label for="loginEmail" class="text-black-50">Seu email</label>
      <b-form-input
        id="loginEmail"
        v-model="email"
        type="email"
        class="text-center"
        placeholder="exemplo@email.com"
        required
      ></b-form-input>

      <br />

      <label for="loginUser" class="text-black-50">Seu nome de usuário</label>
      <b-form-input
        id="loginUser"
        v-model="password"
        type="text"
        class="text-center"
        placeholder="@meu_username"
        required
      ></b-form-input>
      <div class="text-center mt-4">
        <b-button type="submit" style="font-weight: 500" variant="info">
          Entrar
        </b-button>
      </div>
    </b-form>
  </b-card>
</template>
<script>
// import { BIcon } from 'bootstrap-vue'

export default {
  name: 'Login',
  components: {
    // BIcon,
  },
  data() {
    return {
      show: true,
      avatar: '',
      email: '',
      password: '',
    }
  },
  watch: {
    avatar(n) {
      this.show = !!(n !== '')
    },
  },
  methods: {
    toggleHide() {
      this.show = this.avatar.length < 1
    },
    loadAvatar() {
      const input = this.$refs.imageInput.$el
      input.click()
    },
    changeInputFile(event) {
      this.toBase64(event.target.files[0], (i) => {
        this.avatar = i
      })
    },
    toBase64(file, callback) {
      const reader = new FileReader()
      reader.readAsDataURL(file)
      reader.onload = () => callback(reader.result)
    },
  },
}
</script>

<!-- 21:58 -->
