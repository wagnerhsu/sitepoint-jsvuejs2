<template>
  <h1>{{ heading }}</h1>
  <table>
    <thead>
      <tr>
        <td>FirstName</td>
        <td>LastName</td>
        <td>Email</td>
      </tr>
    </thead>
    <tbody>
      <tr v-for="employee in employees" :key="employee.firstName">
        <td>{{ employee.firstName }}</td>
        <td>{{ employee.lastName }}</td>
        <td>{{ employee.email }}</td>
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
      heading: "Staff Directory",
      employees: [
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
};
</script>