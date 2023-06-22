<template>
  <Navbar :showShadow="!intersected"/>

  <div id="HeroPadding" class="hero-padding"/>
  <div id="Hero" class="hero">
    <div style="overflow: hidden">
      <h1 ref="heroHeading1" style="transition: ease-in-out 1.25s" class="outside-screen">Hi there!</h1>
      <h1 ref="heroHeading2" style="transition: ease-in-out 1.5s" class="outside-screen">I'm <span style="color: var(--secondary)">Riley Wong.</span></h1>
      <p ref="heroParagraph" style="transition: ease-in-out 1.75s; max-width: 70ch" class="outside-screen">
        I value independence, communication, and the opportunity to learn from others! Feel free to <span @click="toProjects" class="hero-to-link">check my work below</span> or <span @click="toContact" class="hero-to-link">reach out to me here!</span>
      </p>
      <!-- <span style="border: 2px solid black; border-radius: 999px; margin: 5px; padding: 8px 25px 8px; font-weight: 400">
        Check out my work!
      </span> -->
      <div style="transition: 3s; margin-top: 60px" ref="heroLinks" class="hidden" >
        <MediaLogos />
      </div>
    </div>
    <div class="bio-pic-container">
      <img src="@/assets/biopic.jpg" alt="Bio Picture" ref="heroImage" style="transition: 3s" class="bio-pic hidden" />
      <!-- <button @click="load">Load</button> -->
    </div>
  </div>

  <div id="AboutMe" style="scroll-margin-top: 100px;" class="about-me">
    <h2 style="grid-column: 1">About Me.</h2>
    <div style="grid-column: 2">
      <p>
        I’m Riley, a sophomore computer science student at <span style="color: var(--secondary)">Santa Clara University</span>.
        My passion for programming began in middle school when I first discovered MIT Scratch.
        At the time, I didn't even know what a function was, but I somehow made my 1000 lines of repeated code work...
        Today, I enjoy learning new technologies from REST API's to circuits! 
        In my free time, I’ll be found playing tennis, rendering a new 3D project in Blender, 
        or practicing a finger-style song on the acoustic guitar. 
      </p>
      <div style="width: 200px">
        <a href="documents/resume.pdf" target="_black" style="color: black; text-decoration: none">
          <div class="resume-link">
            <div style="margin-top: 5px; margin-left: 35px; font-weight: 400; font-size: 1.75rem">Résumé</div>
            <div style="margin-left: 32.5px">
              <svg width="50px" height="50px">
                <line x1="25%" y1="50%" x2="75%" y2="50%" style="stroke: black; stroke-width: 2px"/>
                <line x1="50%" y1="25%" x2="50%" y2="75%" style="stroke: black; stroke-width: 2px"/>
              </svg>
            </div>
          </div>
        </a>
      </div>

      <div style="display: flex">
        <h4>Skills</h4>
        <svg width="100%" height="25px">
          <line x1="5%" y1="50%" x2="95%" y2="50%" style="stroke: black" />
        </svg>
      </div>
      <div class="skills">
        <div>
          <h4 style="margin: 25px 0 10px">Languages:</h4>
          <ul style="list-style-type: circle">
            <li>Python</li>
            <li>C++</li>
            <li>JavaScript</li>
            <li>HTML/CSS</li>
            <li>SQL</li>
          </ul>
        </div>
        <div>
          <h4 style="margin: 25px 0 10px">Frameworks:</h4>
          <ul style="list-style-type: circle">
            <li>Flask</li>
            <li>Vue.js</li>
            <li>React.js</li>
            <li>Matplotlib</li>
            <li>Scipy</li>
          </ul>
        </div>
        <div>
          <h4 style="margin: 25px 0 10px">Tools:</h4>
          <ul style="list-style-type: circle">
            <li>VS Code</li>
            <li>GitHub</li>
            <li>Jupyter</li>
            <li>Blender API</li>
            <li>Stack Overflow</li>
          </ul>
        </div>
      </div>
    </div>
  </div>

  <div id="Projects" style="scroll-margin-top: 100px; margin: 50px 0 50px; padding: 30px 5% 30px">
    <h2 style="margin-bottom: 50px">Projects.</h2>
    <ProjectCard name="gourm.ai"
                 description="An AI-powered cooking assistant designed to simplify and enhance the culinary experience. I primarily worked on the frontend, but I also communicated prompts with the backend team as to parse GPT-4 effectively."
                 type="vid"
                 media="https://www.youtube.com/embed/R8uRnmXLSpo"
                 link="https://github.com/rileywong311/CalHack-AI-2023"
                 />
    <hr class="line-break" />
    <ProjectCard name="Blender Addon: Screen to Text"
                 description="This plugin renders the current viewport with the image as ASCII characters based on brightness values. This utilized the Blender API's off-screen rendering, custom texture drawing, and developer tools for authoring the interface."
                 type="vid"
                 media="https://www.youtube.com/embed/iYzjLTMy2-c"
                 link="https://github.com/rileywong311/Blender_ScreenToText"
                 />
    <hr class="line-break" />
    <ProjectCard name="Hands For Help"
                 description="Supported an internet-independent mode of resource tracking and sharing through “digital handshakes.” This was acheived by transfering data user-to-user with QR codes storing JSON. I worked on the backend to locate and parse highest-rated locations."
                 type="vid"
                 media="https://www.youtube.com/embed/LOz8XoQQS2A"
                 link="https://github.com/rileywong311/H4H-2023"
                 />
    <hr class="line-break" />
    <ProjectCard name="Logistic Map Psuedo-Random Number Generator"
                 description="Distilled the chaotic region of the logistic map as a source of entropy for intrinsic random number generation. Ran a series of statistical tests on the generator. "
                 type="img"
                 media="LogisticMap.png"
                 link="https://github.com/rileywong311/Logistic-Map-PRNG"
                 />   
    <hr class="line-break" />
    <ProjectCard name="NestNotifications"
                 description="An alternative location tracking app that provides independence among adolescents and more privacy for all users by measuring time and distance rather than providing a direct location. I worked on the backend to record travel-time polygons and location within the zone."
                 type="vid"
                 media="https://www.youtube.com/embed/39aNTYJP-SQ"
                 link="https://github.com/rileywong311/INRIX-Hack-22"
                 />              
  </div>

  <div id="Experience" style="scroll-margin-top: 100px; margin: 50px 0 50px; padding: 30px 5% 50px; background: var(--background2)">
    <h2>Experience.</h2>
    <br />
    <div style="display: flex; flex-wrap: wrap; column-gap: 50px; row-gap: 25px">
      <ExperienceCard dates="May 2023-Present" role="Student Developer" org="Google Summer of Code, IfcOpenShell">
        <p>
          The project I am working on involves updating and reworking the smart building entity authoring tool in IfcOpenShell's Blender plugin, <a href="https://blenderbim.org/" target="_blank" style="color: var(--secondary)">BlenderBIM.</a>
          Here, I am working to further bridge the IFC and <a href="https://brickschema.org/" target="_blank" style="color: var(--secondary)">BrickSchema</a> semantic structures and their shared mission to evolve the common exchange of building information.
        </p>
      </ExperienceCard>
      <ExperienceCard dates="April 2023-Present" role="Webmaster" org="SCU Association of Computational Machinery">
        <p>
          ACM is one of the largest student organizations on campus and is the primary computer science club that hosts workshops, guest speakers, and hackathons. 
          I work to mantain, update, and expand ACM's sites and content database.
          Check out the ACM sites
          <a href="http://acm.engr.scu.edu/#/" target="_blank" style="color: var(--secondary)">here</a>,
          <a href="https://hackforhumanity.io/" target="_blank" style="color: var(--secondary)">here</a>,
          and <a href="http://acm.engr.scu.edu/inrix/" target="_blank" style="color: var(--secondary)">here!</a>
        </p>
      </ExperienceCard>
    </div>
  </div>

  
  <div id="Contact" class="contact" style="scroll-margin-top: 100px ">
    <h2 style="grid-column: 1">Contact.</h2>
    <div style="grid-column: 2; margin: 50px auto">
      <FormCard  />
      <div style="margin: auto; text-align: center;">
        <a href="mailto:rnwong@scu.edu" style="text-decoration: none"><div style="margin: 50px;"><span class="email">rnwong@scu.edu</span></div></a>
        <MediaLogos :center="true" />
      </div>
    </div>
  </div>

  <router-link to="received">here</router-link>

  <Footer />

