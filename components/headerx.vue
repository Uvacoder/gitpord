<template>
  <div>
    <div class="hero1">
      <div id="inner-wrapper">
        <img id="logo" src="~/static/github-logo.png" alt="boy" />

        <div id="input-cover">
          <input
            type="text"
            id="search-input"
            placeholder="Search or jump to..."
          />
          <button id="input-btn">/</button>
        </div>

        <ul id="links-one">
          <li>Pull requests</li>
          <li>Issues</li>
          <li>Marketplace</li>
          <li>Explore</li>
        </ul>

        <div id="place-holder-bnt">
          <ul id="btns-one">
            <li>
              <button><span class="mdi mdi-bell-outline"></span></button>
              <button>
                <span class="mdi mdi-plus"></span>
                <span class="mdi mdi-chevron-down"></span>
              </button>
              <button>
                <img src="~/static/profile.jpg" alt="" />
                <span class="mdi mdi-chevron-down"></span>
              </button>
            </li>
          </ul>
        </div>
      </div>
    </div>
    <div id="header">
      <div id="clear"></div>
      <ul id="page-tabs">
        <li>
          <button class="tabb">
            <span class="mdi mdi-book-open-variant"></span> Overview
          </button>
        </li>

        <li>
          <button class="tabb active-tab">
            <span class="mdi mdi-book-play-outline"></span> Repositories
          </button>
        </li>

        <li>
          <button class="tabb">
            <span class="mdi mdi-graph-outline"></span> Projects
          </button>
        </li>

        <li>
          <button class="tabb">
            <span class="mdi mdi-package-variant"></span> Packages
          </button>
        </li>
      </ul>

      <div id="image-switch"></div>
    </div>

    <div id="hero2">
      <div id="actns-wrapper">
        <button id="menu-btn"><span class="mdi mdi-menu"></span></button>

        <img id="logo" src="~/static/github-logo.png" alt="" />

        <button id="alert-btn">
          <span class="mdi mdi-bell-outline"></span>
        </button>
      </div>
      <div id="menu-extension">
        <div id="input-cover2">
          <input
            type="text"
            id="search-input2"
            placeholder="Search or jump to..."
          />
          <button id="input-btn">/</button>
        </div>

        <ul id="small-navigation">
          <li>Dashboard</li>
          <li>Pull requests</li>
          <li>Issues</li>
          <li>Marketplace</li>
          <li>Explore</li>
          <li>Settings</li>
          <li><img src="~/static/profile.jpg" alt="" /> Xceldeveloper</li>
          <li><span class="mdi mdi-logout"></span> Sign out</li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      showmenu: false,
    };
  },
  mounted() {
    var h = document.getElementById("header");
    //  var readout = document.getElementById("readout");
    var stuck = false;
    var stickPoint = getDistance();

    function getDistance() {
      var topDist = h.offsetTop;
      return topDist;
    }

    window.onscroll = function (e) {
      var distance = getDistance() - window.pageYOffset;
      var offset = window.pageYOffset;
      // readout.innerHTML =
      //   stickPoint + "   " + distance + "   " + offset + "   " + stuck;
      if (distance <= 0 && !stuck) {
        h.style.position = "fixed";
        h.style.top = "0px";
        stuck = true;
      } else if (stuck && offset <= stickPoint) {
        h.style.position = "static";
        stuck = false;
      }
    };

    var smheader = document.getElementById("hero2");
    var menubtn = document.getElementById("menu-btn");
    var menucont = document.getElementById("menu-extension");
    menubtn.addEventListener("click", () => {
      if (!this.showmenu) {
        this.showmenu = true;
        smheader.style.height = "465px";
        menucont.style.display = "block";
      } else {
        this.showmenu = false;
        smheader.style.height = "63px";
        menucont.style.display = "none";
      }
    });
  },
};
</script>

<style scoped>
.hero1 {
  height: 63px;
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: #161b22;
}
#inner-wrapper {
  height: 34px;
  display: flex;
  width: 100%;
  overflow: auto;
}

#logo {
  height: 100%;
  width: 30px;
  margin: 0px 15px 0px 30px;
}

#input-cover {
  background-color: #0d1117;
  height: 29px;
  padding: 0px 8px;
  border: 0.5px solid #393c41;
  border-radius: 30px;
  width: auto;
  margin: 2px 0px;
}

#search-input {
  outline-style: none;
  height: 100%;
  width: 272px;
  color: #fff;
  border: none;
  padding: 3px;
  background-color: transparent;
  transition: ease-in 0.3s all;
}

