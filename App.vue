<template>
  <div>
    <h1>家計簿</h1>
    <record-form @addRecord="addRecord"></record-form>
    <record-list :records="records"></record-list>
  </div>
</template>

<script>
import RecordForm from './components/RecordForm.vue';
import RecordList from './components/RecordList.vue';

export default {
  components: {
    RecordForm,
    RecordList,
  },
  data() {
    return {
      records: []      
    }
  },
  methods: {
    addRecord(record) {
      this.records.push(record);
    }
  }
}
</script>

<style>

</style>