</template>

<script>
import Navbar from '@/components/Navbar.vue';
import MediaLogos from '@/components/MediaLogos.vue';
import ProjectCard from '@/components/ProjectCard.vue';
import ExperienceCard from '@/components/ExperienceCard.vue';
import FormCard from '@/components/FormCard.vue';
import Footer from '@/components/Footer.vue';

export default {
  name: 'Mainpage',
  components: {
    Navbar,
    MediaLogos,
    ProjectCard,
    ExperienceCard,
    FormCard,
    Footer,
  },
  data: () => {
    return {
      observer: null,
      intersected: true,
    }
  },
  mounted() {
    // intersection observer
    let options = {
      rootMargin: "0px 0px 0px -25px",
      threshold: 0.8,
    };
    this.observer = new IntersectionObserver(entries => {
      if (entries[0].isIntersecting) {
        this.intersected = true;
      }
      else {
        this.intersected = false;
      }
    }, options);
    this.observer.observe(document.getElementById("HeroPadding"));

    this.load();
  },
  destroyed() {
    this.observer.disconnect();
  },
  methods: {
    async toProjects() {
        const element = document.getElementById("Projects");
        element.scrollIntoView({behavior: 'smooth'}); 
      },
    async toContact() {
      const element = document.getElementById("Contact");
      element.scrollIntoView({behavior: 'smooth'}); 
    },
    async load() {
      setTimeout( () => {
        this.$refs.heroHeading1.classList.remove('outside-screen');
        this.$refs.heroHeading2.classList.remove('outside-screen');
        setTimeout( () => {
          this.$refs.heroParagraph.classList.remove('outside-screen')
          this.$refs.heroImage.classList.remove('hidden');
          this.$refs.heroLinks.classList.remove('hidden');
        }, 800)
      }, 200)
    }
  }
}
</script>

