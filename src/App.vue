<template>
  <!-- <nav>
    <router-link to="/">List</router-link> |
    <router-link to="/about">About</router-link>
  </nav> -->
  <router-view/>
</template>
<script>
export default {
  name: "app",
  data() {
    return {
      storageModified: false
    }
  },
  watch: {
    storageModified() {
      vm.$forceUpdate();
      alert("atualizou");
    }
  }
}
</script>
<style>
#app {
  font-family: 'Saira', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.card-shadow {
  -webkit-box-shadow: 4px 4px 15px 0px rgba(204,204,204,0.43);
  -moz-box-shadow: 4px 4px 15px 0px rgba(204,204,204,0.43);
  box-shadow: 4px 4px 15px 0px rgba(204,204,204,0.43);
}

.text-green {
  color: #42b983;
}

.text-red {
   color:rgb(253, 121, 97);
}

.bg-green {
  background-color: #42b983;
}

.text-bold {
  font-weight: 600;
}

.text-semibold {
  font-weight: 500;
}

.form-check input {
  display: none;
}

.form-check input + label:before {
  content: '';
  width: 16px;
  height: 16px;
  border-radius: 50%;
  background-color: white;
  border: 1px solid gray;
  display: inline-block;
  vertical-align: middle;
  margin-right: 8px;
  margin-bottom: 3px;
}

.form-check input:checked + label:before {
  background-color: white;
  box-sizing: border-box;
  border: 5px solid #42b983;
  padding: 4px;
}

.btn-green{
  color:white !important;
  background-color: #42b983 !important;
}

.btn-red {
  color:white !important;
  background-color: rgb(253, 121, 97) !important;
}

.revevue {
  border-right: 5px solid #42b983;
}

.expense {
  border-right: 5px solid rgb(253, 121, 97);
}

.swal2-popup {
  font-family: 'Saira', sans-serif !important;
  -webkit-font-smoothing: antialiased !important;
  -moz-osx-font-smoothing: grayscale !important;
  text-align: center !important;
  color: #2c3e50 !important;
}
.swal2-success-ring {
  color: #42b983 !important;
}
.swal2-styled {
  background-color: #42b983 !important;
  border-color: transparent !important;
  box-shadow: none !important;
  text-shadow: none !important;
}
.swal2-styled:hover {
  background-color: #42b280 !important;
}
</style>
