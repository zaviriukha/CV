<script setup>
import { ref } from "vue";

const props = defineProps({
  msg: String,
});

const count = ref(0);

const data = ref({
  name: "Zaviriukha Valeriia",
  position: "Front-End Developer (Vue.js)",
  contact: {
    email: "v.zaviriukha@gmail.com",
    phone: "(097) 170 70 30",
    git: "https://github.com/zaviriukha",
  },
  summary:
    "Over 6 years of professional experience in Front-end development. For over 2 years have been doing front-end development based on the Vue.js framework. Prior to that, worked on the development of sites for CMS ModX Revolution for 4 years.",
  about: [
    {
      me: "Have extensive experience in Front-end development for projects based on the Shopware 6 and Pimcore CMS, as well as on VueJs. Also have experience in e-commerce development in Germany and Ukraine.",
      involved: [
        {
          title:
            "I was directly involved in communicating with clients on the following topics:",
          details: [
            "Presenting products to clients",
            "Calling to get their product suggestions",
            "Training clients to work with the developed/modified functionality",
          ],
        },
      ],
      partners:
        "I also repeatedly communicated with partner companies on issues of developing new functionality based on their developments, making edits and suggestions to improve the operation of their system.",
      presentations:
        "I was involved in studying and presenting new technologies for the company, in particular, implementing work with Shopware 6 and the associated Vue Storefront.",
    },
  ],
  skills: [
    "Programming language: JavaScript (JS)",
    "JS Framework: Vue.js (Vuex, Vuex ORM)",
    "CMS: Shopware, Pimcore",
    "PWA: Vue Storefront",
    "Component Framework: Vuetify",
    "CSS Framework: Tailwind, Bootstrap",
    "Preprocessors: Sass/Scss, Stylus",
    "UI Design: Figma",
    "Graphic Editors: Photoshop, Illustrator",
    "IDE: WebStorm, PhpStorm, VSCode",
    "Module Bundler: Webpack",
    "Version Control: GIT",
  ],
  experience: [
    {
      company: "Blackbit digital Commerce GmbH",
      position: "Front-End Developer",
      period: "November 2020 - March 2025",
      tasks: [
        {
          title: "Worked on Shopware 6 CMS projects",
          details: [
            "Development and  maintained websites based on shopware 6",
            "Developed custom modules for Shopware 6",
            "Vue Storefront",
          ],
        },
        {
          title: "Worked on Styla storefront projects",
          details: [
            "Developed custom modules using Vue.js",
            "Assembled and maintained websites using the Styla storefront",
            "Provided client consultations on Styla implementation and best practices",
          ],
        },
        {
          title: "Worked on Pimcore CMS projects",
          details: [
            "Websites development",
            "Participation in the development of the storefront module for this CMS",
          ],
        },
      ],
    },
    {
      company: "Diamatic LLC",
      position: "Front-End Developer",
      period: "December 2018 — July 2020",
      tasks: [
        "Development of base components in Vue.js using Vuetify",
        "Using complex state management (Vuex, Vuex ORM)",
        "Converting Figma UI/UX designs to Vue components",
        "Participation in a commercial PWA development project",
        "Using Gridsome for static site generation",
      ],
    },
    {
      company: "DevDroid",
      position: "Junior Front-End Developer",
      period: "November 2017 — October 2018",
      tasks: [
        "Development of the admin panel using Vue.js, Node.js, and MongoDB",
        "Created a WYSIWYG editor based on Vue.js",
        "Website layout and maintenance",
      ],
    },
    {
      company: "IMQ",
      position: "Markup Developer",
      period: "May 2014 — September 2017",
      tasks: [
        "Website layout and optimization",
        "Ongoing website maintenance",
        "Development of new sites according to technical specifications",
        "Migration of sites to CMS ModX",
      ],
    },
  ],
  education: [
    {
      degree: "Master's Degree in Telecommunications and Radio Engineering",
      institution: "State University of Telecommunications",
      period: "2014 — 2016",
    },
    {
      degree: "Bachelor's Degree in Computer Engineering",
      institution: "Kyiv College of Communication",
      period: "2011 — 2014",
    },
  ],
  languages: [
    "English – Upper Intermediate",
    "Ukrainian – Native",
    "Russian – Fluent",
  ],
  certification: [
    "Pimcore – Pimcore Developer, 2024",
    "Shopware 6 – Shopware Developer, 2021",
  ],
});
</script>