#search-input:focus {
  width: 450px;
}

#input-cover:hover {
  border: 0.5px solid #b1b1b1;
}

#input-btn {
  background-color: transparent;
  border: 0.5px solid #393c41;
  color: #393c41;
  border-radius: 13px;
  height: 18px;
  width: 18px;
}

#links-one {
  padding: 0px;
  margin: 0px 10px;
  list-style-type: none;
  color: #fff;
  white-space: nowrap;

  display: flex;
  align-items: center;
  justify-content: center;
}

#links-one li {
  margin: 0px 5px;
  display: inline-block;
  font-size: 14px;
  color: #fff;
}

#links-one li:hover {
  color: lightgrey;
  cursor: pointer;
}

#place-holder-bnt {
  height: 100%;
  flex: 1;
  width: 100px;
  text-align: right;
  padding-right: 20px;
}

#btns-one {
  padding: 0px;
  margin: 0px;
  list-style-type: none;
  white-space: nowrap;
}

#btns-one li button {
  background-color: transparent;
  border: none;
  display: inline-block;
  outline-style: none;
  color: #c9d1d9;
  height: 100%;
  font-size: 18px;
  word-spacing: 0px;
}

#btns-one li button img {
  height: 17px;
  width: 17px;
  border-radius: 50%;
}

#btns-one li button:hover {
  color: #b1b1b1;
  cursor: pointer;
}

#header {
  height: 74px;
  display: block;
  background-color: #0d1117;
  width: 100%;
  border-bottom: 0.5px solid #393c41;
  z-index: 90;
  position: relative;
}

#clear {
  height: 38px;
}

#page-tabs {
  padding: 0px;
  margin: auto;
  white-space: nowrap;
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100%;
  max-width: 500px;
}

#page-tabs li {
  display: inline-block;
  width: 25%;
}

.tabb {
  background: transparent;
  color: #616972;
  height: 35px;
  width: 100%;

  font-size: 12px;
  border: none;
  outline-style: none;
}

.tabb:hover {
  color: #c9d1d9;
  font-size: 14.5px;
  cursor: pointer;
  border-bottom: 1px solid lightgrey;
}

.active-tab {
  color: #fff;
  font-size: 15px;
  border-bottom: 1px solid #fff;
}

#image-switch {
  width: 200px;
  height: 74px;
  background-color: red;
  position: absolute;
  right: 100px;
  bottom: 0px;
  display: none;
}

@media only screen and (min-device-width: 768px) {
  #hero2 {
    display: none;
  }
}

@media only screen and (max-device-width: 767px) {
  #header,
  .hero1 {
    display: none;
  }

  #hero2 {
    width: 100%;
    height: 63px;
    margin-bottom: 5px;
    background-color: #161b22;
    transition: ease-in 0.4s all;
  }

  #menu-btn {
    width: 40px;
    height: 40px;
    background-color: transparent;
    border: none;
    outline-style: none;
    float: left;
    font-size: 25px;
    margin: 15px 10px;
    color: #c9d1d9;
  }

  #logo {
    height: 40px;
    width: 40px;
    border-radius: 50%;
    float: left;
    margin: 10px 5px;
  }

  #alert-btn {
    width: 40px;
    height: 40px;
    background-color: transparent;
    border: none;
    outline-style: none;
    float: right;
    font-size: 25px;
    margin: 15px 10px;
    color: #c9d1d9;
  }

  #menu-extension {
    width: 100%;
    height: 396;
    display: none;
    float: left;
    transition: ease-in 0.4s all;
  }

  #input-cover2 {
    background-color: #0d1117;
    height: 29px;
    padding: 0px 8px;
    border: 0.5px solid #393c41;
    border-radius: 30px;
    width: 95%;
    margin: 2px auto;
  }

  #search-input2 {
    outline-style: none;
    height: 100%;
    width: 92%;
    color: #fff;
    border: none;
    padding: 3px;
    background-color: transparent;
  }

  #small-navigation {
    padding: 0px;
    margin: 10px auto;
    list-style-type: none;
    width: 93%;
    display: block;
    overflow: auto;
  }

  #small-navigation li {
    border-style: solid;
    color: #fff;
    font-size: 15px;
    border-color: #747373;
    border-width: 0.1px 0px 0.2px 0px;
    padding: 10px 0px;
  }

  #small-navigation li img {
    height: 20px;
    width: 20px;
    border-radius: 50%;
  }
}
</style>