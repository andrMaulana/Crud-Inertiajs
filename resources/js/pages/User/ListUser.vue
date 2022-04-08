<script setup>
    import {Link, Head}  from '@inertiajs/inertia-vue3';
defineProps({
    users : Object
})
</script>
<template>
<Head title="List Data"/>


<div class="max-w-5xl m-auto mt-5">
    <div class="overflow-x-auto mt-3">
    <Link :href="route('user.create')" class="btn btn-primary text-white">Create User</Link>
  <table class="table w-full mt-3">
    <!-- head -->
    <thead>
      <tr>
        <!-- <th></th> -->
        <th>Name</th>
        <th>Email</th>
        <th>Action</th>
      </tr>
    </thead>
    <tbody>
      <!-- row 1 -->
      <tr v-for="(user) in users" :key="user.id">
        <!-- <th>{{ user.id }}</th> -->
        <td>{{ user.name }}</td>
        <td>{{ user.email }}</td>
        <td class="pt-1 space-x-2">
            <Link :href="route('user.edit', user.id)" class="btn btn-warning btn-sm">Edit</Link>
            <Link :href="`/user/${user.id}`" method="delete" class="btn btn-error btn-sm">Delete</Link>
            </td>
      </tr>

    </tbody>
  </table>
</div>
</div>
</template>
