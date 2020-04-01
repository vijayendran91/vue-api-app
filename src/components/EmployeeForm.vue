<template>
  <div id='employee-form'>
    <form @submit.prevent="handleSubmit">
      <label>Employee Name</label>
      <input v-model='employee.name' type='text'/>
      <br>
      <label>Employee Email</label>
      <input v-model='employee.email' type='text'/>
      <br>
      <button>Add Employee</button>
    </form>
  </div>
</template>

<script>
  export default {
  name: 'employee-form',
  data() {
    return {
      employee: {
        name: '',
        email: '',
      },
    }
  },
  methods:{
    handleSubmit() {
      this.$emit('add:employee', this.employee)
    },
  }
}
</script>
