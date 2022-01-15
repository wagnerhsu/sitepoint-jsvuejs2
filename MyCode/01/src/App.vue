<template>
  <h1>{{ heading }}</h1>
  <input v-model="text" type="text" />
  <p>{{ text }}</p>
  <button @click="setText">SetText</button>
  <table>
    <thead>
      <tr>
        <td>FirstName</td>
        <td>LastName</td>
        <td>Email</td>
        <td>Photo</td>
      </tr>
    </thead>
    <tbody>
      <tr v-for="(employee, index) in employees" :key="index">
        <td>{{ employee.firstName }}</td>
        <td>{{ employee.lastName }}</td>
        <td>{{ employee.email }}</td>
        <td><img :src="employee.photoUrl" /></td>
      </tr>
    </tbody>
  </table>
</template>

<script>
export default {
  name: "App",
  components: {},
  data() {
    return {
      sortBy: "firstName",
      text: "",
      heading: "Staff Directory",
      employees: [
         {
          firstName: "cobbie",
          lastName: "nurphy",
          photoUrl: "https://randomuser.me/api/portraits/thumb/women/79.jpg",
          email: "bobbie.murphy@example.com",
          phone: "(925)-667-7604",
          department: "Management",
        },
        {
          firstName: "amelia",
          lastName: "austin",
          photoUrl: "https://randomuser.me/api/portraits/thumb/women/9.jpg",
          email: "amelia.austin@example.com",
          phone: "(651)-507-3705",
          department: "Engineering",
        },
        {
          firstName: "bobbie",
          lastName: "murphy",
          photoUrl: "https://randomuser.me/api/portraits/thumb/women/79.jpg",
          email: "bobbie.murphy@example.com",
          phone: "(925)-667-7604",
          department: "Management",
        },
      ],
    };
  },
  computed: {
    sortedEmployees() {
      return this.employees.sort((a, b) =>
        a[this.sortBy].localeCompare(b[this.sortBy])
      );
    },
  },
  methods: {
    setText(event) {
      this.text = "SetText";
      console.log(event);
      this.sortBy = "lastName";
      this.employees = this.sortedEmployees;
    },
  },
};
</script>