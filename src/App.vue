<template>
  <div id="app" class="small-container">
    <h1> Employee Table </h1>
    <employee-table :employees_array="employees"/>
    <br>
    <br>
    <h1> Add Employees </h1>
    <employee-form @add:employee="addEmployee"/>
  </div>
</template>

<script>
  import EmployeeTable from '@/components/EmployeeTable.vue'
  import EmployeeForm from '@/components/EmployeeForm.vue'

  export default{
    name: 'app',
    components: {
      EmployeeTable,
      EmployeeForm,
    },
    data(){
      return{
        employees: [
          {
            id:1,
            name: 'Vijayendran Gopalakrishnan',
            email: 'vijayendran91@gmail.com'
          },
          {
            id:2,
            name: 'Chandhini Muthiah',
            email: 'chandhinimuthiah@gmail.com'
          }
        ],
      }
    },
    methods: {
      addEmployee(employee){
        const lastId =
        this.employees.length > 0
          ? this.employees[this.employees.length - 1].id
          : 0;
        const id = lastId + 1;
        const newEmployee = { ...employee, id };
        this.employees = [...this.employees, newEmployee];
      }
    }
  }
</script>
