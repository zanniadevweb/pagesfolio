<template>
  <v-app>
    <v-app-bar>
      <v-container class="d-flex align-center py-0">
        <v-app-bar-title class="pl-0">
          <div class="d-flex align-center word">
            Alexandre ZANNI
          </div>
        </v-app-bar-title>

        <input
          id="myInput"
          type="text"
          value="zannialexandre@outlook.fr"
          size="4"
          style="text-align: center; width: 300px; border: none; outline: none;"
        >

        <v-btn-alt
          prepend-icon="mdi-email"
          text="Copier E-mail"
          @click="copyTextFromInput"
        />

        <v-spacer />

        <v-btn-alt
          prepend-icon="mdi-linkedin"
          append-icon="mdi-open-in-new"
          href="https://www.linkedin.com/in/alexandre-zanni-232884187"
          rel="noopener noreferrer"
          target="_blank"
          text="Linkedin"
        />
      </v-container>
    </v-app-bar>

    <v-main>
      <section id="hero">
        <v-sheet
          class="d-flex align-center pb-16"
          color="#181818"
        >
          <v-parallax src="https://cdn.vuetifyjs.com/images/parallax/material2.jpg">
            <v-container class="text-center">

              <v-responsive class="mx-auto" width="500">
                <v-img
                  src="https://cdn.vuetifyjs.com/docs/images/logos/v.png"
                  height="400"
                />

                <v-parallax color="red" src="https://cdn.vuetifyjs.com/images/backgrounds/vbanner.jpg" class="rounded-card">
                  <v-container class="text-center">
                    <h2 class="text-h3 text-uppercase text-white font-weight-black stroke-text-black">
                      Développeur
                    </h2>
                  </v-container>
                  <v-container class="text-center">
                    <h2 class="text-h3 text-uppercase text-white font-weight-bold text-decoration-overline stroke-text-black">
                      Sites Internet
                    </h2>
                    <h2 class="text-h3 text-uppercase text-white font-weight-bold stroke-text-black">
                      E-Commerce
                    </h2>
                    <h2 class="text-h3 text-uppercase text-white font-weight-bold stroke-text-black">
                      Applications Web
                    </h2>
                    <h2 class="text-h3 text-uppercase text-white font-weight-bold stroke-text-black">
                      Mobile Friendly
                    </h2>
                  </v-container>
                </v-parallax>

                <v-container class="text-center">
                  <p class="mt-4 text-black font-weight-bold">
                    Alexandre ZANNI offre des services de freelance en tant que
                    Développeur Web. Envoyez un mail via le bouton :
                  </p>
                </v-container>
                <v-container class="text-center">
                  <v-btn
                    color="rgb(var(--v-theme-primary)) !important"
                    class="v-btn-plain text-black"
                    prepend-icon="mdi-email"
                    text="Copier E-mail"
                    @click="copyTextFromInput"
                  />
                </v-container>

              </v-responsive>
            </v-container>
          </v-parallax>
        </v-sheet>
      </section>

      <v-sheet class="py-16">

        <section id="grid">
          <v-container>
            <v-row justify="space-between">
              <v-col cols="auto">
                <v-responsive width="100%">
                  <h2 class="text-h4">
                    Mes compétences
                  </h2>

                  <div id="containerAlternateText">
                    <span id="text1" />
                    <span id="text2" />
                  </div>
                  <svg id="filters">
                    <defs>
                      <filter id="threshold">
                        <feColorMatrix
                          in="SourceGraphic"
                          type="matrix"
                          values="1 0 0 0 0
                              0 1 0 0 0
                              0 0 1 0 0
                              0 0 0 255 -140"
                        />
                      </filter>
                    </defs>
                  </svg>
                </v-responsive>
                <v-responsive width="100%">
                  <div id="canvasContainer" />
                  <canvas id="threedeeCanvas" />
                </v-responsive>
                <p class="mt-3">
                  Design : Figma, Adobe Photoshop, Adobe Illustrator...
                </p>
                <p class="mt-3">
                  Front-End : HTML / CSS, Javascript, Vue.js...
                </p>
                <p class="mt-3">
                  Back-End : SQL, PHP, Symfony, Laravel...
                </p>
                <p class="mt-3">
                  Supports : Desktop & Mobile friendly
                </p>
                <p class="mt-3">
                  E-Commerce : WordPress, Magento
                </p>
                <p class="mt-3">
                  SEO : Naturel, comme le référencement !
                </p>
              </v-col>
            </v-row>
          </v-container>
        </section>
      </v-sheet>

      <v-sheet
        class="py-16"
        color="#181818"
      >
      </v-sheet>
    </v-main>

    <v-footer>
      <v-container class="text-overline d-flex align-center justify-space-between">
        <div>
          Copyright &copy; {{ (new Date()).getFullYear() }} Alexandre ZANNI
        </div>
      </v-container>
      <v-container class="text-overline d-flex align-center justify-space-between">
        <v-input>
          <input
            type="text"
            value="zannialexandre@outlook.fr"
            size="4"
            style="text-align: center; width: 300px; border: none; outline: none;"
          >
        </v-input>
        <v-btn-alt
          prepend-icon="mdi-email"
          text="Copier E-mail"
          @click="copyTextFromInput"
        />
      </v-container>
      <v-icon icon="$vuetify" size="x-large" />
    </v-footer>
  </v-app>
