<template>
  <Navbar :showShadow="!intersected" :currentSection="currentSection"/>

  <!-- Hero Screen -->
  <div id="HeroPaddingTop" class="hero-padding"/>
  <section id="Hero" class="hero">
    <div id="SectionBreak" data-section-number="0" style="overflow: hidden">
      <h1 ref="heroHeading1" style="transition: ease-in-out 1.25s" class="outside-screen">Hi there!</h1>
      <h1 ref="heroHeading2" style="transition: ease-in-out 1.5s" class="outside-screen">I'm <span style="color: var(--secondary)">Riley Wong.</span></h1>
      <p ref="heroParagraph" style="transition: ease-in-out 1.75s; max-width: 70ch" class="outside-screen">
        I'm committed to fostering independence, communication, and the opportunity to learn from others! Feel free to
        <span role="tab" tabindex="0" @click="toProjects" @keyup.enter="toProjects" class="hero-to-link">explore my work below</span>
        or <span role="tab" tabindex="0" @click="toContact" @keyup.enter="toContact" class="hero-to-link">reach out to me here!</span>
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
    </div>
  </section>
  <div id="SectionBreak" class="hero-padding"/>

  <!-- About Me Section -->
  <section id="AboutMe" style="scroll-margin-top: 20vh;" class="about-me">
    <h2 id="SectionBreak" data-section-number="1" style="grid-column: 1; margin-bottom: auto">About Me.</h2>
    <div style="grid-column: 2">
      <p>
        <b>My Education: </b>
        I’m a dedicated and driven Computer Science student at <span style="color: var(--secondary)">Santa Clara University</span>
        with a minor in Mathematics and Computer Engineering.
        My official emphasis is <span style="color: var(--secondary)">Data Science</span>, where I have many related classes under my belt,
        but I have also taken a breadth of courses from <i>Automata Theory</i> to <i>Computer Security</i>.
      </p>
      <p>
        <b>My Journey: </b>
        My passion for programming began in middle school when I first discovered drag-and-drop coding in MIT Scratch
        (check out that old work <a href="https://scratch.mit.edu/users/18rwong/projects/" target="_blank">here</a>).
        However, at the time, I didn't even know what a function was, yet resolutely I still made my 1000 lines of repeated code work.&nbsp;.&nbsp;.
        Today, I thrive on continually learning new skills, and I am eager to explore diverse opportunities and industries with a
        shared emphasis on technology, informing my professional career along the way.
      </p>
      <p>
        <b>My Hobbies: </b>
        When I'm not studying for CS or Math, I’ll be found playing <span style="color: var(--secondary)">tennis</span>,
        rendering a new 3D project using <span style="color: var(--secondary)">Blender</span>
        (here's my <a href="https://youtu.be/QGM3tFAf_bQ" target="_blank">demo reel</a>), 
        or practicing finger-style on the <span style="color: var(--secondary)">acoustic guitar</span>. 
      </p>
      <p>
        Here are some other fun facts about me:
        <ul>
          <li>
            I love games! 
            My favorite video games include <i>Minecraft</i>, <i>Rocket League</i>, and <i>Stardew Valley</i>.
            My favorite board games include <i>Love Letter</i>, <i>Terraforming Mars</i>, <i>King of Tokyo</i>, and <i>Marvel's Legendary</i>. 
            Let's play!
          </li>
          <li>
            I started using Duolingo on a whim, now I have a {{ Math.round((((new Date().getTime()) - (new Date("09/10/2019").getTime())) / (1000 * 3600 * 24))) }}-day
            streak learning Spanish and Japanese. If your curious, ask me about these languages!
          </li>
          <li>
            I grew up in Berkeley—feel free to chat about my hometown!
          </li>
        </ul>
      </p>
      <div style="width: 200px">
        <a href="documents/resume.pdf" target="_black" style="color: black; text-decoration: none">
          <div class="resume-link">
            <div style="margin-top: 5px; margin-left: 37.5px; font-weight: 400; font-size: 30px">Résumé</div>
            <div style="margin-left: 35px">
              <!-- <img src="@/assets/link.svg" style="margin: 10px 0 0 12.5px; width: 25px"/> -->
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
        <svg width="100%" height="25px" style="margin-left: 15px">
          <line x1="0%" y1="50%" x2="95%" y2="50%" style="stroke: black" />
        </svg>
      </div>
      <div class="skills">
        <div>
          <h4 style="margin: 25px 0 10px">Languages:</h4>
          <ul style="list-style-type: none; padding-left: 15px">
            <li><i class="devicon-python-plain"/> Python</li>
            <li><i class="devicon-cplusplus-plain"/> C++</li>
            <li><i class="devicon-javascript-plain"/> JavaScript</li>
            <li><i class="devicon-html5-plain"/> HTML</li>
            <li><i class="devicon-css3-plain"/> CSS</li>
            <li><i class="devicon-dart-plain"/> Dart</li>
          </ul>
        </div>
        <div>
          <h4 style="margin: 25px 0 10px">Frameworks:</h4>
          <ul style="list-style-type: none; padding-left: 15px">
            <li><i class="devicon-flask-original"/> Flask</li>
            <li><i class="devicon-vuejs-plain"/> Vue.js</li>
            <li><i class="devicon-react-original"/> React.js</li>
            <li><i class="devicon-flutter-plain"/> Flutter</li>
          </ul>
        </div>
        <div>
          <h4 style="margin: 25px 0 10px">Tools:</h4>
          <ul style="list-style-type: none; padding-left: 15px">
            <li><i class="devicon-vscode-plain"/> VS Code</li>
            <li><i class="devicon-github-original"/> GitHub</li>
            <li><i class="devicon-jupyter-plain"/> Jupyter</li>
            <li><i class="devicon-blender-original"/> Blender API</li>
            <li><i class="devicon-figma-plain"/> Figma</li>
            <li><i class="devicon-qt-original"/> Qt</li>
            <li>(Stack Overflow)</li>
            <li>(ChatGPT)</li>
          </ul>
        </div>
      </div>
      <div id="SectionBreak" data-section-number="1" style="height: 25px"/>
    </div>
  </section>
  
  <!-- Projects Section -->
  <section id="Projects" style="scroll-margin-top: 15vh; margin: 50px 0 50px; padding: 30px 5% 30px">
    <h2 id="SectionBreak" data-section-number="2" style="margin-bottom: 50px">Projects.</h2>
    <ProjectCard name="Brickdle.com"
                  type="vid"
                  media="https://www.youtube.com/embed/2WSh96YcIwc"
                  :links="[
                    {link: 'https://www.brickdle.com/', name: 'Play here!'}
                  ]">
      <p>
        Parsed catalog of LEGO sets to create a Wordle-like game where users guess number of LEGO’s in the picture.
        We are releasing global daily puzzles!
      </p>
      <div style="display: flex; row-gap: 12px; column-gap: 5px; flex-wrap: wrap">
        <SkillTag v-for="skill in ['Flutter', 'Python', 'SQL', 'Google Analytics', 'BigQuery']"> {{ skill }} </SkillTag>
      </div>
    </ProjectCard>
    <hr class="line-break" />
    <ProjectCard name="Park, Bus, & Jam"
                  type="vid"
                  media="https://www.youtube.com/embed/GFKy2b_VfmI"
                  :links="[
                    {link: 'https://github.com/rileywong311/Park-Bus-and-Jam', name: 'GitHub'}
                  ]">
      <p>
        Traffic congestion and other stresses of transportation can quickly take away from a once-in-a-lifetime concert experience.
        This app takes care of all the stress, providing precise routing, cheap/available parking spaces, and an optimized last leg of public transport to your venue.
      </p>
      <div style="display: flex; row-gap: 12px; column-gap: 5px; flex-wrap: wrap">
        <SkillTag v-for="skill in ['Dart', 'Python', 'Flutter', 'Flask', 'INRIX API', 'Ticket Master API', 'Google Services API']"> {{ skill }} </SkillTag>
      </div>
    </ProjectCard>
    <hr class="line-break" />
    <ProjectCard name="BlenderBIM BrickSchema Module"
                  type="vid"
                  media="https://www.youtube.com/embed/8bbuyzT5-rc"
                  :links="[
                    {link: 'https://osarch.org/2023/07/29/what-is-brickschema-and-how-can-i-use-it-update-blenderbim-add-ons-brick-module/', name: 'Blog Post'},
                    {link: 'https://gist.github.com/rileywong311/c5dd453740ac7e80107398032698b081', name: 'Final Report'}
                  ]">
      <p>
        This project further bridges the IfcOpenShell and BrickSchema open-source communities and shared mission to evolve the common exchange of building information.
        This project allows facility management operators to seamlessly edit equipment data and relationships as they continue monitoring the building.
      </p>
      <div style="display: flex; row-gap: 12px; column-gap: 5px; flex-wrap: wrap">
        <SkillTag v-for="skill in ['Python', 'SPARQL', 'Blender API', 'Plugin', 'Python Unit Tests', 'Feature Tests', 'Smart Buildings', 'Building Information Models', 'IFC', 'BrickSchema']"> {{ skill }} </SkillTag>
      </div>
    </ProjectCard>
    <hr class="line-break" />
    <ProjectCard name="gourmAI"
                  type="vid"
                  media="https://www.youtube.com/embed/R8uRnmXLSpo"
                  :links="[
                    {link: 'https://github.com/rileywong311/CalHack-AI-2023', name: 'GitHub'}
                  ]">
      <p>
       An AI-powered cooking assistant designed to provide users with an intuitive, seamless, and delightful culinary experience. 
       I primarily worked on the frontend, ensuring a user-friendly interface that guides the cooking process,
       but I also collaborated closely with the backend team to optimize prompts as we focused on parsing GPT-4 effectively.
      </p>
      <div style="display: flex; row-gap: 12px; column-gap: 5px; flex-wrap: wrap">
        <SkillTag v-for="skill in ['JavaScript', 'React.js', 'Node.js', 'GPT-4', 'OpenAI API']"> {{ skill }} </SkillTag>
      </div>
    </ProjectCard>
    <hr class="line-break" />
    <ProjectCard name="Blender Addon: Screen to Text"
                 type="vid"
                 media="https://www.youtube.com/embed/iYzjLTMy2-c"
                 :links="[
                    {link: 'https://github.com/rileywong311/Blender_ScreenToText', name: 'GitHub'}
                  ]">
      <p>
        This plugin renders the current viewport with the image as ASCII characters based on brightness values. 
        This utilized the Blender API's off-screen rendering, custom texture drawing, and developer tools for authoring the interface.
        It can be installed right now into recent Blender versions!     
      </p>
      <div style="display: flex; row-gap: 12px; column-gap: 5px; flex-wrap: wrap">
        <SkillTag v-for="skill in ['Python', 'Blender API']"> {{ skill }} </SkillTag>
      </div>
    </ProjectCard>
    <hr class="line-break" />
    <ProjectCard name="Logistic Map Psuedo-Random Number Generator"
                 type="img"
                 media="LogisticMap.png"
                 :links="[
                    {link: '/documents/LogisticMap.pdf', name: 'Research Paper'},
                    {link: 'https://github.com/rileywong311/Logistic-Map-PRNG', name: 'GitHub'}
                  ]">
      <p>
        Distilled the chaotic region of the logistic map as a source of entropy for intrinsic random number generation;
        this tapped into the logistic map's inherent unpredictability.
        Afterward, I ran a series of statistical tests to evaluate that the generator met the criteria for randomness.
      </p>
      <div style="display: flex; row-gap: 12px; column-gap: 5px; flex-wrap: wrap">
        <SkillTag v-for="skill in ['Python', 'Matplotlib', 'Scipy', 'Computational Physics']"> {{ skill }} </SkillTag>
      </div>
    </ProjectCard>
    <div id="SectionBreak" data-section-number="2" style="height: 25px"/>
  </section>

  <!-- Experience Section -->
  <section id="Experience" style="scroll-margin-top: 15vh" class="experience">
    <div style="grid-column: 1; width: min(500px, 100%)">
      <h2 id="SectionBreak" data-section-number="3" style="margin-bottom: auto">Experience.</h2>
      <div class="experience-image" :style="{'opacity': experienceImage ? 100 : 0, 'transform': experienceImage ? null : 'translate(-25px)'}">
        <img v-if="experienceImage" :src="require(`@/assets/experience/${experienceImage}`)" class="shadow" style="width: 100%; height: 100%">
      </div>
    </div>
    <div style="grid-column: 2">
      <span class="experience-hint">hover over experiences to reveal additional images!</span>
      <ExperienceCard dates="Incoming" position="Software Engineer Intern" org="Juniper Networks" 
        @mouseover="experienceImage = 'Juniper.jpg'"
        @mouseleave="experienceImage = ''">
        <p>
          I joined Global Services to deploy a LAMP full-stack log analyzer API and website for switch/router/firewall operating systems, working to streamline configuration checks and troubleshooting with custom knowledge base of 800+ error signatures to solve customer cases.
        </p>
      </ExperienceCard>
      <ExperienceCard dates="October 2023 - Present" position="Competitive Programmer" org="International Collegiate Programming Contest (ICPC)" 
        @mouseover="experienceImage = 'ICPC.jpg'"
        @mouseleave="experienceImage = ''">
        <p>
          Having dedicated months to honing our skills in competitive programming since the beginning of the school year,
          my team of 3 representing Santa Clara University entered the ICPC PacNW Div. 2 Regional.
          Together, we clinched the 3rd place in California and ranked an exciting 9th overall in the region!
        </p>
      </ExperienceCard>
      <ExperienceCard dates="April 2023 - April 2024" position="Club Webmaster" org="SCU Association of Computational Machinery"
        @mouseover="experienceImage = 'H4H.jpg'"
        @mouseleave="experienceImage = ''">
        <p>
          SCU ACM is one of the largest student organizations on campus and the leading tech club 
          for organizing workshops, inviting guest speakers, and hosting hackathons. 
          I worked to mantain, update, and expand ACM's sites and cloud management system.
          Access SCU ACM sites
          <a href="https://scuacm.com" target="_blank" style="color: var(--secondary)">here</a>,
          <a href="https://hackforhumanity.io/" target="_blank" style="color: var(--secondary)">here</a>,
          and <a href="https://roblox.scuacm.com/" target="_blank" style="color: var(--secondary)">here!</a>
        </p>
      </ExperienceCard>
      <ExperienceCard dates="May 2023 - August 2023" position="Software Developer Intern" org="Google Summer of Code, IfcOpenShell"
        @mouseover="experienceImage = 'BrickSchema.jpg'"
        @mouseleave="experienceImage = ''">
        <p>
          The project I worked on focused on enhancing the smart building development tool in IfcOpenShell's Blender plugin, 
          <a href="https://blenderbim.org/" target="_blank" style="color: var(--secondary)">BlenderBIM.</a>
          Here, I worked to combine the
          <a href="https://technical.buildingsmart.org/standards/ifc/" target="_blank">IFC</a> (Industry Foundation Classes) and
          <a href="https://brickschema.org/" target="_blank" style="color: var(--secondary)">BrickSchema</a> semantic structures,
          with the shared goal of advancing the standard exchange of building information and establishing more enriched building 
          management systems. My final report is published
          <a href="https://gist.github.com/rileywong311/c5dd453740ac7e80107398032698b081"  target="_blank" style="color: var(--secondary)">here</a>.
        </p>
      </ExperienceCard>
      <ExperienceCard dates="June 2022 - August 2022" position="Student Visitor" org="University of California, Berkeley"
        @mouseover="experienceImage = 'Berkeley.jpg'"
        @mouseleave="experienceImage = ''">
        <p>
          As a visiting student for the summer, I took the popular “The Structure and Interpretation of Computer Programs”
          (<a href="https://cs61a.org/" target="_blank">COMPSCI 61A</a>) class as well as the data science class
          “Introduction to Computational Techniques in Physics” (<a href="https://classes.berkeley.edu/content/physics-77" target="_blank">PHYSICS 77</a>).
        </p>
      </ExperienceCard>
    </div>
    <div id="SectionBreak" data-section-number="3" style="height: 25px"/>
  </section>

  <!-- Contact Section -->
  <section id="Contact" class="contact" style="scroll-margin-top: 100px ">
    <h2 id="SectionBreak" data-section-number="4" style="grid-column: 1; margin-bottom: auto;">Contact.</h2>
    <div style="grid-column: 2; margin: 50px auto">
      <FormCard  />
      <div style="margin: auto; text-align: center;">
        <div style="margin: 50px;">
            <a href="mailto:rnwong@scu.edu" style="text-decoration: none"><span class="email">rnwong@scu.edu</span></a>
        </div>
        <MediaLogos :center="true" />
      </div>
    </div>
  </section>

  <Footer />
