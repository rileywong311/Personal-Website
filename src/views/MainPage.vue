<template>
  <Navbar :showShadow="!intersected" :currentSection="currentSection"/>

  <div id="HeroPaddingTop" class="hero-padding"/>
  <section id="Hero" class="hero">
    <div id="SectionBreak" data-section-number="0" style="overflow: hidden">
      <h1 ref="heroHeading1" style="transition: ease-in-out 1.25s" class="outside-screen">Hi there!</h1>
      <h1 ref="heroHeading2" style="transition: ease-in-out 1.5s" class="outside-screen">I'm <span style="color: var(--secondary)">Riley Wong.</span></h1>
      <p ref="heroParagraph" style="transition: ease-in-out 1.75s; max-width: 70ch" class="outside-screen">
        I value independence, strong communication, and the opportunity to learn from others! Feel free to
        <span @click="toProjects" class="hero-to-link">check my work below</span>
        or <span @click="toContact" class="hero-to-link">reach out to me here!</span>
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

  <section id="AboutMe" style="scroll-margin-top: 20vh;" class="about-me">
    <h2 id="SectionBreak" data-section-number="1" style="grid-column: 1; margin-bottom: auto">About Me.</h2>
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
            <div style="margin-top: 5px; margin-left: 37.5px; font-weight: 400; font-size: 30px">Résumé</div>
            <div style="margin-left: 35px">
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
      <div id="SectionBreak" data-section-number="1" style="height: 25px"/>
    </div>
  </section>
  
  <section id="Projects" style="scroll-margin-top: 15vh; margin: 50px 0 50px; padding: 30px 5% 30px">
    <h2 id="SectionBreak" data-section-number="2" style="margin-bottom: 50px">Projects.</h2>
    <ProjectCard name="gourm.ai"
                  type="vid"
                  media="https://www.youtube.com/embed/R8uRnmXLSpo"
                  :links="[
                    {link: 'https://github.com/rileywong311/CalHack-AI-2023', name: 'GitHub'}
                  ]">
      <p>
       An AI-powered cooking assistant designed to simplify and enhance the culinary experience. 
       I primarily worked on the frontend, but I also communicated prompts with the backend team as we focused on parsing GPT-4 effectively.
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
    <ProjectCard name="Hands For Help"
                 type="vid"
                 media="https://www.youtube.com/embed/LOz8XoQQS2A"
                 :links="[
                    {link: 'https://github.com/rileywong311/H4H-2023', name: 'GitHub'}
                  ]">
      <p>
        Supported an internet-independent mode of resource tracking and sharing through “digital handshakes.”
        This was acheived by transfering data user-to-user with QR codes storing JSON.
        I worked on the backend to locate and parse highest-rated locations."   
      </p>
      <div style="display: flex; row-gap: 12px; column-gap: 5px; flex-wrap: wrap">
        <SkillTag v-for="skill in ['Dart', 'Python', 'Flutter', 'Flask', 'HiveDB', 'QR Codes', 'Google Services API']"> {{ skill }} </SkillTag>
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
        Distilled the chaotic region of the logistic map as a source of entropy for intrinsic random number generation.
        Ran a series of statistical tests on the generator.
      </p>
      <div style="display: flex; row-gap: 12px; column-gap: 5px; flex-wrap: wrap">
        <SkillTag v-for="skill in ['Python', 'Matplotlib', 'Scipy', 'Computational Physics']"> {{ skill }} </SkillTag>
      </div>
    </ProjectCard>
    <hr class="line-break" />
    <ProjectCard name="NestNotifications"
                 type="vid"
                 media="https://www.youtube.com/embed/39aNTYJP-SQ"
                 :links="[
                    {link: 'https://github.com/rileywong311/INRIX-Hack-22', name: 'GitHub'}
                  ]">
      <p>
        An alternative location tracking app that provides independence among adolescents and more privacy for all users
        by measuring time and distance rather than providing a direct location.
        I worked on the backend to record travel-time polygons and location within the zone."     
      </p>
      <div style="display: flex; row-gap: 12px; column-gap: 5px; flex-wrap: wrap">
        <SkillTag v-for="skill in ['Dart', 'Python', 'Flutter', 'Flask', 'SQLite', 'INRIX API', 'Twilio API', 'Google Maps API']"> {{ skill }} </SkillTag>
      </div>
    </ProjectCard>
    <div id="SectionBreak" data-section-number="2" style="height: 25px"/>
  </section>

  <section id="Experience" style="scroll-margin-top: 15vh; margin: 50px 0 50px; padding: 30px 5% 50px; background: var(--background2)">
    <h2 id="SectionBreak" data-section-number="3">Experience.</h2>
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
    <div id="SectionBreak" data-section-number="3" style="height: 25px"/>
  </section>

  <section id="Contact" class="contact" style="scroll-margin-top: 100px ">
    <h2 id="SectionBreak" data-section-number="4" style="grid-column: 1; margin-bottom: auto;">Contact.</h2>
    <div style="grid-column: 2; margin: 50px auto">
      <FormCard  />
      <div style="margin: auto; text-align: center;">
        <a href="mailto:rnwong@scu.edu" style="text-decoration: none"><div style="margin: 50px;"><span class="email">rnwong@scu.edu</span></div></a>
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
      }
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
          this.currentSection = section.getAttribute("data-section-number")
        }
      })
    }, {threshold: 1});
    
    allSections.forEach(section => {
      this.sectionObserver.observe(section);
    })
  
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
  column-gap: 300px;
  row-gap: 50px;
  min-height: min(35vh, 300px);
}

.bio-pic {
  --size: 300px;
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
  /* text-decoration: underline; */
  border-bottom: 1px solid var(--secondary);
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
    --size: 175px;
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