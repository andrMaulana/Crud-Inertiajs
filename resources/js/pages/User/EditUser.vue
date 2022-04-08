<script setup>
import {useForm, Head} from '@inertiajs/inertia-vue3';
const props = defineProps({
    user: Object,
});
const form = useForm({
    name: props.user.name,
    email: props.user.email,
    password: ''
})
</script>

<template>
<Head title="Edit Data"/>
    <div class="max-w-6xl m-auto mt-10">
<form @submit.prevent="form.put(`/user/${user.id}`)">
         <button class="btn btn-sm btn-primary text-white">Back<Link :href="route('user.index')"></Link></button>
    <div class="form-control w-full max-w-xs">
  <label class="label">
    <span class="label-text">Name</span>
  </label>
  <input type="text" v-model="form.name" name="name" placeholder="Masukan Nama" class="input input-bordered w-full max-w-xs">
</div>
<div class="form-control w-full max-w-xs">
  <label class="label">
    <span class="label-text">Emai</span>
  </label>
  <input type="email" v-model="form.email" name="email" placeholder="Masukan email" class="input input-bordered w-full max-w-xs">
</div>
<input type="submit" value="save" class="btn btn-success mt-4 text-white">
</form>
    </div>
</template>
