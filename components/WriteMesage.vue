<template>
  <b-form inline class="formMSG" autocomplete="off">
    <input
      class="inputMesage"
      type="text"
      placeholder="Mensagem..."
      autofocus />
    <b-button class="send" type="submit" variant="outline-success">
      <b-icon icon="cursor" size="1.4"></b-icon>
    </b-button>
  </b-form>
</template>

<script>
export default {
  name: 'WriteMesage',
}
</script>

<style lang="scss">
@import 'bootstrap/scss/bootstrap.scss';

.formMSG {
  @extend .bg-white;
  @extend .border;

  height: 42px;
  position: absolute;
  bottom: 0;
  border-radius: 999px;

  &:not(:focus) {
    @extend .border-light;
  }

  &:focus {
    border-color: #80BDFC;
    outline: 0;
    box-shadow: 0 0 0 0.2rem rgb(0, 123, 255, 0.25);
  }
}

.inputMesage {
  
  @extend .col-8;
  @extend .col-sm-9;
  @extend .m-auto;
  @extend .form-control;

  border: none;
  background-color: transparent;
  outline: none;
}

.send {
  @extend .m-auto;
  max-width: 64px;
  width: fit-content;
  border-width: 2px;
  border-radius: inherit;
}
</style>
