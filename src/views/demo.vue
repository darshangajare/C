<template>
<div id="app">
  <div id="upside">
    <h1 id="title"><b>Enter your data here</b></h1>
    <div id="inputt" class="inpt">
    <!-- <input type="number" id="id" placeholder="Enter your ID" v-model="id" /> -->
    <input type="text" id="name" placeholder="Enter your name" name="name" v-model="name" v-validate="'required'" />
    <input type="number" id="mb" placeholder="Enter your Phone number" v-model="mb"/>
    <input type="text" id="prof" placeholder="Enter your Profession" v-model="prof"/>
    </div>
    <button id="submt" v-on:click="onSubmit">Submit</button>
    </div>
    <div class="demo">
       <table id="firstTable">
  <thead>
    <tr>
      <th scope="col">ID</th>
      <th scope="col">Name</th>
      <th scope="col">Phone</th>
      <th scope="col">Profession</th>
    </tr>
  </thead>
   <tbody>
    <tr v-for="(entry,i) in alldata" :key='i'  v-bind="alldata"> 
     <th scope="row">{{++i}}</th>
      <!-- <td>{{row.id}}</td> -->
      <td>{{entry.name}}</td>
      <td>{{entry.mb}}</td>
      <td>{{entry.prof}}</td>
    </tr>
  </tbody>
</table>
</div>
</div>
</template>
<script>

export default{
  name : 'demo' ,
     data:() => ({name: "",mb:"",prof:"", alldata: [] }),
        methods: {
             onSubmit() {
                 this.alldata.push({name: this.name, mb :this.mb , prof: this.prof });
                 this.clearForm();
    },
    clearForm() {
        this.id= "";
        this.name = "";
        this.mb = "";
        this.prof = "" ; 
    },
  },
}
</script>


<style>
#upside{
  border: 2px solid cornflowerblue;
  width: 700px;
   margin-right: auto;
  margin-left: auto;
}
table {
  font-family: 'Open Sans', sans-serif;
  width: 750px;
  border-collapse: collapse;
  border: 3px solid #44475C;
  margin: 10px 10px 40px 10px;
  margin-right: auto;
  margin-left: auto;
}

table th {
  text-transform: uppercase;
  text-align: left;
  background: #44475C;
  color: #FFF;
  padding: 8px;
  min-width: 30px;
}

table td {
  text-align: left;
  padding: 8px;
  border-right: 2px solid #7D82A8;
}
table td:last-child {
  border-right: none;
}
table tbody tr:nth-child(2n) td {
  background: #D4D8F9;
}
#inputt [type=text],[type=number] {
    margin-right: auto;
    margin-left: auto;
    border:2px #44475C ;
    display: block;


}
#title{
  background-color: rgba(36, 172, 235, 0.527);
   margin: auto;
}
#submt{
  margin-bottom: 5px;
  width: 300px;
  border: 2px solid red;
  background-color: rgba(36, 172, 235, 0.527);
}
.inpt{
  
  margin-top: 20px;
  margin-bottom: 15px;
  
  width: 500px;
   margin-right: auto;
    margin-left: auto;
}

</style>