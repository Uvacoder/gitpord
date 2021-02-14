<template>
     <div id="more-sec-one">
            <input
              type="text"
              id="find-repo-input"
              placeholder="Find a repository"
            />

            <div id="sub-sec">
              <button class="sub-btn">
                Type: <span style="color: #fff">All</span>
                <span class="mdi mdi-chevron-down"></span>
              </button>
              <button class="sub-btn">
                Type: <span style="color: #fff">Language</span>
                <span class="mdi mdi-chevron-down"></span>
              </button>
              <button id="create-repo-btn">
                <span class="mdi mdi-book-play-outline"></span> New
              </button>
            </div>
          </div>
</template>

<script>
export default {
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
  padding: 9px 10px;
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
  padding: 9px 10px;
  font-size: 12px;
  outline-style: none;
  margin: 0px 0px 0px 10px;
  border-radius: 20px;
}

#create-repo-btn:hover {
  background-color: #23cc45;
  cursor: pointer;
}



 @media only screen and (max-device-width: 767px){

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

#sub-sec{
text-align: center;
width: 100%;
}

.sub-btn {
  margin: 10px auto 10px auto;
}

 }
</style>