<template>
  <div class="home">
  <body>
     <header>
        <img src="../Logos+icons/TopPage.png" alt="Ezezimali logo" id="larger-banner-logo" style="width: 300px; height: auto;">
        <nav>
           
            <a href="#">Account</a>
        </nav>
    </header>
    
  </body>
    <HelloWorld msg="Welcome to Your Vue.js App"/>

  </div>
  <footer>
        <p>&copy; Ezezimali - Invest in you</p>
    </footer>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'HomeView',
  components: {
    HelloWorld
  }
}
</script>
<style>
#larger-banner-logo {
  width: 800px;
  
  
}
body {
    background-color: #e0f7fa;
    color: #00695c;
    font-family: Arial, sans-serif;
   
    display: flex;
    flex-direction: column;
    margin-bottom: 20px;
  
}

header {
    background-color: #80cbc4;
    padding: 10px;
    display: flex;
    align-items: center;
    justify-content: space-between;
}

header img#larger-banner-logo {
    width: 35%;
    max-height: 80px; /* Adjust this value to control the height of the logo */
    /*object-fit: contain; /* This will ensure the logo maintains its aspect ratio */
}
footer {
    background-color: #80cbc4;
    padding: 20px;
    text-align: center;
    color: #004d40;
}
</style>
