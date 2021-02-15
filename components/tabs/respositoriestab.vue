<template>
  <div id="more-sec-one">
    <input type="text" id="find-repo-input" placeholder="Find a repository" />

    <div id="sub-sec">
      <!-- <button class="sub-btn" @click="showB =  true">
                Type: <span style="color: #fff">All</span>
                <span class="mdi mdi-chevron-down"></span>
              </button>
              <button class="sub-btn">
                Type: <span style="color: #fff">Language</span>
                <span class="mdi mdi-chevron-down"></span>
              </button>
              -->

      <div class="dropdown">
        <button @click="myFunction(0)" class="sub-btn dropbtn">
          Type: <span style="color: #fff">All</span>
          <span class="mdi mdi-chevron-down"></span>
        </button>
        <div id="myDropdown" class="dropdown-wrapper">
          <span class="dropdown-title">Select type</span>
          <ul id="dropdown-content">
            <li>All</li>
            <li>Public</li>
            <li>Private</li>
            <li>Sources</li>
            <li>Forks</li>
            <li>Archived</li>
            <li>Mirrors</li>
          </ul>
        </div>
      </div>




        <div class="dropdown">
        <button @click="myFunction(1)" class="sub-btn dropbtn">
          Type: <span style="color: #fff">Language</span>
                <span class="mdi mdi-chevron-down"></span>
        </button>
        <div id="myDropdown2" class="dropdown-wrapper">
          <span class="dropdown-title">Select Language</span>
          <ul id="dropdown-content">
            <li>All</li>
            <li>Vue</li>
            <li>Dart</li>
            <li>JavaScript</li>
            <li>TypeScript</li>
            <li>HTML</li>
            <li>Python</li>
          </ul>
        </div>
      </div>

       <button id="create-repo-btn">
                <span class="mdi mdi-book-play-outline"></span> New
              </button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {};
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

    window.onclick = function (event) {
      if (!event.target.matches(".dropbtn")) {
        var dropdowns = document.getElementsByClassName("dropdown-wrapper");
        var i;
        for (i = 0; i < dropdowns.length; i++) {
          var openDropdown = dropdowns[i];
          if (openDropdown.classList.contains("show")) {
            openDropdown.classList.remove("show");
          }
        }
      }
    };
  },
  methods: {
    myFunction(which) {
      if(which == 0){
      document.getElementById("myDropdown").classList.toggle("show");
      }else{
         document.getElementById("myDropdown2").classList.toggle("show");
      }
    },
  },
};
</script>

<style scoped>
#more-sec-one {
  height: auto;
  width: 100%;
  margin: 0px;
  display: flex;
  padding: 20px 0px;
}

#find-repo-input {
  background-color: transparent;
  outline-style: none;
  height: 30px;
  border-radius: 25px;
  padding: 10px;
  border: 0.5px solid #393c41;

  color: #fff;
  flex: 1;
}

#find-repo-input:hover {
  border: 0.5px solid #b1b1b1;
}

.sub-btn {
  color: #c9d1d9;
  background-color: #393c41;
  border: none;
  padding: 7px 10px;
  font-size: 12px;
  outline-style: none;
  margin: 0px 0px 0px 10px;
  border-radius: 20px;
}

.sub-btn:hover {
  padding: 8px 9.5px;
  border: 0.5px solid #c9d1d9;
  cursor: pointer;
}

#create-repo-btn {
  background-color: #238636;
  color: #fff;
  border: none;
  padding: 7px 10px;
  font-size: 12px;
  outline-style: none;
  margin: 0px 0px 0px 10px;
  border-radius: 20px;
}

#create-repo-btn:hover {
  background-color: #23cc45;
  cursor: pointer;
}

@media only screen and (max-device-width: 767px) {
  #more-sec-one {
    height: auto;
    width: 100%;
    margin: 0px;
    display: flex;
    flex-direction: column;
    padding: 20px 0px;
  }

  #find-repo-input {
    flex: unset;
    width: 95%;
    margin: auto;
  }

  #sub-sec {
    text-align: center;
    width: 100%;
  }

  .sub-btn {
    margin: 10px auto 10px auto;
  }
}

@media only screen and (min-device-width: 768px) {
  /* The container <div> - needed to position the dropdown content */
  .dropdown {
    position: relative;
    display: inline-block;
  }

  /* Dropdown Content (Hidden by Default) */
  .dropdown-wrapper {
    display: none;
    position: absolute;
    background-color: #393c41;
    min-width: 220px;
    margin: 5px 0px;
    box-shadow: 0px 8px 16px 0px rgba(0, 0, 0, 0.2);
    z-index: 1;
    border-radius: 5px;
  }

  .dropdown-title {
    color: #c9d1d9;
    padding: 10px;
    font-size: 12px;
    display: block;
    border-bottom: 0.1px solid #b1b1b1;
  }

  /* Show the dropdown menu (use JS to add this class to the .dropdown-wrapper container when the user clicks on the dropdown button) */
  .show {
    display: block;
  }

  #dropdown-content {
    margin: 0px 0px;
    padding: 0px;
    list-style-type: none;
  }

  #dropdown-content li {
    padding: 7px 10px;
    color: #c9d1d9;
    font-size: 13px;
    cursor: pointer;
  }

  #dropdown-content li:hover {
    background-color: rgba(0, 0, 0, 0.4);
  }
}

@media only screen and (max-device-width: 767px) {
  /* The container <div> - needed to position the dropdown content */
  .dropdown {
    position: unset;
    display: unset;
  }

  /* Dropdown Content (Hidden by Default) */
  .dropdown-wrapper {
    display: none;
    position: fixed;
    background-color: #393c41;
    min-width: 300px;
    margin: 5px 0px;
    box-shadow: 0px 8px 16px 0px rgba(0, 0, 0, 0.2);
    z-index: 100;
    border-radius: 5px;

    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    z-index: 99;
    text-align: left;
  }

  .dropdown-title {
    color: #c9d1d9;
    padding: 10px;
    font-size: 12px;
    display: block;
    border-bottom: 0.1px solid #b1b1b1;
  }

  /* Show the dropdown menu (use JS to add this class to the .dropdown-wrapper container when the user clicks on the dropdown button) */
  .show {
    display: block;
  }

  #dropdown-content {
    margin: 0px 0px;
    padding: 0px;
    list-style-type: none;
  }

  #dropdown-content li {
    padding: 7px 10px;
    color: #c9d1d9;
    font-size: 13px;
    cursor: pointer;
  }

  #dropdown-content li:hover {
    background-color: rgba(0, 0, 0, 0.4);
  }
}
</style>