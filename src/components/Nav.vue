<script setup>
import {RouterLink} from "vue-router"
import container from "./container.vue";
import AuthModal from "./AuthModal.vue"
import {ref} from "vue"

const value=ref("")
const isAuthenticated=ref(false)
const onSearch=()=>{}
</script>
<template>
   <ALayoutHeader>
    <container>
        <div class="nav-container">
            <div class="right-content">
    <RouterLink to="/">Instagram</RouterLink>
    
        <AInputSearch
        v-model:value="value"
        placeholder="username..."
        style="width: 200px"
        @search="onSearch"
        />
    </div>
    <div class="left-content" v-if="!isAuthenticated">
    <!-- <AButton type="primary">sign up</AButton> -->
    <!-- <AButton type="primary"> LogIn</AButton> -->
    <AuthModal :isLogin="false"/>
    <AuthModal :isLogin="true"/>
</div>
<div class="left-content" v-else>
    <a-button type="primary">Profile</a-button>
    <a-button type="primary">Logout</a-button>
</div>

</div>
</container>
   </ALayoutHeader>
</template>
<style scoped>
.nav-container{
    background-color: aqua;
    display: flex;
    justify-content: space-between;
}
.right-content{
    display: flex;
    align-items:center ;
}
.right-content a{
    margin-right:10px;

}
.left-content{
    display: flex;
    align-items: center;
}
.left-content button{
    margin-left:10px;
    
}
</style>