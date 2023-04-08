<template>
  <form>
    <label for="date">日付:</label>
    <input type="date" v-model="date">
    <label for="category">カテゴリー:</label>
    <select v-model="category">
      <option value="食費">食費</option>>
      <option value="交際費">交際費</option>>
      <option value="交通費">交通費</option>>
      <option value="住居費">住居費</option>>
      <option value="その他">その他</option>>
    </select>
    <label for="amount">金額</label>
    <input type="number" v-model.number="amount">
    <button type="button" @click="submitForm">追加</button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      date: '',
      category: '',
      amount: '',
    };
  },
  methods: {
    submitForm() {
      const record = {
        date: this.date,
        category: this.category,
        amount: this.amount,
      };
      this.$emit('addRecord', record);
      this.date = '';
      this.category = '';
      this.amount = '';
      localStorage.setItem('record', JSON.stringify({
        date: this.prevDate,
        category: this.prevCategory,
        amount: this.prevamount,
      }))
    }
  }
}
</script>
