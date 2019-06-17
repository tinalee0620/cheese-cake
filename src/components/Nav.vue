<template>
   <nav class="nav">
     <input @click="onCheck" type="checkbox" class="nav__checkbox" id="nav-toggle">
    <label for="nav-toggle" class="nav__btn">
      <button class="nav__icon"></button>
    </label>
    <div id="myNav" :class="`overlay ${myNav}`">
      <div class="overlay-content">
          <!-- <figure class="overlay__item">
      <img src ="../../img/Group.png" alt=" " style="width:50%">
     </figure> -->
     <a href="#" class="overlay-content_a">OUR TRIP</a>
      <img src ="../../img/line_1.png" alt=" " style="width:90%">
        <a href="#">JEJU</a>
        <img src ="../../img/line_1.png" alt=" " style="width:60%">
        <a href="#">TAINAN</a>
         <img src ="../../img/line_1.png" alt=" " style="width:70%">
        <a href="#">ALISHAN</a>
        <img src ="../../img/line_1.png" alt=" " style="width:60%">
        <a href="#">KENTING</a>
         <img src ="../../img/line_1.png" alt=" " style="width:70%">
         <a href="#">HAULIEN</a>
           <img src ="../../img/line_1.png" alt=" " style="width:90%">
         <a href="#" class="overlay-content_a">ADD MORE</a>
      </div>
    </div>
   </nav>
</template>

<script>
export default {
   name: 'Nav',
     data() {
    return {
      checked: false,
      size: "lg",
      myNav: "hide-lg"
    };
  },
  methods: {
    onResize() {
      if (window.innerWidth > 1000) {
        this.size = "lg";
        if (!this.checked) 
          this.myNav = "notransition hide-lg";
      } else {
        this.size = "sm";
        if (!this.checked)
           this.myNav = "notransition hide-sm";
      }
    },

    onCheck() {
      if (this.checked && this.size == "sm") 
        this.myNav = "hide-sm";
      else if (this.checked && this.size == "lg") 
        this.myNav = "hide-lg";
      else 
        this.myNav = "show";
      this.checked = !this.checked;
    },

    onRoute() {
      this.checked = !this.checked;
    }
  },

  created() {
    window.addEventListener("resize", this.onResize);
    if (window.innerWidth > 1000) {
      this.size = "lg";
      this.myNav = "hide-lg";
    } else {
      this.size = "sm";
      this.myNav = "hide-sm";
    }
  }

}
var prevScrollpos = window.pageYOffset;
window.onscroll = function() {
  var currentScrollPos = window.pageYOffset;
  if (prevScrollpos > currentScrollPos) {
    document.getElementsByClassName("nav").style.top = "0";
     document.getElementsByClassName("nav_btn").style.top = "0";
  } else {
    document.getElementsByClassName("nav").style.top = "-50px";
     document.getElementsByClassName("nav_btn").style.top = "-50px";
  }
  prevScrollpos = currentScrollPos;
}
</script>

<style lang="postcss" scoped>
@import "../../styles/base/_variables.css";
@import "../../styles/base/_global.css";
@import "../../styles/modules/_nav.css";
/* .overlay__item{
    position: fixed;
   margin-left: -290px;
    margin-top: -210px;
   width: 80%;
 
} */
.overlay-content_a:link{
 
 
  text-decoration: none;
  font-size: 26px;
  color: #818181;
  color: $color-white;
  display: block;
  transition: 0.3s;
  
}
.notransition {
  transition: 0s !important;
}

.show {
  transition: 0.5s;
  width: 100%;
  height: 100%;
}

.hide-lg {
  transition: 0.5s;
  width: 0%;
  height: 100%;
}

.hide-sm {
  transition: 0.5s;
  width: 100%;
  height: 0%;
}

.overlay {
  position: fixed;
  z-index: 1;
  top: 0;
  left: 0;
  background-color:#517390;
background: url("../../img/Group 3.png");
  background-size:cover;
           background-position:center center;

  overflow-x: hidden;
}

.overlay-content {
  position: relative;
  top: 6%;
  width: 100%;
  text-align: center;
  margin-top: 30px;
}

.overlay a {
  padding: 10px;
  
  text-decoration: none;
  font-size: 22px;
  color: #818181;
  color: $color-white;
  display: block;
  transition: 0.3s;
}

.overlay a:hover,
.overlay a:focus {
  color: #f1f1f1;
}

.overlay .closebtn {
  position: absolute;
  top: 20px;
  right: 45px;
  font-size: 60px;
}

.overlay-width {
}
</style>