<template>
  <div>
    <h1>海野</h1>
    <p>練習</p>
    <button v-on:click="textChange" >送信</button>
    <p>{{ text }}</p>
  </div>
</template>

<script>
export default {
   data() {
    return {
      id: 14,
      text: '',
    }
  },
  methods: {
    textChange() {
      this.text = '変更しました'
    }
  },
};
</script>