<template>
  <div>
    <h1 class="title">Users</h1>
    <b-table :data="users" :columns="columns"></b-table>
  </div>
</template>

<script>
export default {
  name: 'Table',

  data() {
    return {
      users: [],
      columns: [
        {
          field: 'id',
          label: 'ID',
          width: '40',
          numeric: true
        },
        {
          field: 'name',
          label: 'Name'
        },
        {
          field: 'phone',
          label: 'Phone',
          centered: true
        },
        {
          field: 'email',
          label: 'Email'
        }
      ]
    }
  },
  async mounted() {
    this.users = await this.$axios.$get(
      'https://jsonplaceholder.typicode.com/users'
    )
  }
}
</script>
