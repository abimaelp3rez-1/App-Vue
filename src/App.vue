<script setup>
// Importams el componente btnOpciones.vue
import btnOpciones from './components/btnOpciones.vue'
import { ref } from 'vue'; 


</script>

<template>
    <section id="contenedor">

      <header id="header">
        <img src="" alt="">

        <h1>Frameworks</h1>

        <ul>

          <li>
            <a href="#">Nuevo usuario</a>
          </li>

          <li>
            <a href="#">Bitacora</a>
          </li>

        </ul>

      </header>
    
      
      <section id="main">

        <section id="info">
          <h2>Datos</h2>
          <div>
           <table>
              <thead>
                  <tr>
                    <th>Juan</th>
                    <th>Perez</th>
                  </tr>
              </thead>
            
             <tbody>
              <tr>
                <td>Edad: 30</td>
                <td>Sexo: Masculino</td>
              </tr>
             </tbody>
           </table>
          </div>
        </section>

        <section>
          <btnOpciones />

        </section>


      </section>

      <section id="footer">
       
      </section>
      
    </section>
    
</template>

<style>

*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

#contenedor{
  background-color: rgb(102, 102, 233);
  width: 100%;
  height: 100vh;
  display: flex;
  flex-direction: column;

}

header{
  background-color: rgb(255, 255, 255);
  height: 100px; 
  display: flex;
  flex-direction: horizontal;
  justify-content: space-between;
  border: 3px solid blue;
}

#main{
  background-color: green;
  height: 100%;
  display: grid;
  grid-template-columns: 80% 1fr;
}


#footer{
  background-color: darkorange;
  height: 30px;
  border: 3px solid blue;
}

#info{
  padding: 20px;
}

#info div{
  width: 80%;
  height: 60%;
  background-color: rgb(243, 113, 239);
  border: 3px solid blue;
}
</style>