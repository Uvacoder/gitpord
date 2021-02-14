<template>
  <div class="container">
    <div class="hero">
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
          <button>
            <span class="mdi mdi-book-open-variant"></span> Overview
          </button>
        </li>

        <li>
          <button class="active-tab">
            <span class="mdi mdi-book-play-outline"></span> Repositories
          </button>
        </li>

        <li>
          <button><span class="mdi mdi-graph-outline"></span> Projects</button>
        </li>

        <li>
          <button>
            <span class="mdi mdi-package-variant"></span> Packages
          </button>
        </li>
      </ul>

      <div id="image-switch"></div>
    </div>

    <div id="over-all-wrapper">
      <div id="content-wrapper">
        <div id="user-details-wrapper">
          <div id="profile-pic-wrapper">
            <img id="avatar" src="~/static/profile.jpg" alt="boy" />
            <button id="set-status-btn">
              <span class="mdi mdi-emoticon-excited-outline"></span>
            </button>
          </div>

          <span id="user-name">Xceldeveloper</span>

          <button id="edit-profile-btn">Edit profile</button>

          <ul id="user-internal-links">
            <li>
              <span
                style="color: #616972"
                class="mdi mdi-account-supervisor-outline"
              ></span>
              <span style="color: #c9d1d9">34</span> followers
            </li>
            <li><span class="dix"></span></li>
            <li><span style="color: #c9d1d9">11</span> following</li>
            <li><span class="dix"></span></li>
            <li>
              <span style="color: #616972" class="mdi mdi-star-outline"></span>
              <span style="color: #c9d1d9">11</span>
            </li>
          </ul>

          <ul id="user-external-links">
            <li>
              <a href="#"
                ><span class="mdi mdi-link"></span> xceldeveloper.com</a
              >
            </li>
            <li>
              <a href="#"
                ><span class="mdi mdi-twitter"></span> @xceldeveloper</a
              >
            </li>
          </ul>
          <br />
          <div id="divider"></div>

          <span id="organizations-title">Organizations</span>
          <ul id="organization-badge">
            <li></li>
            <li></li>
            <li></li>
          </ul>
        </div>

        <div id="more-wrapper">
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
        </div>
      </div>
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

<style>
.container {
  min-height: 100vh;
  padding: 0px;
  margin: 0px;
  box-sizing: border-box;
  background-color: #0d1117;
}

.hero {
  height: 63px;
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: #161b22;
}
#inner-wrapper {
  height: 30px;
  display: flex;
  width: 100%;
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

#image-switch {
  width: 200px;
  height: 74px;
  background-color: red;
  position: absolute;
  right: 100px;
  bottom: 0px;
  display: none;
}

#over-all-wrapper {
  width: 70%;
  margin: auto;
}

#content-wrapper {
  width: 100%;
  height: 200vh;
  display: flex;
}

#user-details-wrapper {
  width: 300px;
  height: auto;
  position: relative;
}

#profile-pic-wrapper {
  width: 270px;
  height: 270px;
  background-color: #0d1117;
  margin: 0px 15px;
  border-radius: 50%;
  position: absolute;
  top: -30px;
  border: 2px solid #393c41;
  box-shadow: 0px 0px 15px #202022;
  position: relative;
  z-index: 95;
}

#avatar {
  width: 100%;
  height: 100%;
  border-radius: 50%;
}

#set-status-btn {
  border: 0.5px solid #393c41;
  border-radius: 50%;
  height: 35px;
  font-size: 21px;
  width: 35px;
  outline-style: none;
  background-color: #202022;
  position: absolute;
  bottom: 30px;
  color: #616972;
  right: 5px;
}

#set-status-btn:hover {
  color: #c9d1d9;
  border: 0.5px solid #c9d1d9;
  cursor: pointer;
}

#user-name {
  display: block;
  font-size: 20px;
  color: #616972;
  padding: 5px 15px;
}

#edit-profile-btn {
  color: #c9d1d9;
  background-color: #393c41;
  border: none;
  padding: 10px 0px;
  outline-style: none;
  width: 270px;
  margin: 10px 15px;
  border-radius: 30px;
}

#edit-profile-btn:hover {
  padding: 9px 0px;
  border: 0.5px solid #c9d1d9;
  cursor: pointer;
}

#user-internal-links {
  list-style-type: none;
  padding: 0px;
  margin: 0px 15px;
  white-space: nowrap;
  display: flex;
  align-items: center;
  justify-content: center;
}

#user-internal-links li {
  color: #616972;
  display: inline-block;
}

#user-internal-links li:hover {
  color: cornflowerblue;
  cursor: pointer;
}

.dix {
  height: 7px;
  width: 7px;
  display: block;
  margin: 0px 6px;
  background-color: #fff;
}

#user-external-links {
  padding: 0px;

  list-style-type: none;
  color: #fff;
  margin: 10px 15px;
}

#user-external-links li {
  padding: 3px 0px;
  color: #c9d1d9;
}

#user-external-links li a {
  text-decoration: none;
  color: #c9d1d9;
}

#user-external-links li a:hover {
  color: cornflowerblue;
}

#divider {
  width: 100%;
  height: 1px;
  background-color: #616972;
}

#organizations-title {
  color: #c9d1d9;
  display: block;
  padding: 10px 0px 5px 0px;
}

#organization-badge {
  padding: 0px;
  height: auto;
  width: 100%;
  white-space: nowrap;
  overflow: auto;
}

#organization-badge li {
  margin: 3px 6px 0px 0px;
  display: inline-block;
  height: 50px;
  width: 50px;
  background-color: grey;
  border-radius: 7px;
  cursor: pointer;
}

#more-wrapper {
  min-height: 200vh;
  width: 100%;
  flex: 1;
}

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
</style>
