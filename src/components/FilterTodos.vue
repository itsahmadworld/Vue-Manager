<template>
  <div>
    Filter Todos: 
    <select @change="onChange" v-model="limit">
    <option value="200">200</option>
    <option value="100">100</option>
    <option value="50">50</option>
    <option value="25">25</option>
    <option value="10">10</option>
    <option value="5">5</option>
  </select>
  </div>
</template>

<script>
import { mapActions } from 'vuex';
export default {
  data() {
        return {
            limit: 200
        }
    },
    methods: {
        ...mapActions(['filterTodos']),
        onChange() {
            this.filterTodos(this.limit);
        }
    },
}
</script>

<style>
select {
    margin-top: 20px;
    padding: 5px;
    border: 1px solid #41b883;

}

</style>