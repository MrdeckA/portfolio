<template>
  <div>
    <header>
      <nav class="navigation-bar">
        <h1><a href="#">MERIDEV</a></h1>
        <ul class="navLinks">
          <li class="active"><a href="#" class="actives">HOME</a></li>
          <li><a href="#">ABOUT</a></li>
          <li><a href="#">SERVICES</a></li>
          <li><a href="#">PORTFOLIO</a></li>
          <li><a href="#">BLOG</a></li>
          <li><a href="#">CONTACT</a></li>
        </ul>
        <img
          id="hamburger"
          src="../assets/files/menu_black_24dp.svg"
          alt="button-hamburger"
          class="hamburger"
        />
        <div  id="items" class="menu-hamburger">
          <ul>
          <li><a class="activeNav" href="#">HOME</a></li>
          <li><a href="#">ABOUT</a></li>
          <li><a href="#">SERVICES</a></li>
          <li><a href="#">PORTFOLIO</a></li>
          <li><a href="#">BLOG</a></li>
          <li><a href="#">CONTACT</a></li>
        </ul>
        </div>
      </nav>
      <section>
        <div class="styled">
          <div class="header-content">
            <h1>Hello ! My name is Mériadeck AMOUSSOU</h1>
            <span class="welcome centered">I'm a </span><span id="typed" class="my-4 h2 fw transform centered welcome1"></span><span id="space"></span>

            
            <div class="pt-5">
              <v-btn color="primary" class="bg-primary text-light animatedButton"
              >me connaitre</v-btn
            >
            </div>
          </div>
          <div>
            <img class="profil-picture" src="../assets/images/vue-color-avatar.png" alt="my-picture" />
          </div>
        </div>
      </section>
    </header>
    <!--
      <section>
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Reiciendis quo
      provident esse porro quod tempore, amet ut nobis nisi? Pariatur distinctio
      ratione dolorem iste provident nam quisquam mollitia voluptatibus culpa.
      Lorem ipsum dolor, sit amet consectetur adipisicing elit. A, accusamus
      corrupti. Cumque, tenetur deserunt sint mollitia quisquam praesentium
      consectetur vitae quas animi soluta doloribus provident modi aspernatur
      debitis qui ab. Lorem ipsum dolor sit amet consectetur adipisicing elit.
      Aperiam iusto asperiores, quia itaque et expedita ullam eveniet quasi
      voluptates? Illo deleniti minima officia praesentium modi ea, ratione
      adipisci natus placeat! Lorem, ipsum dolor sit amet consectetur
      adipisicing elit. Voluptatem eum velit tempore dolorum saepe sint
      excepturi, consequuntur recusandae quo et sapiente quia nisi. Odit aut
      vitae repudiandae saepe, velit minima?
      <h1>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Perferendis
        officia non cumque ipsa, hic optio ipsum quae odit tenetur impedit, iste
        voluptatem eius possimus porro quasi. Fugiat aliquid voluptate cum?
      </h1>
    </section>
    -->

  </div>
</template>
<script>
export default {
  data(){
    return{
      sets: 2
    }
  },
  mounted() {
    this.iterating(`Web Developper`.toUpperCase());
    const hamburger = document.getElementById('hamburger')
    const items = document.getElementById('items')
    hamburger.addEventListener('click', () => {
      items.classList.toggle('displayed')
      hamburger.classList.toggle('hamburger-border')
    })
  },
   methods: {
    iterating(iterating) {
      let i = 0
      let chaine = ''

      setInterval(() => {
        if (i < iterating.length) {
          chaine = chaine + iterating[i]
          document.getElementById('typed').innerHTML = chaine
          i++
        } else {
          if(this.sets===1){
            iterating=(`Web Developper`.toUpperCase())
            this.sets=2
          }
          else if(this.sets===2){
            iterating=(`Mobile Developper`.toUpperCase())
            this.sets=3
          }
          else if(this.sets===3){
            iterating=(`Full Stack Javascript Developper`.toUpperCase())
            this.sets=1
          }
          chaine=''
          i = 0
        }
      }, 400)
    },
  },
}
</script>
<style scoped>
header {
  width: 100%;
  height: 100vh;
  background-image: url('@/assets/images/bg-gradient.jpg');
  background-size: cover;
  font-family: ui-sans-serif, system-ui, -apple-system, BlinkMacSystemFont,
    Segoe UI, Roboto, Helvetica Neue, Arial, Noto Sans, sans-serif,
    Apple Color Emoji, Segoe UI Emoji, Segoe UI Symbol, Noto Color Emoji;
  color: white;
}

