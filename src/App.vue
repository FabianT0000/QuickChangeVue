
<template>

<nav class="navbar navbar-expand-lg bg-body-tertiary">
  <div class="container-fluid">
    <router-link to="/" class="nav-link active" aria-current="page">
     
      <img alt="reload" src="./assets/Logoquick.png">
  
    </router-link> 
   
    <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button>
    
    <div class="collapse navbar-collapse" id="navbarSupportedContent">
      <ul class="navbar-nav me-auto mb-2 mb-lg-0">
        <!-- <li class="nav-item">
          <router-link to="/" class="nav-link active" aria-current="page">Hombres</router-link> 
          
        </li> -->
        <li class="nav-item dropdown">
         
            <router-link to="/" class="nav-link dropdown-toggle" href="#" role="button" data-bs-toggle="dropdown" aria-expanded="false">Hombres</router-link> 
        
          <ul class="dropdown-menu dropdown-menu-dark">
            <li>
              <router-link to="/jeans" class="dropdown-item" aria-current="page">Jean</router-link> 
            </li>
            <li><a class="dropdown-item" href="#">Another action</a></li>
            <li><hr class="dropdown-divider"></li>
            <li><a class="dropdown-item" href="#">Something else here</a></li>
          </ul>
        </li>
        <li class="nav-item">
          <router-link to="/about" class="nav-link">Mujeres</router-link>
          <!-- <a class="nav-link" href="#">Link</a> -->
        </li>
        <li class="nav-item">
          <router-link to="/about" class="nav-link">Ofertas</router-link>
          <!-- <a class="nav-link" href="#">Link</a> -->
        </li>
        <li class="nav-item">
          <router-link to="/estudiantes" class="nav-link">Estudiante</router-link>
         
        </li>
        <li class="nav-item">
          
          <!-- <a class="nav-link" href="#">Link</a> -->
        </li>
        <!-- <li class="nav-item dropdown">
          <a class="nav-link dropdown-toggle" href="#" role="button" data-bs-toggle="dropdown" aria-expanded="false">
            Dropdown
          </a>
          <ul class="dropdown-menu dropdown-menu-dark">
            <li><a class="dropdown-item" href="#">Action</a></li>
            <li><a class="dropdown-item" href="#">Another action</a></li>
            <li><hr class="dropdown-divider"></li>
            <li><a class="dropdown-item" href="#">Something else here</a></li>
          </ul>
        </li> -->
        <!-- <li class="nav-item">
          <a class="nav-link disabled" aria-disabled="true">Disabled</a>
        </li> -->
      </ul>
      <form class="d-flex" role="search">
        <input class="form-control me-2" type="search" placeholder="Buscar" aria-label="Search">
        <button class="btn btn-outline-success" type="submit">Buscar</button>
      </form>
      <ul id="ul-img">
        <li >
          <router-link to="/registro" class="nav-link"> <img src="./assets/adduser.png" alt="" id="adduser"> </router-link>
        </li>
        <li>
          <!-- <button type="button" class="btn btn-primary btn-sm" id="eliminar" name="eliminar" > <router-link to="/login" >Login</router-link> </button> -->
       
          <router-link to="/login" class="nav-link">Login</router-link>
        </li>
      </ul>
   
    </div>
  </div>
</nav>

 
  
  <router-view/>
  
</template>






<style>

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}
#adduser{
  width: 50%;
  margin-left: -5%;

}
.btn.btn-primary.btn-sm{
  color:rgb(253, 252, 252);
  background-color: rgb(107, 107, 219);

margin-left:-40% ;
}
#ul-img{
  list-style: none ;
  display: inline;
  width: 8%;
  align-items: center ;
  margin-left: -2%;
  margin-top: 10px;
  
}
</style>
