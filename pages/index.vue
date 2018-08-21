<template>
  <section class="container">
    <div class="sections">
			<side-nav />
      <div id="main">
        <div class="header-bar">
					<div class="menu-container" v-on:click="openNav" v-bind:class="{change: menuFlag}">
							<div class="bar1"></div>
							<div class="bar2"></div>
							<div class="bar3"></div>
					</div>
					<Ribbon />
        </div>
        <Landing/>
        <Section1/>
        <Section2/>
        <Section3/>
      </div>
    </div>
  </section>
</template>

<script>

import AppLogo from '~/components/AppLogo.vue'
import Ribbon from '~/components/Ribbon.vue'
import SideNav from '~/components/SideNav.vue'

import Landing from '~/components/sections/Landing.vue'
import Section1 from '~/components/sections/Section1.vue'
import Section2 from '~/components/sections/Section2.vue'
import Section3 from '~/components/sections/Section3.vue'

export default {
  components: {
    AppLogo,
    Ribbon,
    Landing,
    Section1,
    Section2,
    Section3,
    SideNav
  },
  data: () => ({
    menuFlag: false
  }),
  methods: {
    sideBar: function(event) {
      this.menuFlag = !this.menuFlag;
    },
    openNav: function(event) {
      this.sideBar();
      if (this.menuFlag) {
        document.getElementById("mySidenav").style.width = "250px";
        document.getElementById("main").style.marginLeft = "250px";
      } else {
          this.closeNav();
      }
    },
    closeNav: function(event) {
      document.getElementById("mySidenav").style.width = "0";
      document.getElementById("main").style.marginLeft= "0";
    }
  }
}
</script>

<style>

@import "https://fonts.googleapis.com/icon?family=Material+Icons";
@import 'vue-material/dist/vue-material.min.css';
@import 'vue-material/dist/theme/default.css';

.container {
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}
.md-dialog {
    max-width: 768px;
}
.md-content-body {
    padding: 20px;
}
.header-bar {
  display: flex;
  justify-content: space-between;
}

.ribbon {
  margin-right: 50px;
}

.active {
  display: block !important;
}

.sidebar {
  position: relative;
  width: 350px;
  height: 100vh;
  display: none;
  background: #106CC8;
  transition: 0.4s;
}

.sections {
  width: 100%;
  padding: 10px;
  display: flex;
  color: white;
  flex-direction: column;
  justify-content: space-around;
}

.title {
  font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif; /* 1 */
  display: block;
  font-weight: 500;
  color: black;
  letter-spacing: 1px;
  padding: 10px;
}

.title:hover {
    color: green !important;
    font-family: 800;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}

#mySidenav > a {
    display: flex;
    text-decoration: none;
}

#mySidenav a:hover {
    color: white !important;
}

#mySidenav a > i {
    padding: 0 10px;
    color: white;
}
.sidenav {
    height: 100%;
    width: 0;
    position: fixed;
    z-index: 1;
    top: 0;
    left: 0;
    background-color:#000000;
    overflow-x: hidden;
    transition: 0.5s;
    padding-top: 30px;
}

.sidenav a {
    padding: 8px 8px 8px 32px;
    text-decoration: none;
    font-size: 25px;
    color: #d3dae4 !important;
    display: block;
    transition: 0.3s;
}

.sidenav a:hover {
    color: #f1f1f1;
}

.sidenav .closebtn {
    position: absolute;
    top: 0;
    right: 25px;
    font-size: 36px;
    margin-left: 50px;
}

#main {
    transition: margin-left .5s;
    padding: 16px;
}

@media screen and (max-height: 450px) {
  .sidenav {padding-top: 15px;}
  .sidenav a {font-size: 18px;}
}

.menu-container {
    display: inline-block;
    cursor: pointer;
}

.bar1, .bar2, .bar3 {
    width: 35px;
    height: 5px;
    background-color: #333;
    margin: 6px 0;
    transition: 0.4s;
}

.change .bar1 {
    -webkit-transform: rotate(-45deg) translate(-9px, 6px);
    transform: rotate(-45deg) translate(-9px, 6px);
}

.change .bar2 {opacity: 0;}

.change .bar3 {
    -webkit-transform: rotate(45deg) translate(-8px, -8px);
    transform: rotate(45deg) translate(-8px, -8px);
}

.dropdown {
    position: relative;
    display: inline-block;
    color: black;
    width: 100px;
    cursor: pointer;
    margin-right: 50px;
}

.dropdown-content {
    display: none;
    position: absolute;
    background-color: #f9f9f9;
    min-width: 160px;
    height: auto;
    
    border: 1px solid #00000052;
    box-shadow: 0px 8px 16px 0px rgba(0,0,0,0.2);
    padding: 12px 16px;
    z-index: 1;
}

.ribbon-title:hover {
    border-bottom: 2px solid green;
}

.dropdown:hover .dropdown-content {
    display: block;
}
</style>
