<template>
  <div id="app">
    <header>
      <div style="display:flex; flex-direction:row; justify-content: space-evenly;">
        <div style="display:flex; justify-content: flex-start; width: 600px;" ><img src="./assets/logo-blue.png" title="Logo" alt="Logo Pagina"></div>
        <nav style="display:flex; justify-content: flex-end;">
                <ul style="display:flex; justify-content: flex-end;list-style:none;">
                    <li>
                        <nav style="display:flex; justify-content: flex-end;">
                            <ul style = "text-align: center;list-style:none;display:flex; justify-content: space-evenly;">
                                <li class="item"><a>Home</a></li>
                                <li class="item"><a>Jobs</a></li>
                                <li class="item"><a>Courses</a></li>
                                <li class="item"><a>Questions</a></li>
                                <li class="item"><a>Teachers</a></li>
                                <li class="item"><a>For business</a></li>
                                <li class="item"><a>ES/EN</a></li>
                            </ul>
                        </nav>
                    </li>
                </ul>
            </nav>
      </div>
    </header>
    <div style ="background-color: blue;">
    <div style="display:flex; flex-direction:row; justify-content: space-evenly; text-align: center;">
        <div style="display:flex; justify-content: flex-start; width: 600px;" >
          <form id="form" style="display:flex; text-align: center; padding: 10px;">
            <input type="search" id="query" name="q" placeholder="Search..." style="width: 600px;border-radius: 10px;">

    </form>
</div>

        <nav style="display:flex; justify-content: flex-end;">
                <ul style="display:flex; justify-content: flex-end;list-style:none;">
                    <li>
                        <nav style="display:flex; justify-content: flex-end;">
                            <ul style = "text-align: center;list-style:none;display:flex; justify-content: space-evenly;">
                                <li class="item"><button style="border-radius: 10px;">Area</button></li>
                                <li class="item"><button style="border-radius: 10px;">Rol</button></li>
                                <li class="item"><button style="border-radius: 10px;">Salary</button></li>
                                <li class="item"><button style="border-radius: 10px;">Location</button></li>
                            </ul>
                        </nav>
                    </li>
                </ul>
            </nav>
          </div>
      </div>
      <section>
        <ul style="list-style:none">
          <li v-for="empleo in empleos" :key="empleo.id">
            <section style="padding:2rem; margin-right: 2rem;">
            <div style="display:grid; grid-template-columns: 1fr 4fr; border-style: inset;">
              <div><img v-bind:src="'./assets/' + empleo.imagen"></div>
              <div style="display:flex; flex-direction: column;">
                <div><div style="display:flex;"><h4>{{empleo.cargo}}</h4><div style ="display: flex; text-align: center;"><h6 style="margin-left:1rem; margin-top: 1rem; border-style: solid; border-width: 1px; border-radius: 15px; padding: 2px; font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;" v-for="cualidad in empleo.cualidades" :key="empleo.cualidades">{{cualidad}}</h6></div></div></div>
                <div style="display:flex; justify-content: flex-start;">
              <span class="caracteristica">{{empleo.info[0]}}</span>
              <span class="caracteristica">{{empleo.info[1]}}</span>
              <span class="caracteristica">{{empleo.info[2]}}</span>
              <span class="caracteristica">{{empleo.info[3]}}</span>
              <span style="margin-right: 5rem;">{{empleo.info[4]}}</span>
            </div>
          </div>
        </div>
      </section></li>
        </ul>
      </section>
    <HelloWorld msg="Welcome to Your Vue WORKSHOP4.js App"/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  },
  data(){
    return{
      empleos: [{imagen:"todoservy.jpg",cargo:"Bussiness Consultant", cualidades:["Excel Intermedio","Actitud"],info:["Excel Intermedio","Remote","1.2M -2 M","1 Job", "6 hours ago"],id : 2500},{imagen:"Evalueserve.jpg",cargo:"Full Stack" ,cualidades:["Excel Intermedio","Actitud","Excel Intermedio","Actitud"],info:["Excel Intermedio","Remote","1.2M -2 M","1 Job", "6 hours ago"], id : 2501},{imagen:"1651527124961.jpg",cargo:"Data Scientist" ,cualidades:["Excel Intermedio","Actitud"],info:["Excel Intermedio","Remote","5.2M -7 M","4 Job", "3 hours ago"], id : 2502},{imagen:"_Head_Hunter_logo.png",cargo:"SQL Developer" ,info:["Excel Intermedio","Remote","6.2M -8 M","2 Job", "8 hours ago"], id : 2503}]
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

.item{
  margin-right: 2rem;
}

.caracteristica{
  margin-right: 14rem;
}
</style>