header section {
  position: relative;
  top: 3em;
}

.navigation-bar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1em 3em;
  height: 6em;
}

.navLinks {
  list-style-type: none;
  display: flex;
}

.navLinks li {
  margin-left: 3em;
}
.navLinks li a {
  color: white;
  text-decoration: none;
}

.navLinks li :hover {
  background-color: white;
  color: black;
  padding: 0.5em 2em;
  transition: all 0.5s ease;
  border-radius: 2em;
}

h1 a {
  color: gold;
  text-decoration: none;
}

.styled {
  align-items: center;
  align-content: center;
  width: 90%;
  margin: auto;
  display: flex;
}
.header-content {
  margin-right: 1em;
  text-align: center;
  width: 70%;
}
.hamburger {
  display: none;
}

.menu-hamburger {
  display: none;
}

.transform{
  text-transform: uppercase;
}

.fw{
  font-weight: 400;
  color: rgb(125, 158, 249);
}

@keyframes discorverMe {
  0% {
    position: relative;
    top: 0.5em
  }
  
  50% {
    position: relative;
    top: 1em;
  }
  100% {
    position: relative;
    top: 0em;
  }
}

.animatedButton{
  animation-name: discorverMe;
  animation-duration: 2s;
  animation-iteration-count: infinite;
  animation-timing-function: linear;
  
}


.header-content h1{
  font-weight: normal;
}

@media screen and (max-width: 960px) {
  .navLinks {
    display: none;
  }
  .hamburger {
    display: block;

    
  }

  .hamburger-border{
    border-style: groove;
    border-radius: 1em;
    border-width: 1px;
  }
  .menu-hamburger {
    display: block;
    position: absolute;
    top: 6em;
    left: 0;
    z-index: 1;
    width: 100%;
    height: calc(100vh - 6em);
    margin-left: -100%;
    transition: 0.5s ease;
    justify-content: center;
    justify-items: center;
    align-items: center;
    align-content: center;
    backdrop-filter: blur(25px);
 
  }
  
  

  .displayed {
    margin-left: 0;
    transition: 0.5s ease;
  }
.menu-hamburger ul{
  display: flex;
  flex-direction: column;
  list-style-type: none;
  align-items: center;
 

}

.menu-hamburger ul li{
  margin: 1.5em 0;
  box-shadow: inset 0 0 1em gold, 0 0 2em red;

}

.menu-hamburger ul li a {
  background-color: white;
  color: black;
  padding: 0.5em 2em;
  transition: all 0.5s ease;
  border-radius: 2em;
  text-decoration: none;
    box-shadow: inset 0 0 1em gold;

  
}
.menu-hamburger ul li a:hover{
  background-color: red;
  transition: 1s ease;
  
}

}

.centered {

  font-size: 2em;
}

.welcome{
  color: yellow
}
.welcome1{
  color: blue
}

.profil-picture{
  padding-bottom: 5em;
}

#space {
  padding: 0.4em 0.3em;
  background-color: white;
  animation-name: anim;
  animation-duration: 300ms;
  animation-iteration-count: infinite;
  animation-timing-function: linear;
}

@keyframes anim {
  0% {
    background-color: black;
  }
  100% {
    background-color: white;
  }
}
</style>
