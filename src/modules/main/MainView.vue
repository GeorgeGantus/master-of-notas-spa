<template>
  <div class="main">
    <header class="header">
        <div class="header__left">
            <span @click="toggleMenu()">hamb</span>
            <img class="menu__logo" src="@/assets/logo.svg" alt="">
        </div>
        <div>
            
        </div>
        
    </header>
    <div class="content">
        <div class="content__sidebar" :class="{'is-expanded': isMenuExpanded}"> Side Bar</div>
        <div>{{user.username}}</div>
        <br>
        <div>{{user.tipoUsuario}}</div>

    </div>
    <footer>dasdsa</footer>
  </div>
</template>

<script>
import { mapState } from 'vuex'
  export default {
    data: () => ({ 
        drawer: null ,
        isMenuExpanded: false
        
        
    }),
    computed:{
        ...mapState(['user'])
    },
    methods: {
        toggleMenu() {
            this.isMenuExpanded = !this.isMenuExpanded
        }
    },
  }
</script>
<style scoped>
.main{
    background: #E5E5E5;
    height: 100%;
    display: flex;
    flex-direction: column;
}
.aux{
    display: flex;
    justify-content: center;
    align-items: center;
}
.header{
    height: 90px;
    display: flex;
    justify-content: space-between;
    padding: 0px 20px;
}
.header__left{
    height: 100%;
}
.menu__logo{
    max-width: 250px;
}
.content{
flex-grow:1;
display: flex;
}
.content__sidebar{
    width: 50px;
    background: #1E5BD7;;
    transition: width .7s;
}
.is-expanded{
    width: 200px;
}
</style>