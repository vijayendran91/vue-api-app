<template>
  <div id='employee-table'>
    <table>
      <thead>
        <tr>
          <th>Employee Name</th>
          <th>Employee Email</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="employee in employees_array" :key="employee.id">
          <td>{{employee.name}}</td>
          <td>{{employee.email}}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
  export default{
    name: 'employee-table',
    props:{
      employees_array: Array
    }
  }
</script>
