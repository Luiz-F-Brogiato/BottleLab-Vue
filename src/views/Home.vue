<template>
    <Banner />
    <div class="main-container">
        <h1>Monte a sua garrafa</h1>
        <p>Formulário</p>
        <BottleForm />
    </div>
</template>
<script>
import Banner from '@/components/Banner.vue';
import BottleForm from '@/components/BottleForm.vue';

export default {
  name: 'Home',
  components: {
    Banner,
    BottleForm,
  },
};
</script>