<style>
.outside-screen {
  transform: translateX(-100%);
}

.hidden {
  opacity: 0;
}

.hero-padding {
  height: min(500px, 30vh)
}

.hero {
  margin: 0 5% 0;
  display: flex;
  flex-wrap: wrap-reverse;
  column-gap: 150px;
  row-gap: 40px;
  min-height: min(65vh, 800px);
}

.bio-pic {
  --size: 200px;
  width: var(--size);
  height: var(--size);
  border: 4px solid var(--secondary);
  border-radius: 999px;
  object-fit: cover;
  z-index: -1;
  box-shadow: rgba(99, 99, 99, 0.8) 0px 2px 8px 0px;
}

.hero-to-link {
  font-weight: 300;
  color: var(--secondary);
  text-decoration: underline;
  transition: 0.2s;
}

.hero-to-link:hover {
  cursor: pointer;
  background: var(--background2);
}

@media screen and (max-width: 1100px) {
  .hero-padding {
    height: max(15vh, 80px);
  }
}

@media screen and (max-width: 768px) {
  .bio-pic-container {
    width: 100%;
    text-align: center;
  }

  .bio-pic {
    --size: 150px;
    border: 3px solid var(--secondary) ;
  }
}

.about-me {
  margin: 50px 0 50px;
  padding: 30px 5% 30px;
  background: var(--background2);
  display: grid;
  grid-auto-rows: auto;
  gap: min(400px, 20vw);
}

@media screen and (max-width: 768px) {
  .about-me {
    display: block;
  }
}

.resume-link {
  border: 2px solid black;
  border-radius: 999px;
  height: 50px;
  width: 200px;
  font-size: 1.5rem;
  transition: ease 0.5s;
  margin: 50px 0 50px;
  overflow: hidden;
  display: flex
}

.resume-link:hover {
  width: 250px;
  cursor: pointer;
}

.skills {
  display: flex;
  column-gap: 175px;
  flex-wrap: wrap;
}

@media screen and (max-width: 768px) {
  .skills {
    column-gap: 100px;
  }
}

@media screen and (max-width: 450px) {
  .skills {
    column-gap: 35px;
  }

  .skills li {
    font-size: 0.875rem;
  }
}

.line-break {
  width: 55%;
  margin: 75px auto 100px;
  border: 1px solid black;
}

.contact {
  margin: 50px 0 50px;
  padding: 30px 5% 30px;
  display: grid;
  grid-auto-rows: auto;
  gap: min(400px, 20vw);
}

@media screen and (max-width: 1200px) {
  .contact {
    display: block;
  }
}

.email {
  color: var(--secondary);
  padding: 10px 30px 10px;
  border-radius: 999px;
  transition: 0.5s;
}

.email:hover {
  box-shadow: rgba(99, 99, 99, 0.4) 0px 2px 8px 0px;
  cursor: pointer;
}


</style>