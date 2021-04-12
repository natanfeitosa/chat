<template>
  <b-container>
    <div class="mt-4">
      <ChatList :payload="payload" class="m-auto"></ChatList>
    </div>
  </b-container>
</template>

<script>
export default {
  data() {
    return {
      payload: {},
    }
  },
}
</script>
