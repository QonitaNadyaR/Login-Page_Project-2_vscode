<template>
    <div>
        <div v-if="!auth.username">
            <router-link to="/login">Silakan login untuk mengakses halaman ini</router-link>
        </div>
        <div v-else>
            Lorem, ipsum dolor sit amet consectetur adipisicing elit. Excepturi assumenda vitae doloremque distinctio quos!
            Quam dolorem eligendi sit placeat numquam, eos voluptates animi officiis vitae, cupiditate exercitationem in
            unde nisi!
        </div>
    </div>
</template>
  
<script setup lang="ts">
import { useAuthStore } from '@/stores/auth';
import { useRouter } from 'vue-router';

const auth = useAuthStore();
const router = useRouter();

if (!auth.username) {
    alert('Silakan login untuk mengakses halaman ini');
    router.push('/login');
}
</script>
  