</template>

<script>
  import { defineComponent } from 'vue'
  import * as THREE from 'three'
  import { aliases, mdi } from 'vuetify/iconsets/mdi'

  // https://pictogrammers.github.io/@mdi/font/1.1.34/
  export default defineComponent({
    icons: {
      defaultSet: 'mdi',
      aliases,
      sets: {
        mdi,
      },
    },
    mounted () {
      this.animateTypeWriter()
      this.animateBlurryTextChange()
      this.animateThreedCubes()
    },
    methods: {
      animateTypeWriter () {
        const words = ['Bonjour,', 'Mon nom', 'est ...', 'Alexandre', 'ZANNI']
        let part = ''
        let i = 0
        let offset = 0
        const len = words.length
        let forwards = true
        let skipCount = 0
        const skipDelay = 15
        const speed = 70
        const wordflick = function () {
          setInterval(function () {
            if (forwards) {
              if (offset >= words[i].length) {
                ++skipCount
                if (skipCount === skipDelay) {
                  forwards = false
                  skipCount = 0
                }
              }
            } else {
              if (offset === 0) {
                forwards = true
                i++
                offset = 0
                if (i >= len) {
                  i = 0
                }
              }
            }
            part = words[i].substr(0, offset)
            console.log(part)
            if (skipCount === 0) {
              if (forwards) {
                offset++
              } else {
                offset--
              }
            }
            document.querySelector('.word').textContent = part
          }, speed)
        }

        document.addEventListener('DOMContentLoaded', function () {
          wordflick()
        })
      },
      animateBlurryTextChange () {
        const elts = {
          text1: document.getElementById('text1'),
          text2: document.getElementById('text2'),
        }

        const texts = [
          'WordPress',
          'Magento',
          'PHP',
          'HTML',
          'CSS',
          'Javascript',
          'SQL',
          'Python',
          'Figma',
          'Photoshop',
          'Illustrator',
          'SEO',
          'Bootstrap',
          'Vuetify',
          'Vue.js',
          'Symfony',
          'Laravel',
        ]

        const morphTime = 1
        const cooldownTime = 0.25

        let textIndex = texts.length - 1
        let time = new Date()
        let morph = 0
        let cooldown = cooldownTime

        elts.text1.textContent = texts[textIndex % texts.length]
        elts.text2.textContent = texts[(textIndex + 1) % texts.length]

        function doMorph () {
          morph -= cooldown
          cooldown = 0

          let fraction = morph / morphTime

          if (fraction > 1) {
            cooldown = cooldownTime
            fraction = 1
          }

          setMorph(fraction)
        }

        function setMorph (fraction) {
          elts.text2.style.filter = `blur(${Math.min(8 / fraction - 8, 100)}px)`
          elts.text2.style.opacity = `${Math.pow(fraction, 0.4) * 100}%`

          fraction = 1 - fraction
          elts.text1.style.filter = `blur(${Math.min(8 / fraction - 8, 100)}px)`
          elts.text1.style.opacity = `${Math.pow(fraction, 0.4) * 100}%`

          elts.text1.textContent = texts[textIndex % texts.length]
          elts.text2.textContent = texts[(textIndex + 1) % texts.length]
        }

        function doCooldown () {
          morph = 0

          elts.text2.style.filter = ''
          elts.text2.style.opacity = '100%'

          elts.text1.style.filter = ''
          elts.text1.style.opacity = '0%'
        }

        function animate () {
          requestAnimationFrame(animate)

          const newTime = new Date()
          const shouldIncrementIndex = cooldown > 0
          const dt = (newTime - time) / 1000
          time = newTime

          cooldown -= dt

          if (cooldown <= 0) {
            if (shouldIncrementIndex) {
              textIndex++
            }

            doMorph()
          } else {
            doCooldown()
          }
        }

        animate()
      },
      animateThreedCubes () {
        const threedeeCanvas = document.getElementById('threedeeCanvas')

        const imgWordpress = 'wordpress.png'
        const imgBootstrap = 'bootstrap.png'
        const imgFigma = 'figma.png'
        const imgPhp = 'php.png'
        const imgHtmlcss = 'htmlcss.png'
        const imgJavascript = 'javascript.png'
        const imgSymfony = 'symfony.png'
        const imgVue = 'vue.png'
        const imgSql = 'sql.png'

        const materialWordpress = this.loadTexture(imgWordpress)
        const materialBootstrap = this.loadTexture(imgBootstrap)
        const materialFigma = this.loadTexture(imgFigma)
        const materialHtmlcss = this.loadTexture(imgHtmlcss)
        const materialJavascript = this.loadTexture(imgJavascript)
        const materialPhp = this.loadTexture(imgPhp)
        const materialSymfony = this.loadTexture(imgSymfony)
        const materialVue = this.loadTexture(imgVue)
        const materialSql = this.loadTexture(imgSql)

        // Create an empty scene
        const scene = new THREE.Scene()

        // Create a basic perspective camera
        const camera = new THREE.PerspectiveCamera(75, window.innerWidth / window.innerHeight, 0.1, 1000)
        camera.position.z = 5

        // Create a renderer with Antialiasing
        const renderer = new THREE.WebGLRenderer({ alpha: true, canvas: threedeeCanvas })

        // Configure renderer clear color
        // renderer.setClearColor("#000000")
        renderer.setClearColor(0x000000, 0) // Fond transparent

        // Configure renderer size
        renderer.setSize(window.innerWidth, window.innerHeight)

        // Append Renderer to DOM
        document.getElementById('canvasContainer').appendChild(renderer.domElement)

        ;(function () {
          // add a ambient light
          const light1 = new THREE.AmbientLight(0x020202)

          scene.add(light1)
          // add a light in front
          const light2 = new THREE.DirectionalLight('white', 1)
          light2.position.set(0.5, 0.5, 2)
          scene.add(light2)
          // add a light behind
          const light3 = new THREE.DirectionalLight('white', 0.75)
          light3.position.set(-0.5, 2.5, -2)
          scene.add(light3)
        })()

        const geometryCube = new THREE.BoxGeometry(1, 1, 1)

        const cubeWordpress = new THREE.Mesh(geometryCube, materialWordpress)
        cubeWordpress.position.set(-2.5, 2.5, 0)
        scene.add(cubeWordpress)

        const cubeBootstrap = new THREE.Mesh(geometryCube, materialBootstrap)
        cubeBootstrap.position.set(0, 2.5, 0)
        scene.add(cubeBootstrap)

        const cubeFigma = new THREE.Mesh(geometryCube, materialFigma)
        cubeFigma.position.set(2.5, 2.5, 0)
        scene.add(cubeFigma)

        const cubePhp = new THREE.Mesh(geometryCube, materialPhp)
        cubePhp.position.set(-2.5, 0, 0)
        scene.add(cubePhp)

        const cubeHtmlcss = new THREE.Mesh(geometryCube, materialHtmlcss)
        cubeHtmlcss.position.set(0, 0, 0)
        scene.add(cubeHtmlcss)

        const cubeJavascript = new THREE.Mesh(geometryCube, materialJavascript)
        cubeJavascript.position.set(2.5, 0, 0)
        scene.add(cubeJavascript)

        const cubeSymfony = new THREE.Mesh(geometryCube, materialSymfony)
        cubeSymfony.position.set(-2.5, -2.5, 0)
        scene.add(cubeSymfony)

        const cubeVue = new THREE.Mesh(geometryCube, materialVue)
        cubeVue.position.set(0, -2.5, 0)
        scene.add(cubeVue)

        const cubeSql = new THREE.Mesh(geometryCube, materialSql)
        cubeSql.position.set(2.5, -2.5, 0)
        scene.add(cubeSql)

        const objects = []
        objects.push(
          cubeWordpress, cubeBootstrap, cubeFigma,
          cubePhp, cubeHtmlcss, cubeJavascript,
          cubeVue, cubeSymfony, cubeSql
        )

        // Render Loop
        const render = function () {
          requestAnimationFrame(render)

          for (let k = 0; k < objects.length; k++) {
            objects[k].rotation.x += Math.sin(Date.now() * 0.01) * Math.PI * 0.0005
            objects[k].rotation.y += Math.sin(Date.now() * 0.001) * Math.PI * 0.0005
          }

          // Render the scene
          renderer.render(scene, camera)
        }

        render()
      },
      loadTexture (textureUrl) {
        // MeshStandardMaterial,  MeshNormalMaterial, MeshPhongMaterial, MeshLambertMaterial or LineBasicMaterial
        const loader = new THREE.TextureLoader()
        const numberFacesObject = 6
        const materialArray = []
        for (let i = 1; i <= numberFacesObject; i++) {
          if (i === 5) {
            materialArray.push(new THREE.MeshBasicMaterial({ color: 0xffffff, map: loader.load(textureUrl) }))
          } else {
            materialArray.push(new THREE.MeshNormalMaterial())
          }
        }
        return materialArray
      },
      copyTextFromInput () {
        const copyText = document.getElementById('myInput')
        copyText.select()
        copyText.setSelectionRange(0, 99999) // For mobile devices
        document.execCommand('copy')
        alert('Copied the text: ' + copyText.value)
      },
    },
  })
</script>

<!-- gradient="to bottom, #201c2f 0%, #100751 100%" -->
<style>
  @import url("https://fonts.googleapis.com/css?family=Raleway:900&display=swap");
  .rounded-card{
    border-radius:50px;
  }
  .stroke-text-black {
    -webkit-text-stroke-width: 1px;
    -webkit-text-stroke-color: black;
  }
  .stroke-text-white {
    -webkit-text-stroke-width: 0.1px;
    -webkit-text-stroke-color: white;
  }
  body {
      margin: 0px;
  }
  #containerAlternateText {
      position: absolute;
      margin: auto;
      width: 100vw;
      height: 80pt;
      top: 0;
      bottom: 0;
      z-index: 99;

      filter: url(#threshold) blur(0.6px);
  }
  #text1,
  #text2 {
      position: absolute;
      width: 100%;
      display: inline-block;
      font-family: "Raleway", sans-serif;
      font-size: 80pt;
      text-align: center;
      user-select: none;
  }
  .word {
    font: normal 'tahoma';
    text-shadow: 5px 2px #222324, 2px 4px #222324, 3px 5px #222324;
  }
  .v-btn-plain > .v-btn__underlay {
    opacity: 1;
  }
</style>
