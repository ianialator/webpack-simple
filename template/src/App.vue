<template>
  <div id='app'>
    <img src="./assets/logo.png">
    <h1>Could you...</h1>
    <p>{{ prompt }}</p>
    <div id='voter'>VOTER</div>
  </div>
</template>

<script>
export default {
  name: 'Youdo',
  data () {
    return {
      prompt: ''
    }
  }
  methods () {
    return {
      getPrompt: function () {
        <!-- make variables of all the word lists from the files -->
        function csvJSON(csv){
          var lines=csv.split("\n");
          var result = [];
          var headers=lines[0].split(",");
          for(var i=1;i<lines.length;i++){
              var obj = {};
              var currentline=lines[i].split(",");
              for(var j=0;j<headers.length;j++){
                  obj[headers[j]] = currentline[j];
              }
              result.push(obj);
          }
          //return result; //JavaScript object
          return JSON.stringify(result); //JSON
        }
        <!-- make the prompt out of the words and return the prompt -->
      }
    }
  }
}


</script>

<style{{#sass}} lang="scss"{{/sass}}>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
