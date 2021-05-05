<template>
  <div id="app">

    <nav>
      <div class="nav-wrapper blue darken-1">
        <a href="#" class="brand-logo center">Cadastrar Clientes</a>
      </div>
    </nav>

    <div class="container">

      <form @submit.prevent="salvar(), this.listar()">

          <label>NOME</label>
          <input type="text" placeholder="Digite seu nome" required v-model="pessoa.nome" >
          <label>CPF</label>
          <input type="text" placeholder="Digite seu CPF" required v-model="pessoa.cpf" >
          <label>E-mail</label>
          <input type="text" placeholder="Digite seu E-mail" required v-model="pessoa.email">
          <label>Senha</label>
          <input type="password" placeholder="Digite sua senha" required v-model="senha1">
          <label>Repita a senha</label>
          <input type="password" placeholder="Confirme sua senha" required v-model="senha2">

          <button class="waves-effect waves-light btn-small">Salvar<i class="material-icons left"></i></button>

      </form>

      <table>

        <thead>
          <tr>
            <th>NOME</th>
            <th>CPF</th>
            <th>E-mail</th>
          </tr>
        </thead>

        <tbody>

          <tr v-for="pessoa of pessoas" :key="pessoa.id">

            <td>{{ pessoa.nome }}</td>
            <td>{{ pessoa.cpf }}</td>
            <td>{{ pessoa.email }}</td>
            <td>
              <button @click="editar(pessoa), this.listar()" class="waves-effect btn-small blue darken-1"><i class="material-icons">Editar </i></button>
              <button @click="remover(pessoa), this.listar()" class="waves-effect btn-small red darken-1"><i class="material-icons">Excluir </i></button>

            </td>

          </tr>

        </tbody>
      
      </table>

    </div>

  </div>
</template>

<script>

  import Pessoa from './services/pessoas'
  
  export default{

    data(){
      return {
        
        pessoa:{
          id:'',
          nome:"",
          cpf:'',
          email:'',
          senha:''

        },
        senha1:[],
        senha2:[],

        pessoas:[]
      }
    },
    mounted(){
      this.listar()
    },

    methods:{

      listar(){
        Pessoa.listar().then(resposta => {    
        this.pessoas = resposta.data;
      })
      },

      salvar(){
        if(this.senha1 === this.senha2){

          this.pessoa.senha = this.senha1
          if(!this.pessoa.id){
            Pessoa.salvar(this.pessoa)
            alert('salvo com sucesso! ')
            this.pessoa = {}
            this.senha1=""
            this.senha2=""

          }else {
            Pessoa.atualizar(this.pessoa)
            alert('Atualizado com sucesso!')
            this.pessoa = {}
            this.senha1=""
            this.senha2=""
            this.pessoa.id()
          }

        }else {
          alert("As senhas não combinam")
        }
  
      },

      editar(pessoa){
        this.pessoa = pessoa
      },

      remover(pessoa){
        Pessoa.apagar(pessoa)
        alert("Cliente removido")
        this.listar()
        
      } 
    }
  }
 
</script>

<style>

</style>
