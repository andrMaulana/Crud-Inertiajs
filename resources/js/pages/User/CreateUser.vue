<script setup>
import {useForm, Head, Link} from '@inertiajs/inertia-vue3';
const form = useForm({
    name: '',
    email: '',
    password: ''
})
</script>

<template>
    <Head title="Create User" />
    <div class="max-w-6xl m-auto mt-10">
    <Link :href="route('user.index')" class="btn btn-sm btn-primary text-white">kembali</Link>
<form @submit.prevent="form.post('/user')">
    <div class="form-control w-full max-w-xs">
  <label class="label">
    <span class="label-text">Name</span>
  </label>
  <input type="text" v-model="form.name" name="name" placeholder="Masukan Nama" class="input input-bordered w-full max-w-xs">
  <span v-if="$page.props.errors.name" class="text-error text-sm">{{ $page.props.errors.name }}</span>
</div>
<div class="form-control w-full max-w-xs">
  <label class="label">
    <span class="label-text">Email</span>
  </label>
  <input type="email" v-model="form.email" name="email" placeholder="Masukan email" class="input input-bordered w-full max-w-xs">
  <span v-if="$page.props.errors.email" class="text-error text-sm">{{ $page.props.errors.email }}</span>
</div>
<div class="form-control w-full max-w-xs">
  <label class="label">
    <span class="label-text">Password</span>
  </label>
  <input type="password" v-model="form.password" name="password" placeholder="Masukan password" class="input input-bordered w-full max-w-xs">
  <span v-if="$page.props.errors.password" class="text-error text-sm">{{ $page.props.errors.password }}</span>
</div>

<input type="submit" value="save" class="btn btn-success mt-4 text-white">
</form>
    </div>
</template>