<template>
  <div class="max-w-4xl mx-auto p-8 bg-white shadow-lg rounded-lg text-black">
    <header class="mb-8 text-left border-b-2 border-black">
      <h1 class="text-4xl font-bold">{{ data.name }}</h1>
      <h2 class="text-2xl">{{ data.position }}</h2>
    </header>

    <section class="mb-8 contact flex justify-between">
      <div class="w-1/6 text-left">
        <h3 class="text-xl font-semibold">Contact</h3>
      </div>
      <div class="flex flex-col items-start w-2/6">
        <p>
          <span class="font-bold">Email</span>:
          <a :href="'mailto:' + data.contact.email" class="text-blue-500">{{
            data.contact.email
          }}</a>
        </p>
        <p><span class="font-bold">Phone</span>: {{ data.contact.phone }}</p>
        <p>
          <span class="font-bold">Git</span>:
          <a href="{{ data.contact.git }}">{{ data.contact.git }}</a>
        </p>
      </div>
    </section>

    <section class="mb-8 flex justify-between">
      <h3 class="text-xl font-semibold w-1/6 text-left">Summary</h3>
      <div
        v-for="me in data.about"
        :key="me.me"
        class="flex flex-col text-left w-5/6"
      >
        <p class="mb-5">{{ me.me }}</p>
        <template v-for="(involve, index) in me.involved" :key="index">
          {{ involve.title }}
          <ul class="list-circle pl-5 mb-5">
            <li
              v-for="(detail, i) in involve.details"
              :key="i"
              class="list-disc"
            >
              {{ detail }}
            </li>
          </ul>
        </template>
        <p>{{ me.partners }}</p>
        <p>{{ me.presentations }}</p>
      </div>
    </section>

    <section class="mb-8 flex justify-between">
      <h3 class="text-xl font-semibold w-1/6 text-left">Professional Skills</h3>
      <div class="flex text-left w-5/6">
        <ul class="list-disc pl-5">
          <li v-for="skill in data.skills" :key="skill">{{ skill }}</li>
        </ul>
      </div>
    </section>

    <section class="mb-8 flex justify-between">
      <h3 class="text-xl font-semibold w-1/6 text-left">Work Experience</h3>
      <div class="flex text-left w-5/6 flex-col">
        <div v-for="job in data.experience" :key="job.company" class="mb-4">
          <h4 class="text-lg font-semibold">
            {{ job.position }} - {{ job.company }}
          </h4>
          <p class="text-sm text-gray-600">{{ job.period }}</p>
          <ul class="list-disc pl-5">
            <template v-for="(task, index) in job.tasks" :key="index">
              <li v-if="typeof task === 'string'">{{ task }}</li>
              <li v-else>
                {{ task.title }}
                <ul class="list-circle pl-5">
                  <li v-for="(detail, i) in task.details" :key="i">
                    {{ detail }}
                  </li>
                </ul>
              </li>
            </template>
          </ul>
        </div>
      </div>
    </section>

    <section class="mb-8 flex justify-between">
      <h3 class="text-xl font-semibold w-1/6 text-left">Education</h3>
      <div class="flex text-left w-5/6 flex-col">
        <div v-for="edu in data.education" :key="edu.degree">
          <p class="font-bold">{{ edu.degree }}</p>
          <p>{{ edu.institution }} ({{ edu.period }})</p>
        </div>
      </div>
    </section>

    <section class="mb-8 flex justify-between">
      <h3 class="text-xl font-semibold w-1/6 text-left">Certifications</h3>
      <div class="flex text-left w-5/6 flex-col">
        <p v-for="certif in data.certification" :key="certif">{{ certif }}</p>
      </div>
    </section>

    <section class="flex justify-between">
      <h3 class="text-xl font-semibold w-1/6 text-left">Languages</h3>
      <div class="flex text-left w-5/6 flex-col">
        <p v-for="lang in data.languages" :key="lang">{{ lang }}</p>
      </div>
    </section>
  </div>
</template>
