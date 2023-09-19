<template>
  <div class="window">
    <div class="header">
      <img src="@/assets/images/logo.svg" class="logo">
      <div class="nav-link">
        <div>Home</div>
        <div>New</div>
        <div>Popular</div>
        <div>Trending</div>
        <div>Categories</div>
      </div>
      <span class="material-icons menu" v-on:click="showMenu()">
        menu
      </span>
      <div class="sidebar-mobile" :style="sideBarMenu()">
        <span class="material-icons close" v-on:click="closeMenu()">
          close
        </span>
        <div>Home</div>
        <div>New</div>
        <div>Popular</div>
        <div>Trending</div>
        <div>Categories</div>
      </div>
    </div>
    <div class="body">
      <div>
        <img src="@/assets/images/image-web-3-desktop.jpg" class="banner">
        <img src="@/assets/images/image-web-3-mobile.jpg" class="banner-mobile">
        <div class="main-container">
          <div class="article">
            The Bright Future of Web 3.0?
          </div>
          <div class="content-article">
            We dive into the next evolution of the web that claims to put power of the platforms back into the hands of
            the peoplee. But is it really fulfilling its promise?
            <button>
              READ MORE
            </button>
          </div>
        </div>
      </div>
      <div class="conteiner-new">
        <div class="title">
          New
        </div>
        <div class="subtitle">
          Hydrogen VS Eletric Cars
        </div>
        <div class="text">
          Wll hydrogen-fueled cars ever catch up to EVs?
        </div>
        <div class="separation"></div>
        <div class="subtitle">
          The Downsides of AI Artistry
        </div>
        <div class="text">
          What are the possivle adverse effects of on-demand Ai image generation?
        </div>
        <div class="separation"></div>
        <div class="subtitle">
          Is VC Funding Drying Up?
        </div>
        <div class="text">
          Private funding by VC firms is down 50% YOY. We take a look at what that means.
        </div>
      </div>
    </div>
    <div class="mini-cards">
      <div class="card">
        <img src="@/assets/images/image-retro-pcs.jpg">
        <div class="card-content">
          <div class="card-number">
            01
          </div>
          <div class="card-title">
            Reviving Retro PCs
          </div>
          <div class="card-text">
            What happens when old PCs are given modern upgrades?
          </div>
        </div>
      </div>
      <div class="card">
        <img src="@/assets/images/image-top-laptops.jpg">
        <div class="card-content">
          <div class="card-number">
            02
          </div>
          <div class="card-title">
            Top 10 Laptops of 2022
          </div>
          <div class="card-text">
            Our best picks of various needs and budgets.
          </div>
        </div>
      </div>
      <div class="card">
        <img src="@/assets/images/image-gaming-growth.jpg">
        <div class="card-content">
          <div class="card-number">
            03
          </div>
          <div class="card-title">
            The Growth of Gaming
          </div>
          <div class="card-text">
            WHow the pandemic has sparked fresh opportunities.
          </div>
        </div>
      </div>
    </div>
    <div class="darken" v-if="menu === true">
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      menu: false
    }
  },
  methods: {
    showMenu() {
      this.menu = true
    },
    sideBarMenu() {
      if (this.menu === true) {
        return "display:block;height: 100%;display: flex;flex-direction: column; gap: 3vh; position: absolute; right: 0;top: 0;width: 50%;background-color: white;padding: 15vh 5vw;font-size: 2.5em; user-select:none;z-index: 2; box-sizing: border-box; "
      }
    },
    closeMenu(){
      this.menu = false
    }
  }
}
</script>
<style>
body {
  margin: 0;
  
}
.window {
  font-family: 'Inter', sans-serif;
  padding: 5vw 7vw;
  font-size: 1vw;
  position: relative;
}
.darken {
  position: absolute;
  background-color: rgba(0,0,0,0.7);
  width: 100%;
  height: 100%;
  top: 0;
  left: 0;
  z-index: 1;
}
.logo {
  width: 5em;
}

.header {
  color: gray;
  display: flex;
  justify-content: space-between;
  margin-bottom: 3vw;
  align-items: center;
}

.nav-link {
  display: flex;
  gap: 2vw;
  cursor: pointer;
  font-size: 1rem;
}

