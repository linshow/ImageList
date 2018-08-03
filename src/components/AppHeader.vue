<template>
    <div class="ui secondary pointing menu">
        <router-link  to="/" class="active item">
        image storage 
        </router-link>
        <!-- {{ isLoggedIn}} -->
        <div class="right menu">
            <div v-if="isLoggedIn" class="horizontal">
                <router-link to="/" class="item">Galleries</router-link>
                <router-link class="item" to="/upload">upload</router-link>
                <a class="item" @click="logout">logout</a>
               
              
            </div>


            <a v-else  href="#" class="ui item" @click="login">
                Login
            </a>
        </div>
    </div>
</template>


<script>
import {mapActions,mapGetters} from 'vuex';
export default {
    name:'AppHeader',
    computed: mapGetters(['isLoggedIn']),
    methods: mapActions(['login','logout'])
};
</script>


<style scoped>
.horizontal{
    display: flex;
    flex-direction: row;

}
</style>
