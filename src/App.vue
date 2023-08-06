<template>
  <v-app>
    <v-app-bar>
      <v-container class="d-flex align-center py-0">
        <v-app-bar-title class="pl-0">
          <div class="d-flex align-center">
            <v-avatar
              class="me-3"
              image="https://cdn.vuetifyjs.com/docs/images/logos/v.png"
              rounded="0"
            />

            Alexandre ZANNI
          </div>
        </v-app-bar-title>

        <v-spacer />

        <v-btn-alt
          append-icon="mdi-open-in-new"
          href="https://vuetifyjs.com/components/all/"
          rel="noopener noreferrer"
          target="_blank"
          text="Vuetify Documentation"
        />
      </v-container>
    </v-app-bar>

    <v-main>
      <section id="hero">
        <v-sheet
          class="d-flex align-center pb-16"
          color="#181818"
        >
        <v-parallax src="https://cdn.vuetifyjs.com/images/parallax/material.jpg">
          <v-container class="text-center">
            <v-responsive class="mx-auto" width="500">
              <v-img
                src="https://cdn.vuetifyjs.com/docs/images/logos/v.png"
                height="400"
              />

              <h3 class="text-h3 text-uppercase">
                Développeur
              </h3>
              <h3 class="text-h3 text-uppercase">
                Sites Internet
              </h3>
              <h3 class="text-h3 text-uppercase">
                E-Commerce
              </h3>
              <h3 class="text-h3 text-uppercase">
                Applications Web
              </h3>
              <h3 class="text-h3 text-uppercase">
                App. Mobile
              </h3>

              <p class="mt-4 text-medium-emphasis">
                This is a basic Vuetify 3 application designed to help get your feet wet with the next version of the framework. Visit our <a href="https://vuetifyjs.com/" target="_blank" rel="noopener noreferrer">documentation</a> for more information.
              </p>
            </v-responsive>
          </v-container>
          </v-parallax>
        </v-sheet>
      </section>

      <v-sheet class="py-16">
        <section id="filter">
          <v-container>
            <v-row justify="space-between">
              <v-col cols="auto">
                <v-responsive width="350">
                  <h2 class="text-h4">
                    New customization system
                  </h2>

                  <p class="text-success mt-3">
                    Global Defaults
                  </p>

                  <strong class="mt-3">
                    Version 3 Only
                  </strong>

                  <p class="mt-8">
                    Vuetify 3 has an unprecedented level of customization options that make implementing any design system easy.
                  </p>

                  <p class="mt-8">
                    Assign default values for all components in the library, including nested support.
                  </p>

                  <v-btn
                    class="mt-6"
                    href="https://vuetifyjs.com/features/global-configuration/"
                    target="_blank"
                    rel="noopener noreferrer"
                  >
                    More Information
                  </v-btn>
                </v-responsive>
              </v-col>

              <v-img
                max-width="400"
                src="https://cdn.vuetifyjs.com/store/themes/vite-free/chips-bar.png"
              />
            </v-row>
          </v-container>
        </section>

        <v-container>
          <v-divider class="my-12" />
        </v-container>

        <section id="controls">
          <v-container>
            <v-row justify="space-between">
              <v-col cols="auto">
                <v-responsive width="350">
                  <h2 class="text-h4">
                    Rebuilt from the ground up
                  </h2>

                  <p class="text-success mt-3">
                    Composition API
                  </p>

                  <p class="mt-3">
                    Vuetify 3 uses the Vue composition API to build easy-to-use and feature rich components that work out of the box.
                  </p>

                  <p class="mt-8">
                    <strong>How to use:</strong>

                    Services are now accessed through <strong>use functions</strong> that follow the Vue 3 nomenclature and code styling.
                  </p>

                  <v-btn
                    class="mt-6"
                    href="https://vuetifyjs.com/introduction/why-vuetify/"
                    rel="noopener noreferrer"
                    target="_blank"
                  >
                    More Information
                  </v-btn>
                </v-responsive>
              </v-col>

              <v-img
                max-width="400"
                src="https://cdn.vuetifyjs.com/store/themes/vite-free/slider.png"
              />
            </v-row>
          </v-container>
        </section>

        <v-container>
          <v-divider class="my-12" />
        </v-container>

        <section id="grid">
          <v-container>
            <v-row justify="space-between">
              <v-col cols="auto">
                <v-responsive width="350">
                  <h2 class="text-h4">
                    Skills
                  </h2>

                  <p class="text-success mt-3">
                    Available now!
                  </p>

                  <p class="mt-3">
                    The latest version is here. Use one of our free themes to get a head start!
                  </p>

                  <p class="mt-8">
                    This theme is designed to demonstrate a basic single page application using Vuetify 3.
                  </p>

                  <v-btn class="mt-6">
                    More Information
                  </v-btn>
                </v-responsive>
                <v-responsive width="100%">
                  <div id="canvasContainer"></div>
                  <canvas id="threedeeCanvas"></canvas>
                </v-responsive>
              </v-col>

              <v-img
                max-width="400"
                src="https://cdn.vuetifyjs.com/store/themes/vite-free/layout.png"
              />
            </v-row>
          </v-container>
        </section>
      </v-sheet>

      <v-sheet
        class="py-16"
        color="#181818"
      >
        <section id="grid">
          <v-container>
            <v-row justify="space-between">
              <v-col cols="auto">
                <v-responsive
                  class="overflow-visible"
                  width="350"
                >
                  <h2 class="text-h4">
                    Shape the future of Vuetify
                  </h2>

                  <p class="text-success mt-3">
                    Support Development
                  </p>

                  <strong>Become a sponsor</strong>

                  <p class="mt-8">
                    Vuetify is free to use software under the <a href="https://opensource.org/licenses/MIT" target="_blank" rel="noopener noreferrer">MIT</a> License and requires an extensive amount of time to maintain. Supporting development ensures Vuetify will be actively maintained.
                  </p>

                  <v-btn-alt
                    class="mt-6 "
                    href="https://github.com/sponsors/johnleider"
                    target="_blank"
                    rel="noopener noreferrer"
                    text="Support now"
                    prepend-icon="$vuetify"
                  />
                </v-responsive>
              </v-col>

              <v-img
                max-width="400"
                src="https://cdn.vuetifyjs.com/store/themes/vite-free/vuetify.png"
              />
            </v-row>
          </v-container>
        </section>
      </v-sheet>
    </v-main>

    <v-footer>
      <v-container class="text-overline d-flex align-center justify-space-between">
        <div>
          Copyright &copy; 2016-{{ (new Date()).getFullYear() }} Vuetify, LLC
        </div>
      </v-container>
      <v-container class="text-overline d-flex align-center justify-space-between">
        <v-input>
          <input id="myInput" type="text" value="zannialexandre@outlook.fr" size="4" style="text-align: center; width: 300px;">
        </v-input>
        <v-btn-alt prepend-icon="mdi-email"
          text="Copier"
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
      const threedeeCanvas = document.getElementById('threedeeCanvas')

      const imgFigma = 'https://upload.wikimedia.org/wikipedia/commons/3/33/Figma-logo.svg'
      const imgVue = 'https://upload.wikimedia.org/wikipedia/commons/thumb/9/95/Vue.js_Logo_2.svg/768px-Vue.js_Logo_2.svg.png?20170919082558'
      const imgWordpress = 'https://upload.wikimedia.org/wikipedia/commons/thumb/0/09/Wordpress-Logo.svg/2048px-Wordpress-Logo.svg.png'
      const imgJavascript = 'https://upload.wikimedia.org/wikipedia/commons/thumb/9/99/Unofficial_JavaScript_logo_2.svg/2048px-Unofficial_JavaScript_logo_2.svg.png'
      const imgHtmlcss = 'https://upload.wikimedia.org/wikipedia/commons/1/10/CSS3_and_HTML5_logos_and_wordmarks.svg'
      const imgPhp = 'https://upload.wikimedia.org/wikipedia/commons/thumb/2/27/PHP-logo.svg/2560px-PHP-logo.svg.png'

      const materialVue = this.loadTexture(imgVue)
      const materialFigma = this.loadTexture(imgFigma)
      const materialWordpress = this.loadTexture(imgWordpress)
      const materialJavascript = this.loadTexture(imgJavascript)
      const materialHtmlcss = this.loadTexture(imgHtmlcss)
      const materialPhp = this.loadTexture(imgPhp)

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

      const cubeFigma = new THREE.Mesh(geometryCube, materialFigma)
      cubeFigma.position.set(-2.5, 0, 0)
      scene.add(cubeFigma)

      const cubeVue = new THREE.Mesh(geometryCube, materialVue)
      cubeVue.position.set(0, 2.5, 0)
      scene.add(cubeVue)

      const cubeWordpress = new THREE.Mesh(geometryCube, materialWordpress)
      cubeWordpress.position.set(-2.5, 2.5, 0)
      scene.add(cubeWordpress)

      const cubeJavascript = new THREE.Mesh(geometryCube, materialJavascript)
      cubeJavascript.position.set(2.5, 0, 0)
      scene.add(cubeJavascript)

      const cubeHtmlcss = new THREE.Mesh(geometryCube, materialHtmlcss)
      cubeHtmlcss.position.set(0, 0, 0)
      scene.add(cubeHtmlcss)

      const cubePhp = new THREE.Mesh(geometryCube, materialPhp)
      cubePhp.position.set(2.5, 2.5, 0)
      scene.add(cubePhp)

      const objects = []
      objects.push(cubeFigma, cubeVue, cubeWordpress, cubeJavascript, cubeHtmlcss, cubePhp)

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
    methods: {
      loadTexture (textureUrl) {
        // MeshStandardMaterial,  MeshNormalMaterial, MeshPhongMaterial, MeshLambertMaterial or LineBasicMaterial
        const loader = new THREE.TextureLoader()
        const numberFacesObject = 6
        const materialArray = []
        for (let i = 1; i <= numberFacesObject; i++) {
          if (i === 5) {
            materialArray.push(new THREE.MeshBasicMaterial({ color: 0xffffff, map: loader.load(textureUrl) }))
          } else {
            materialArray.push(new THREE.MeshNormalMaterial({ color: 'black' }))
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

<!-- background: linear-gradient(to bottom, #201c2f 0%, #100751 100%); -->
<style>
  #threedeeCanvas {
    width: 100vw;
    height: 100vh;
    display: block;
    top: 0;
    left: 0;
    z-index: 1;
  }
</style>
