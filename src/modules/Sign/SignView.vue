<template>
    <div class="page">
        <div class="page-container"> 
        <form class="login__box">
            <img style="max-width:100%" src="../../assets/logo.png"/>
            <v-text-field label="E-mail" v-model="user.email" type="email" :rules="rules">
                <v-icon slot="prepend" color="grey" >
                  @
                </v-icon>
            </v-text-field>
            <v-text-field :rules="rules" label="Senha" v-model="user.password" type="password">
                <v-icon slot="prepend" color="grey" >
                  mdi-key
                </v-icon>
            </v-text-field>
            <v-btn block depressed color="#00C853" class="white--text" type="submit">
                Entrar
            </v-btn>

            <p class="login__forgot-password">Esqueceu sua senha? <span>Clique aqui</span></p>
        </form>
        <div class="signUp__box">
            <v-btn block depressed color="#1976D2" class="white--text" @click="navigate('signup')">
                Cadastrar-se
            </v-btn>
        </div>
        </div>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                user: {
                    email: '',
                    password: '',
                },
                rules: [
                    value => !!value || 'Obrigatório',
                    value => (value && value.length >= 6) || 'Mínimo de 3 caracteres',
                ],
            }
        },
        methods: {
            navigate(to) {
                this.$router.push({name:to})
            }
        },
    }
</script>

<style scoped>
.page{
    width:100%;
    height:100%;
    background: linear-gradient(180deg, #0038A8 0%, #1E5BD7 100%);
    display: flex;
    justify-content:center;
}
.page-container{
    height:100%;
    width: 768px;
    display:flex;
    justify-content:center;
    flex-direction: column;
    align-items:center;
}
.login__box{
    border-radius: 5px;
    display: flex;
    flex-direction: column;
    max-width: 768px;
    background-color: white;
    padding: 10px;
}
.login__forgot-password{
    align-self: center;
    margin-top: 20px;
}
.login__forgot-password span{
    color: #3366ff;
    cursor:pointer;
}
.login__forgot-password span:hover{
    text-decoration: underline;
}
.signUp__box{
    margin-top: 40px;
    width: 100%;
    background-color: white;
    padding:20px;
    border-radius: 5px;
}
@media only screen and (max-width: 768px) {
  .page-container{
      width: calc(100% - 40px)
  }
}
</style>