.sidebar-mobile {
  display: none;
}

.nav-link div:hover {
  color: red;
}

.menu {
  display: none;
}

.body {
  display: flex;
  gap: 2vw;
}

.banner {
  width: 100%;
}

.banner-mobile {
  display: none;
}

.main-container {
  display: flex;
  justify-content: space-between;
  margin-top: 3vh;
}

.article {
  font-size: 3.1em;
  color: rgb(11, 1, 32);
  font-weight: bolder;
  width: 35%;
  margin-right: 5vw;
}

.content-article {
  width: 50%;
  display: flex;
  flex-direction: column;
}

button {
  background-color: rgb(11, 1, 32);
  color: white;
  margin-top: 6vh;
  padding: 2vh 2vw;
  width: fit-content;
  border: none;
  letter-spacing: 2px;
  cursor: pointer;
  font-family: 'Inter', sans-serif;
}

button:hover {
  background-color: rgb(241, 96, 91);
  transition: ease-in-out 200ms;
}

.conteiner-new {
  background-color: rgb(11, 1, 32);
  padding: 3vh 2vw;
  display: flex;
  flex-direction: column;
  gap: 2vh;
}

.title {
  font-size: 2.5em;
  font-weight: bolder;
  color: rgb(240, 193, 65);
  margin-bottom: 1vh;
}

.subtitle {
  font-size: 1.5em;
  font-weight: bold;
  color: white;
  cursor: pointer;
  transition: ease-in-out 200ms;
}

.subtitle:hover {
  color: rgb(240, 193, 65);
  transition: ease-in-out;
}

.text,
.content-article {
  font-size: 1em;
  color: rgb(131, 128, 128);
  letter-spacing: 1px;
  line-height: 1.5em;
}

.separation {
  border: 1px solid gray;
  width: 100%;
  margin: 2vh 0;
}

.mini-cards {
  display: flex;
  gap: 3vw;
  margin-top: 7vh;
  height: 20vh;

}

.card {
  display: flex;
  gap: 1vw;
  width: 30%;
}

.card-content {
  display: flex;
  flex-direction: column;
  justify-content: space-around;
}

.card-number {
  color: rgb(185, 185, 185);
  font-size: 2em;
  font-weight: bold;
}

.card-title {
  font-size: 1.5em;
  color: rgb(11, 1, 32);
  font-weight: bold;
  margin: 1vh 0;
  cursor: pointer;
}

.card-title:hover {
  color: rgb(241, 96, 91);
  transition: ease-in-out;
}

.card-text {
  font-size: 1em;
  color: rgb(131, 128, 128);
  letter-spacing: 1px;
  line-height: 1.5em;
}

@media screen and (max-width:1000px) {
  .nav-link {
    display: none;
  }

  .window {
    font-size: 2vw;
    padding: 3vw;
  }

  .menu {
    display: block;
    color: black;
    font-size: 5em;
    user-select: none;
  }

  .banner {
    display: none;
  }

  .banner-mobile {
    display: block;
    width: 100%;
  }
  .close {
    position: absolute;
    top: 0;
    right: 0;
    font-size: 2.5em;
    margin: 2vh 1vw;
  }
  
  .body {
    flex-direction: column;
  }

  .main-container {
    flex-direction: column;
    gap: 2vh;
  }

  .article,
  .content-article {
    width: 100%;
  }

  .article {
    font-size: 6em;
    line-height: 1em;
  }

  .content-article {
    font-size: 2em;
  }

  button {
    background-color: rgb(241, 96, 91);
    font-family: 'Inter', sans-serif;
    width: 50vw;
    margin-bottom: 5vh;
  }

  .conteiner-new {
    padding: 2vh 3vh;
  }

  .subtitle {
    font-size: 2.5em;
  }

  .text {
    font-size: 2em;
  }

  .mini-cards {
    flex-direction: column;
    height: fit-content;
  }

  .mini-cards img {
    max-height: 20vh;
  }

  .card {
    width: 100%;
    gap: 5vw;
  }

  .card-number {
    font-size: 4.1em;
  }

  .card-title {
    font-size: 2.2em;
  }

  .card-text {
    font-size: 1.8em;
  }
}</style>