<template>
  <b-col class="border-dark rounded my-1">
    <ul class="msgs">
      <b-row tag="li" class="msg">
        <div class="mt-4 mb-1 d-inline-flex">
          <Avatar
            src="//via.placeholder.com/100"
            class="border-0"
            size="34px"
          ></Avatar>
          <b-col class="content">
            <p class="user">Fulano</p>
            <p class="body">Aqui está a mensagem</p>
            <small class="at">Hoje às 22:21</small>
          </b-col>
        </div>
      </b-row>

      <b-row tag="li" class="msg me">
        <div class="mt-4 mb-1 d-inline-flex">
          <Avatar
            src="//via.placeholder.com/100"
            class="border-0"
            size="34px"
          ></Avatar>
          <b-col class="content">
            <p class="user">Fulano</p>
            <p class="body">Aqui está a mensagem</p>
            <small class="at">Hoje às 22:21</small>
          </b-col>
        </div>
      </b-row>
    </ul>
  </b-col>
</template>

<script>
export default {
  name: 'ChatList',
  props: {
    payload: {
      type: Object,
      default: () => ({ src: '' }),
    },
  },
}
</script>

<style lang="scss" scoped>
@import 'bootstrap/scss/bootstrap.scss';

.col {
  width: min(98%, 540px); background-color: #2f495e;
  box-shadow: 0 0rem 3rem 0px rgb(253 253 253 / 10%);
}

.msgs {
  padding: 0;
  /* height: calc(100% - 42px); */
  height: 80%;
  overflow-y: scroll;
  overflow-x: hidden;
  padding: 0 8px 0 12px;
}

.msg {
  @extend .px-2;
  @extend .pb-3;

  &:not(.me) {
    @extend .justify-content-start;

    .user {
      right: 8px;
    }

    .at {
      left: 8px;
    }
  }

  &.me {
    @extend .justify-content-end;

    .content {
      order: -1;
      background-color: #78e08f;

      .user {
        left: 8px;
      }

      .at {
        right: 8px;
      }
    }
  }

  .content {
    margin: 0 10px;
    border-radius: 20px;
    background-color: #82ccdd;
    padding: 10px;
    padding: 4px 10px;
    height: fit-content;

    .body {
      margin: 0;
      padding: 2px 4px;
      min-width: 82px;
      max-width: 230px;
      border-radius: inherit;
      overflow: hidden;
      white-space: break-spaces;
    }

    .user,
    .at {
      padding: 2px 4px;
      position: absolute;
      color: rgba(255, 255, 255, 0.76);
      width: max-content;
    }

    .user {
      @extend .font-weight-bold;
      top: -1.2rem;
      font-size: 0.8rem;
      margin: 0;
    }

    .at {
      bottom: -1.2rem;
    }
  }
}
</style>
