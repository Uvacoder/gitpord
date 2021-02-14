<template>
  <div class="container">
  <headerx/>

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
import headerx from '~/components/headerx.vue'
export default {
  components:{
    headerx
  },
  mounted() {
  
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
