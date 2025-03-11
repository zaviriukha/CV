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
    git: "https://github.com/zaviriukha",
    email: "v.zaviriukha@gmail.com",
    phone: "(097) 170-70-30",
  },
  summary:
    "Over 6 years of professional experience in Front-end development. For over 2 years have been doing front-end development based on the Vue.js framework. Prior to that, worked on the development of sites for CMS ModX Revolution for 4 years.",
  about: [
    {
      me: "Extensive experience in Front-end development using Shopware 6, Pimcore CMS, and Vue.js. Skilled in e-commerce development in Germany and Ukraine.",
      involved: [
        {
          title: "Direct involvement in client communications, including:",
          details: [
            "Presenting products to clients",
            "Collecting client product suggestions",
            "Training clients to use developed or modified functionality",
          ],
        },
      ],
      partners:
        "Regular collaboration with partner companies to develop new features, suggest improvements, and refine their systems.",
      presentations:
        "Researched and presented new technologies to the company, including the implementation of Shopware 6 and Vue Storefront.",
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
            "Analysis of the possible use of Vue Storefront in new projects",
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
  <div
    class="max-w-4xl mx-auto lg:p-8 p-0 bg-white lg:shadow-lg lg:rounded-lg text-black overflow-hidden"
  >
    <header
      class="md:mb-8 mb-5 text-left border-b-2 border-black justify-between flex md:pb-5 pb-4"
    >
      <div>
        <h1 class="md:text-5xl text-4xl font-bold">{{ data.name }}</h1>
        <h2 class="md:text-2xl text-xl">{{ data.position }}</h2>
      </div>
      <div class="contact md:flex hidden">
        <div class="flex flex-col items-start">
          <p>
            <span class="font-bold">Git</span>:
            <a href="{{ data.contact.git }}">{{ data.contact.git }}</a>
          </p>
          <p>
            <span class="font-bold">Email</span>:
            <a :href="'mailto:' + data.contact.email" class="text-black">{{
              data.contact.email
            }}</a>
          </p>
          <p><span class="font-bold">Phone</span>: {{ data.contact.phone }}</p>
        </div>
      </div>
    </header>

    <section class="mb-8 flex justify-between md:flex-row flex-col">
      <div class="lg:w-1/6 md:w-2/6 text-left md:mb-0 mb-2.5">
        <h3 class="text-xl font-semibold">Summary</h3>
      </div>
      <div
        v-for="me in data.about"
        :key="me.me"
        class="flex flex-col text-left md:w-5/6 w-full"
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

    <section class="mb-8 flex justify-between md:flex-row flex-col">
      <div class="lg:w-1/6 md:w-2/6 text-left md:mb-0 mb-2.5">
        <h3 class="text-xl font-semibold">Professional Skills</h3>
      </div>
      <div class="flex text-left md:w-5/6 w-full">
        <ul class="list-disc pl-5">
          <li v-for="skill in data.skills" :key="skill">{{ skill }}</li>
        </ul>
      </div>
    </section>

    <section class="mb-8 flex justify-between md:flex-row flex-col">
      <div class="lg:w-1/6 md:w-2/6 text-left md:mb-0 mb-2.5">
        <h3 class="text-xl font-semibold">Work Experience</h3>
      </div>
      <div class="flex text-left md:w-5/6 w-full flex-col">
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

    <section class="mb-8 flex justify-between md:flex-row flex-col">
      <div class="lg:w-1/6 md:w-2/6 text-left md:mb-0 mb-2.5">
        <h3 class="text-xl font-semibold">Education</h3>
      </div>
      <div class="flex text-left md:w-5/6 w-full flex-col">
        <div v-for="edu in data.education" :key="edu.degree">
          <p class="font-bold">{{ edu.degree }}</p>
          <p>{{ edu.institution }} ({{ edu.period }})</p>
        </div>
      </div>
    </section>

    <section class="mb-8 flex justify-between md:flex-row flex-col">
      <div class="lg:w-1/6 md:w-2/6 text-left md:mb-0 mb-2.5">
        <h3 class="text-xl font-semibold">Certifications</h3>
      </div>
      <div class="flex text-left md:w-5/6 w-full flex-col">
        <p v-for="certif in data.certification" :key="certif">{{ certif }}</p>
      </div>
    </section>

    <section class="mb-8 flex justify-between md:flex-row flex-col">
      <div class="lg:w-1/6 md:w-2/6 text-left md:mb-0 mb-2.5">
        <h3 class="text-xl font-semibold">Languages</h3>
      </div>
      <div class="flex text-left md:w-5/6 w-full flex-col">
        <p v-for="lang in data.languages" :key="lang">{{ lang }}</p>
      </div>
    </section>

    <section
      class="contact justify-between md:hidden flex md:flex-row flex-col"
    >
      <div class="lg:w-1/6 md:2/6 text-left md:mb-0 mb-2.5">
        <h3 class="text-xl font-semibold">Contact</h3>
      </div>
      <div class="flex flex-col items-start md:w-5/6 w-full">
        <p>
          <span class="font-bold">Email</span>:
          <a :href="'mailto:' + data.contact.email" class="text-black">{{
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
  </div>
</template>
