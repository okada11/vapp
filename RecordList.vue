<template>
  <div>
    <h2>Records</h2>
    <table>      
      <thead>
        <tr>
          <th>Date</th>
          <th>Category</th>
          <th>Amount</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(record, index) in records" :key="index">
          <td>{{ record.date }}</td>
          <td>{{ record.category }}</td>
          <td>{{ record.amount }}</td>
        </tr>
      </tbody>
    </table>
  </div>>
</template>

<script>
export default {
  props: ['records']
//ここでは親コンポーネントから子コンポーネントにデータを渡している  
};
</script>

<style scoped>
table {
  border-collapse: collapse;
  margin-top: 1rem;
}

th,
td {
  border: 1px solid black;
  padding: 0.5rem;
  text-align: center;
}
</style>
