<template>
  <div id="Hero" class="hero">
    <div>
      <h1>Hi there!</h1>
      <h1>I'm <span style="color: var(--secondary)">Riley Wong.</span></h1>
      <p style="max-width: 70ch;">
        I value independence, communication, and the ability to learn from others! Feel free to <a href="#contact" style="font-weight: 400; color: var(--secondary)">reach out to me here</a> or <a href="#projects" style="font-weight: 400; color: var(--secondary)">check my work below!</a>
      </p>
      <!-- <span style="border: 2px solid black; border-radius: 999px; margin: 5px; padding: 8px 25px 8px; font-weight: 400">
        Check out my work!
      </span> -->
      <div style="margin-top: 50px">
        <MediaLogos />
      </div>
    </div>
    <div class="bio-pic-container">
      <img src="@/assets/RileyWong.jpg" alt="Bio Picture" class="bio-pic" />
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

      <div style="display: flex">
        <h4>Skills</h4>
        <svg width="100%" height="25px">
          <line x1="5%" y1="50%" x2="95%" y2="50%" style="stroke: black" />
        </svg>
      </div>
      <div class="skills">
        <div>
          <h4 style="margin: 25px 0 10px">Languages:</h4>
          <ul>
            <li>Python</li>
            <li>C++</li>
            <li>JavaScript</li>
            <li>HTML/CSS</li>
            <li>SQL</li>
          </ul>
        </div>
        <div>
          <h4 style="margin: 25px 0 10px">Frameworks:</h4>
          <ul>
            <li>Flask</li>
            <li>Vue.js</li>
            <li>React.js</li>
            <li>Matplotlib</li>
            <li>Scipy</li>
          </ul>
        </div>
        <div>
          <h4 style="margin: 25px 0 10px">Tools:</h4>
          <ul>
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
                 description="An AI-powered cooking assistant designed to simplify and enhance the culinary experience. Constructed from GPT-4."
                 media="https://www.youtube.com/embed/R8uRnmXLSpo"
                 link="https://github.com/rileywong311/CalHack-AI-2023"
                 />
    <hr class="line-break" />
    <ProjectCard name="Blender Addon: Screen to Text"
                 description="Renders the current viewport and overlays the screen with the image as ASCII characters. This utilized the Blender API's off-screen rendering and custom texture drawing features."
                 media="https://www.youtube.com/embed/iYzjLTMy2-c"
                 link="https://github.com/rileywong311/Blender_ScreenToText"
                 />
    <hr class="line-break" />
    <ProjectCard name="Hands For Help"
                 description="Supported an internet-independent mode of resource tracking and sharing through “digital handshakes.” This was acheived by transfering data user-to-user with QR codes storing JSON."
                 media="https://www.youtube.com/embed/LOz8XoQQS2A"
                 link="https://github.com/rileywong311/H4H-2023"
                 />
    <hr class="line-break" />
    <ProjectCard name="Logistic Map Psuedo-Random Number Generator"
                 description="Distilled the chaotic region of the logistic map as a source of entropy for intrinsic random number generation. Ran a series of statistical tests on the generator. "
                 media=""
                 link="https://github.com/rileywong311/Logistic-Map-PRNG"
                 />   
    <hr class="line-break" />
    <ProjectCard name="NestNotifications"
                 description="An alternative location tracking app that provides independence among adolescents and more privacy for all users by measuring time and distance rather than providing a direct location."
                 media="https://www.youtube.com/embed/39aNTYJP-SQ"
                 link="https://github.com/rileywong311/INRIX-Hack-22"
                 />              
  </div>
</template>

<script>
import MediaLogos from '@/components/MediaLogos.vue';
import ProjectCard from '@/components/ProjectCard.vue';
export default {
  name: 'Mainpage',
  components: {
    MediaLogos,
    ProjectCard,
  }
}
</script>

<style>
.hero {
  margin: 30vh 5% 0;
  display: flex;
  flex-wrap: wrap-reverse;
  column-gap: 150px;
  row-gap: 40px;
  min-height: 58vh;
}

.bio-pic {
  --size: 250px;
  width: var(--size);
  height: var(--size);
  border: 4px solid var(--secondary);
  border-radius: 999px;
  object-fit: cover;
  z-index: -1;
  box-shadow: rgba(99, 99, 99, 0.8) 0px 2px 8px 0px;
}


@media screen and (max-width: 1100px) {
  .hero {
    margin: 20vh 5% 0;
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
  margin: 35px auto 40px;
  border: 1px solid black;
}

</style>