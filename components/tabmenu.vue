<template>
  <div>
    <ul id="page-tabs">
        <li>
          <button>
           Overview
          </button>
        </li>

        <li>
          <button class="active-tab">
            Repositories
          </button>
        </li>

        <li>
          <button>
          Projects
          </button>
        </li>

        <li>
          <button>
             Packages
          </button>
        </li>
      </ul>

  </div>
</template>

<script>
export default {
  mounted() {
    console.log("mounted...")
    var h = document.getElementById("page-tabs");
    //  var readout = document.getElementById("readout");
    var stuck = false;
    var stickPoint = getDistance();

    function getDistance() {
      var topDist = h.offsetTop;
      return topDist;
    }

    window.onscroll = function (e) {
         console.log("scrolling")
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
  },
};
</script>

<style scoped>

#page-tabs {
  padding: 0px;
  margin:6px auto;
  white-space: nowrap;
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100%;
  max-width: 500px;
  border-bottom: 0.5px solid #616972;
  overflow: auto;
}

#page-tabs li {
  display: inline-block;
  width: 25%;
}

#page-tabs li button {
  background: transparent;
  color: #616972;
  height: 35px;
  width: 100%;

  font-size: 12px;
  border: none;
  outline-style: none;
}

#page-tabs li button:hover {
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

 @media only screen and (max-device-width: 767px){
 #page-tabs{
     display: block;
   }
   }

   
 @media only screen and (min-device-width: 768px){
 #page-tabs{
     display: none;
   }
 }
</style>