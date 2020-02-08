<template>
  <v-layout>
    <v-flex>
      <v-card outlined color="rgb(0, 0, 0, 0.1)" class="my-3">
                <v-card-text class="display-3 font-weight-thin text-center" style="word-break: normal">Welcome to my homepage</v-card-text>
      </v-card>

      <v-card outlined color="rgb(0, 0, 0, 0.1)" class="my-3">
        <v-card-title>Education</v-card-title>
        <v-card-subtitle>Massachusetts Institute of Technology</v-card-subtitle>
        <v-card-text>
          <p> Candidate for Masters of Engineering Program in Computer Systems</p> 
          <p> Bachelor of Science in Computer Science, 2019</p> 
        </v-card-text>
      </v-card>

      <v-card outlined color="rgb(0, 0, 0, 0.1)" class="my-3">
        <v-card-title>Work and Research</v-card-title>
        <v-card-text>
          <h4 class="display-7 font-weight-thin">Multi-Party Computation Project</h4>
          <ul>
            <li>Designed the foundation for a web platform that would encapsulate a bare-bones C++ implementation of several cryptographic and multi-party computations</li>
            <li>Worked on transcribing the C++ codebase into JavaScript using Emscripten, a tool that compiles C++ into WebAssembly</li>
            <li>Setup a MySQL database for the storage of credentials and an SMTP server to handle email tokens</li>
            <li>Followed many security best practices, including salting/hashing passwords, CSRF tokens, CSP headers, and creating TLS certificates using Let'sEncrypt</li>
          </ul>
        </v-card-text>

        <v-card-text>
          <h4 class="display-7 font-weight-thin">Vivint SmartHome Internship</h4>
          <ul>
            <li>Worked on circumventing corporate firewalls using NAT traversing servers for WebRTC applications</li>
            <li>Used Docker, Kubernetes, Terraform, and Google’s Cloud Platform to automate the setup of said servers and scale the infrastructure</li>
          </ul>
        </v-card-text>

        <v-card-text>
          <h4 class="display-7 font-weight-thin">Cells for Cells Internship</h4>
          <ul>
            <li>Worked with a team of biotech investigators and facilitated CAD design, 3D printing, and Arduino circuit logistics to design a syringe pump embedded robotic arm to be used for precise bio-filament placement</li>
          </ul>
        </v-card-text>
      </v-card>

      <v-card outlined color="rgb(0, 0, 0, 0.1)" class="my-3">
        <v-card-title>Skills</v-card-title>
        <v-card-text>Fully Bilingual (Spanish, English); Proficiency in Python, Java, JavaScript; Experience with AngularJS, Rust, Express, VueJS, SQL, cloud development (GCP, AWS EC2, Docker, Terraform), Git, HTML, CSS, and C++; Familiar with React, MongoDB, AutoCAD, Unity2D, Android Studio, Photoshop, FL Studio, 2D animation, video editing, 3D printing, Arduino systems, electronic tools, Unix systems, Redis, Gstreamer, WebRTC, FFmpeg</v-card-text>
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
    VuetifyLogo
  }
};
</script>