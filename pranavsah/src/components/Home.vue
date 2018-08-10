<template>
  <body>
    <div class="wrapper">
      <header>
        <nav id="nav">
          <div class="menu-icon" @click="toggle">
            <i class="fa fa-cloud"></i>
          </div>
          <div class="logo">
            LOGO
          </div>
          <div class="menu">
            <ul id="ul">
              <li><a href="#" @click="home">Home</a></li>
              <li><a href="#" @click="about">About me</a></li>
              <li><a href="#" @click="projects">Projects</a></li>
            </ul>
          </div>
        </nav>
      </header>
      <div class="techstackContainer">
        <h2 class="techstackTitle">Theck stack I dabble with</h2>
        <!-- <p class="techstackDescription">Blah Blah Blah Blah Blah Blah Blah Blah </p> -->
        <div class="techstack">
          <img src="../assets/techstack/techstack1.jpg" alt="techstack 1">
          <img src="../assets/techstack/techstack2.jpg" alt="techstack 2">
          <img src="../assets/techstack/techstack3.jpg" alt="techstack 3">
          <img src="../assets/techstack/techstack4.jpg" alt="techstack 4">
        </div>
      </div>
      <footer>
        <p>ASHARPVAN &copy;</p>
      </footer>
    </div>
  </body>
</template>

<script>
export default {
  methods: {
    handleScroll: function (event) {
      if (window.scrollY > window.screenTop) {
        document.getElementById('nav').classList.add('black')
      } else {
        document.getElementById('nav').classList.remove('black')
      }
    },
    toggle: function (click) {
      document.getElementById('ul').classList.toggle('showing')
    },
    home: function (click) {
      console.log('Clicked on Home')
      document.getElementById('ul').classList.toggle('showing')
    },
    about: function (click) {
      console.log('Clicked on About')
      document.getElementById('ul').classList.toggle('showing')
      // setTimeout(this.about, 1000)
      console.log('transition complete')
    },
    projects: function (click) {
      console.log('Clicked on Projects')
      document.getElementById('ul').classList.toggle('showing')
      // This works!!
      // this.$router.push({name: 'projects'})
    }
  },
  created: function () {
    window.addEventListener('scroll', this.handleScroll)
  },
  destroyed: function () {
    window.removeEventListener('scroll', this.handleScroll)
  }
}
</script>

<style>
html, body {
  margin: 0;
  padding: 0;
  width: 100%;
}

body {
  background-color: #0e0e0e;
}

header {
  width: 100%;
  height: 100vh;
  background: url('../assets/techstack/techstack3.jpg') no-repeat 50% 50%;
  background-size: cover;
}

.logo {
  position: fixed;
  float: left;
  margin: 16px 16px;
  color: #ffffff;
  font-weight: bold;
  font-size: 24px;
}
nav {
  position: fixed;
  width: 100%;
}
nav ul {
  list-style: none;
  background: rgba(0, 0, 0, 0);
  overflow: hidden;
  color: #ffffff;
  padding: 0;
  text-align: center;
  margin: 0;
  transition: 1s;
}
nav.black ul {
  background: #000;
}
nav ul li {
  display: inline-block;
  padding: 20px;
}
nav ul li a {
  text-decoration: none;
  color: #ffffff;
  font-size: 20px;
}
.menu-icon {
  width: 100%;
  background: #000;
  text-align: right;
  box-sizing: border-box;
  padding: 15px 24px;
  cursor: pointer;
  color: #ffffff;
  display: none;
}

.techstackContainer {
  width: 95%;
  margin: auto auto;
  text-align: center;
  /* background-color: #293042; */
}

.techstackTitle {
  font-size: 48px;
  margin: 40px auto;
  /* background-color: yellow; */
}

/* .techstackDescription {
  font-size: 16px;
  margin: .75em auto;
  font-weight: 300;
  background-color: blue;
} */

.techstack {
  text-align: center;
  width: 100%;
}

.techstack img {
  margin: 1%;
  width: 45%;
  /* height: 45%; */
  background-color: blue;
}

footer p {
  text-align: center;
  margin: 20px auto;
  color: grey;

}

@media (max-width: 580px) {
  .logo {
    position: fixed;
    top: 0;
    margin-top: 10px;
  }
  nav ul {
    max-height: 0px;
    background: #000;
  }
  nav.black ul {
    background: #000;
  }
  .showing {
    max-height: 20em;
  }
  nav ul li {
    box-sizing: border-box;
    width: 100%;
    padding: 24px 0;
    text-align: center;
  }
  .menu-icon {
    display: block;
  }

  .techstackTitle {
  font-size: 24px;
  margin: 20px auto;
  /* background-color: yellow; */
}

/* .techstackDescription {
  font-size: 12px;
  margin: .75em auto;
  font-weight: 300;
  background-color: blue;
} */
}
</style>
