<template>
  <div>
    <form @submit="submitForm">
      <input type="text" v-model="translateWord" placeholder="请输入需要翻译的内容">
      <select v-model="translateMode">
        <option value="en">English</option>
        <option value="ru">Russian</option>
        <option value="ko">Korean</option>
        <option value="ja">Japenese</option>
      </select>
      <input type="submit">
    </form>
  </div>
</template>

<script>
export default {
  name: 'Form',
  data () {
    return {
      translateWord:'',
      translateMode:'en'
    }
  },
  methods:{
    submitForm:function(e) {
      this.$emit('formSubmit',this.translateWord,this.translateMode)
      e.preventDefault();
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
