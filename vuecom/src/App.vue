<template>
  <div id="App" class="card" v-bind:class='"boder"'>
    <h4>Testing text binding</h4>
    <input type="number" name="Temperature" id="temp">
    <button type="submit">Submit</button>
    <h4 v-text="test1" v-bind:class="status"></h4>
    <p>{{test2}}</p>
    <p v-text="para" ></p>  
    <form action="" method="post" @submit="submitForm" >
    
      <table>
        <tr>
          <td> <label for="Name">Name </label></td>
          <td><input type="text" placeholder="Enter your Name" v-model="formValue.name"></td>
        </tr>
        <tr>
          <td><label for="email">Email</label></td>
          <td>
            <input type="email" name="email" id="email" v-model="formValue.email" placeholder="Enter your Email"/><br>
          </td>
        </tr>
        <tr>
          <td>
            <label for="phone">Phone</label>
          </td>
          <td>
            <input type="tel" name="phone" id="phone"  v-model="formValue.phone" placeholder="Enter your Phone"/><br>
          </td>
        </tr>
        <tr>
          <td><label for="skill">Skill</label></td>
          <td>
            <select name="skill" id="skill"  v-model="formValue.skill">
              <option v-for="skill in skills" value="skill" :key="skill">{{skill}}</option>
            </select>
          </td>
        </tr>
        <tr>
          <td><input type="checkbox" name="remote" id="remote" v-model="formValue.remote"/></td>
          <td><label for="remote">Open for Remote work</label></td>
        </tr>
        <tr>
          <td><label for="yoe">Year of Experience</label></td>
          <td>
            <div>
              <input type="radio" value="0-2"  v-model="formValue.yoe" > <label for="yoe">0-2</label>
              <input type="radio" value="3-5"  v-model="formValue.yoe" > <label for="yoe">3-5</label>
              <input type="radio" value="6-10" v-model="formValue.yoe" > <label for="yoe">6-10</label>
            </div>
            
           </td>
        </tr><tr>
          <td><button type="submit">Submit</button></td>
          <td><button type="reset">Reset</button></td>
        </tr>
      </table>
    
  </form>
  </div>


</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  data(){
    return{
      para:"Paragraph is fetched.",
      test1:'This is test 1',
      test2:'This is test 2',
      status:'danger',
      formValue:{
        name:'',
        email:'',
        phone:'',
        skill:'',
        yoe:'',
        remote:'' 
      },
      skills:["Angular","React","vue"]
    }

  },
  methods:{
    submitForm(event){
      event.preventDefault();
      console.log(this.formValue);
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.card{
  height: 400px;
  width: 600px;
  margin: auto;
  background-color: aquamarine;

}
.boder{
  border: 1px solid orange;
}
.success{
  text-align: center;
  color: green;
}
.danger{
  color: red;
  
}
</style>
