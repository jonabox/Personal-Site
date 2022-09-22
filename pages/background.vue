<template>
  <v-layout>
    <v-flex>
      <v-card flat color="transparent" class="my-3">
        <v-card-text
          class="display-1 text-center text-wrap white--text"
          style="word-break: normal"
          >Background</v-card-text
        >
      </v-card>

      <v-card flat color="transparent" class="my-3 white--text">
        <v-card-title>Education</v-card-title>
        <v-card-subtitle class="white--text"
          >Massachusetts Institute of Technology</v-card-subtitle
        >
        <v-card-text class="white--text">
          <p>Masters of Engineering Program in Computer Systems, 2022</p>
          <p>Bachelor of Science in Computer Science, 2020</p>
        </v-card-text>
      </v-card>

      <v-card flat color="transparent" class="my-3">
        <v-card-title>Work and Research</v-card-title>
        <v-card-text class="white--text">
          <h4>Cybersecurity at MIT Sloan Research Assistant</h4>
          <ul>
            <li>
              Designed a web application to investigate the interaction of
              automated adversaries operating in simulated enterprise network
              environments by utilizing open source tools such as Microsoft
              CyberBattleSim and D3-force. Source code available
              <a
                href="https://github.com/jonabox/Scenario-Based-Simulation-Platform"
                >here</a
              >.
            </li>
          </ul>
        </v-card-text>
        <v-card-text class="white--text">
          <h4>Virtualitics Machine Learning Internship</h4>
          <ul>
            <li>
              Leveraged ML.NET to implement Time Series Forecasting; ran
              benchmarks with synthetic and real-world data and conducted
              competitor analysis
            </li>
          </ul>
        </v-card-text>
        <v-card-text class="white--text">
          <h4>
            CSAIL Document Processing Research Assistant and Project Coordinator
          </h4>
          <ul>
            <li>
              Collaborated with 8 fintech companies to coordinate internal
              project proposals relating to the processing of corporate
              documents using preprocessing techniques and OCR
            </li>
            <li>
              Lead a team of 6 undergraduates and coordinated weekly milestones
            </li>
            <li>
              Held weekly meetings to discuss progress and timelines with team
              members and company sponsors
            </li>
          </ul>
        </v-card-text>
        <v-card-text class="white--text">
          <h4>Multi-Party Computation Project</h4>
          <ul>
            <li>
              Designed the foundation for a web platform that would encapsulate
              a bare-bones C++ implementation of several cryptographic and
              multi-party computations
            </li>
            <li>
              Worked on transcribing the C++ codebase into JavaScript using
              Emscripten, a tool that compiles C++ into WebAssembly
            </li>
            <li>
              Setup a MySQL database for the storage of credentials and an SMTP
              server to handle email tokens
            </li>
            <li>
              Followed many security best practices, including salting/hashing
              passwords, CSRF tokens, CSP headers, and creating TLS certificates
              using Let'sEncrypt
            </li>
          </ul>
        </v-card-text>

        <v-card-text class="white--text">
          <h4>Vivint SmartHome Internship</h4>
          <ul>
            <li>
              Worked on circumventing corporate firewalls using NAT traversing
              servers for WebRTC applications
            </li>
            <li>
              Used Docker, Kubernetes, Terraform, and Google’s Cloud Platform to
              automate the setup of said servers and scale the infrastructure
            </li>
          </ul>
        </v-card-text>

        <v-card-text class="white--text">
          <h4>Cells for Cells Internship</h4>
          <ul>
            <li>
              Worked with a team of biotech investigators and facilitated CAD
              design, 3D printing, and Arduino circuit logistics to design a
              syringe pump embedded robotic arm to be used for precise
              bio-filament placement
            </li>
          </ul>
        </v-card-text>
      </v-card>

      <v-card flat color="transparent" class="my-3">
        <v-card-title>Skills</v-card-title>
        <v-container fluid>
          <v-row justify="start" no-gutters>
            <v-col cols="auto" class="mr-6">
              <v-card-text class="py-0">
                <h4>Proficient Programming Languages and Frameworks</h4>
                <ul class="mb-6">
                  <li>Python</li>
                  <li>JavaScript</li>
                  <li>Vue.js</li>
                  <li>React.js</li>
                  <li>Java</li>
                  <li>Git</li>
                </ul>
                <h4>Software Tools</h4>
                <ul class="mb-6">
                  <li>Amazon Web Services</li>
                  <li>Google Cloud</li>
                  <li>Docker</li>
                  <li>Terraform</li>
                  <li>MySQL</li>
                  <li>MongoDB</li>
                  <li>Unix Command-Line</li>
                </ul>
              </v-card-text>
            </v-col>
            <v-col cols="auto">
              <v-card-text class="py-0">
                <h4>Familiar Programming Languages and Frameworks</h4>
                <ul class="mb-6">
                  <li>Rust</li>
                  <li>HTML/CSS</li>
                  <li>SQL</li>
                  <li>Angular.js</li>
                  <li>React.js</li>
                  <li>C++</li>
                </ul>
                <h4>Other Skills</h4>
                <ul class="mb-6">
                  <li>Fully Bilingual (Spanish, English)</li>
                  <li>Photoshop</li>
                  <li>Adobe After Effects</li>
                  <li>FL Studio</li>
                  <li>Intermediate Music Theory</li>
                  <li>AutoCAD</li>
                  <li>Makerspace Tools</li>
                  <li>Arduino and Teensy Microcontrollers</li>
                  <li>Electronic Lab Tools</li>
                </ul>
              </v-card-text>
            </v-col>
          </v-row>
        </v-container>
      </v-card>
    </v-flex>
  </v-layout>
</template>

<script>
import Logo from "~/components/Logo.vue";
import VuetifyLogo from "~/components/VuetifyLogo.vue";

export default {
  components: {
    Logo,
    VuetifyLogo,
  },
};
</script>