</template>


<script>
import Navbar from '@/components/Navbar.vue';
import MediaLogos from '@/components/MediaLogos.vue';
import ProjectCard from '@/components/ProjectCard.vue';
import SkillTag from '@/components/SkillTag.vue';
import ExperienceCard from '@/components/ExperienceCard.vue';
import FormCard from '@/components/FormCard.vue';
import Footer from '@/components/Footer.vue';

export default {
  name: 'Mainpage',
  components: {
    Navbar,
    MediaLogos,
    ProjectCard,
    SkillTag,
    ExperienceCard,
    FormCard,
    Footer,
  },
  data: () => {
    return {
      navObserver: null,
      intersected: true,
      sectionObserver: null,
      currentSection: 0,
      sections: {
        'top': 0,
        'about': 1,
        'projects': 2,
        'experience': 3,
        'contact': 4,
      },
      experienceImage: '',
    }
  },
  async mounted() {
    // intersection observer
    this.navObserver = new IntersectionObserver(entries => {
      if (entries[0].isIntersecting) {
        this.intersected = true;
      }
      else {
        this.intersected = false;
      }
    }, {threshold: 0.8});
    this.navObserver.observe(document.getElementById("HeroPaddingTop"));

    let allSections = document.querySelectorAll("#SectionBreak")
    this.sectionObserver = new IntersectionObserver(entries => {
      allSections.forEach(section => {
        const position = section.getBoundingClientRect();
        if (position.top >= 0 && position.bottom <= window.innerHeight) {
          this.currentSection = parseInt(section.getAttribute("data-section-number"))
        }
      })
    }, {threshold: 1});
    
    allSections.forEach(section => {
      this.sectionObserver.observe(section);
    })
  
    // load in animations
    this.load();
    
  },
  destroyed() {
    this.navObserver.disconnect();
    this.sectionObserver.disconnect();
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
      // await document.
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
/* =====================
    Load-in animations
======================== */


.outside-screen {
  transform: translateX(-100%);
}

.hidden {
  opacity: 0;
}

.hero-padding {
  height: min(500px, 30vh)
}

/* =====================
    Hero landing
======================== */

.hero {
  margin: 0 5% 0;
  display: flex;
  flex-wrap: wrap-reverse;
  column-gap: 225px;
  row-gap: 20px;
  min-height: min(35vh, 300px);
}

.bio-pic {
  --size: 400px;
  width: var(--size);
  height: var(--size);
  border: 4px solid var(--secondary);
  border-radius: 999px;
  object-fit: cover;
  z-index: -1;
  /* box-shadow: rgba(99, 99, 99, 0.8) 0px 2px 8px 0px; */
}

.hero-to-link {
  font-weight: 400;
  color: var(--secondary);
  /* text-decoration: underline; */
  border-bottom: 1px solid var(--secondary);
  transition: 0.2s;
}

.hero-to-link:hover,
.hero-to-link:focus {
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
    --size: 200px;
    border: 3px solid var(--secondary) ;
  }
}

/* =====================
    About Me Section
======================== */

.about-me {
  margin: 50px 0 50px;
  padding: 30px 5% 30px;
  background: var(--background2);
  display: grid;
  grid-auto-rows: auto;
  gap: min(400px, 20vw);
}

@media screen and (max-width: 1200px) {
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
  column-gap: 200px;
  flex-wrap: wrap;
}

@media screen and (max-width: 768px) {
  .skills {
    column-gap: 100px;
  }
}

@media screen and (max-width: 450px) {
  .skills {
    column-gap: 50px;
  }

  .skills li {
    font-size: 0.875rem;
  }
}

/* =====================
    Projects Section
======================== */

.line-break {
  width: 55%;
  margin: 75px auto 100px;
  border: 1px solid black;
}

/* =====================
    Experience Section
======================== */

.experience {
  margin: 50px 0 50px;
  padding: 30px 5% 30px;
  background: var(--background2);
  display: grid;
  grid-auto-rows: auto;
  column-gap: min(150px, 7.5vw);
}

.experience-image {
  position: -webkit-sticky;
  position: sticky;
  top: 25vh;
  margin-top: 25px;
  width: 500px;
  height: 400px;
  transition: 0.5s;
}

.experience-hint {
  font-size: 0.75rem;
  font-style: italic;
}

.experience-hint::before {
  content:'✦ ';
  font-weight: 600;
}

@media screen and (max-width: 1200px) {
  .experience {
    display: block;
  }

  .experience-image,
  .experience-hint {
    display: none;
  }
}

/* =====================
    Contact Section
======================== */

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