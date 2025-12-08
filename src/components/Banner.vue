<template>
<div id="main-banner">
    <h1>Make your own bottle</h1>
</div>
</template>
<script>
export default {
  name: 'Bannner',
};
</script>
<style scoped>
    #main-banner {
        background-image: url('/home/luiz/Documents/Code/vuejs-project/bottlelab/public/img/BannerImage.png');
        height: 900px;
        background-position: 200px -175px;
        background-repeat: no-repeat;
        background-size: cover;
        display: flex;
        align-items: center;
        justify-content: start;
    }

    #main-banner h1 {
        color: white;
        font-size: 50px;
        font-weight: bold;
        padding: 20px 40px;
        background-color: #333;
        margin-left: 20px;
    }
</style>