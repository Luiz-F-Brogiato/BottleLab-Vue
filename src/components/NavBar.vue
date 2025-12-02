<template>
     <div id="nav">
        <router-link to="/" id="logo_url">
        <img :src="logo" :alt="alt" id="logo ">
        </router-link>
    <router-link to="/">Home</router-link> |
    <router-link to="/pedidos">Pedidos</router-link>
     </div> 
</template>
<script scoped>
export default {
    name: "NavBar",
    props: ["logo", "alt"]
}
</script>

<style>
#nav {
    background-color: #222;
    border-bottom: 4px solid #111;
    padding: 15px 50px;
    display: flex;
    align-items: center;
    justify-content: flex-end;
}
#logo {
  
    height: 40px;
    width: 40px;
}
#nav #logo_url {
     margin: auto;
    margin-left: 0;
}

#nav a {
    color: #bbb;
    text-decoration: none;
    margin: 12px;
    font-size: 18px;
    transition: all 0.3s ease;
}
#nav a:hover {
    color: white;
}
</style>