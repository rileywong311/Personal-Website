<template>
  <nav :class="{shadow: showShadow}" style="position: fixed; top: 0; left 0; width: min(100%, 1800px); background: var(--background); z-index: 2">

    <span @click="toHero" id="right" style="margin-top: min(30px, 3vh); display: block; float: left; margin-left: 5%">
      <span class="main-link">RW.</span>
      <br />
      <svg height="7.5px" width="120px">
        <line x1="0%" y1="50%" x2="100%" y2="50%" style="stroke: black"></line>
      </svg>
    </span>

    <span id="left-bar" style="margin-top: min(30px, 3vh); display: block; float: right; margin-right: 5%">
      <span class="nav-link" :class="{current: currentSection == sections.about}" @click="toAboutMe">About Me</span>
      <span class="nav-link" :class="{current: currentSection == sections.projects}" @click="toProjects">Projects</span>
      <span class="nav-link" :class="{current: currentSection == sections.experience}" @click="toExperience">Experience</span>
      <span class="nav-link" :class="{current: currentSection == sections.contact}" @click="toContact">Contact</span>
    </span>

    <span @click="toggleHamburger" id="left-burger" style="margin-top: min(25px, 1.5vh); position: fixed; right: 5%; padding: 8px; border: 2px solid black; border-radius: 10px">
      <div class="bar1" :class="{change: showNav}"></div>
      <div class="bar2" :class="{change: showNav}"></div>
      <div class="bar3" :class="{change: showNav}"></div>
    </span>
  </nav>
  <div id="nav-list" :class="{change: showNav }">
    <ul>
      <li v-show="showNav" :class="{current: currentSection == sections.about}">
        <span @click="toAboutMe">About Me</span>
      </li>
      <li v-show="showNav" :class="{current: currentSection == sections.projects}">
        <span @click="toProjects">Projects</span>
      </li>
      <li v-show="showNav" :class="{current: currentSection == sections.experience}">
        <span @click="toExperience">Experience</span>
      </li>
      <li v-show="showNav" :class="{current: currentSection == sections.contact}">
        <span @click="toContact">Contact</span>
      </li>
    </ul>
  </div>

  <!-- <nav style="position: fixed; top: 30px; left: 5%; z-index: 1;">
    <span class="main-link">+ RW.</span>
    <br />
    <svg height="5px" width="120px">
      <line x1="0%" y1="50%" x2="100%" y2="50%" style="stroke: black"></line>
    </svg>
  </nav>
  <nav style="position: fixed; top: 30px; right: 5%; z-index: 1;">
    <span class="nav-link">About Me</span>
    <span class="nav-link">Projects</span>
    <span class="nav-link">Experience</span>
    <span class="nav-link">Contact</span>
  </nav> -->
</template>

<script>
export default {
  name: 'Navbar',
  data: () => {
    return {
      showNav: false,
      sections: {
        'top': 0,
        'about': 1,
        'projects': 2,
        'experience': 3,
        'contact': 4,
      }
    }
  },
  props: {
    showShadow: Boolean,
    currentSection: Number,
  },
  methods: {
      toggleHamburger() {
        this.showNav = !this.showNav;
      },
      closeNavbar() {
        this.showNav = false;
      },
      async toHero() {
        await this.$router.push('/')
        window.scrollTo({ top: 0, behavior: 'smooth' });
      },
      async toAboutMe() {
        await this.$router.push('/')
        this.closeNavbar();
        const element = document.getElementById("AboutMe");
        element.scrollIntoView({behavior: 'smooth'}); 
      },
      async toProjects() {
        await this.$router.push('/')
        this.closeNavbar();
        const element = document.getElementById("Projects");
        element.scrollIntoView({behavior: 'smooth'}); 
      },
      async toExperience() {
        await this.$router.push('/')
        this.closeNavbar();
        const element = document.getElementById("Experience");
        element.scrollIntoView({behavior: 'smooth'}); 
      },
      async toContact() {
        await this.$router.push('/')
        this.closeNavbar();
        const element = document.getElementById("Contact");
        element.scrollIntoView({behavior: 'smooth'}); 
      },
  }
}
</script>


<style>
.main-link {
  font-weight: 500;
  margin: 10px;
  padding: 5px 15px 5px;
  border-radius: 999px;
  transition: 0.3s ease-in-out;
}

.main-link:hover {
  /* border-color: black; */
  /* background: var(--accent); */
  box-shadow: rgba(99, 99, 99, 0.4) 0px 2px 8px 0px;
  cursor: pointer;
}


.nav-link {
  margin: 10px;
  padding: 4px 25px 4px;
  border: 2px solid black;
  border-radius: 999px;
  font-weight: 400;
  transition: 0.3s;
}

.nav-link:hover {
  background: var(--secondary);
  color: white;
  cursor: pointer;
}

.nav-link.current {
  background: var(--secondary);
  color: white;
}


#left-burger {
  display: none;
}

.bar1, .bar2, .bar3 {
  width: 35px;
  height: 2px;
  background-color: black;
  transition: 0.5s;
  border-radius: 999px;
}

.bar2 {
  width: 25px;
  margin-left: 10px;
  margin-top: 10px;
  margin-bottom: 10px;
}

.change.bar1 {
  transform: translate(0, 12px) rotate(-45deg);
}

.change.bar2 {
  margin-left: 35px;
  width: 0px;
}

.change.bar3 {
  transform: translate(0, -12px) rotate(45deg);
}

#nav-list ul {
  position: fixed;
  top: 0;
  padding: 20vh 20% 0;
  margin: 0;
  z-index: 1;
  visibility: hidden;
  opacity: 0;
  background: white;
  transition: all 0.5s ease;
  height: 100vh;
  width: 100%;
  
  list-style: none;
  text-align: left;
}

#nav-list li {
  font-size: 2rem;
  margin: 10px 0 10px;
  padding: 5px 20px 5px;
  font-weight: 500;
}

#nav-list li.current {
  background: var(--background2);
}

.change#nav-list ul{
  opacity: 0.98;
  visibility: visible;
}

@media screen and (max-width: 900px ) {
  #left-bar {
    display: none !important;
  }

  #left-burger {
    display: inline;
  }
}

</style>