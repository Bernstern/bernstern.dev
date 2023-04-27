<template>
  <v-main>
    <v-container fluid class="align-center frame">
      <v-row>
        <v-col cols="12" sm="9">
          <v-sheet rounded="lg" class="file-view">
            <v-container class="mgreybg">
              <v-row class="pa-2 align-center mgreybg">
                <v-col class="text-start">
                  <v-row class="align-center mgrey">
                    <v-avatar
                      size="30"
                      image="https://avatars.githubusercontent.com/u/14945414?v=4"
                    />
                    <v-row class="align-baseline pl-5">
                      <a href="https://github.com/Bernstern">
                        <h4>bernstern</h4></a
                      >
                      <p class="pl-1 d-none d-sm-flex">
                        Removed left-pad from dependencies
                      </p>
                    </v-row>
                  </v-row>
                </v-col>
                <v-col cols="5">
                  <v-row class="justify-end align-baseline">
                    <v-icon class="lgreen d-none d-sm-flex">mdi-check</v-icon>
                    <p class="dgrey pr-4 d-none d-sm-flex">
                      3133337 on Jun 15, 2022
                    </p>
                    <v-icon class="pr-2">mdi-history</v-icon>
                    <h4 class="">21</h4>
                    <p class="dgrey pl-1">commits</p>
                  </v-row>
                </v-col>
              </v-row>
            </v-container>
            <v-divider />
            <template v-for="n in files" :key="n">
              <v-row class="pl-4 pa-2 pb-2 align-center">
                <v-col class="text-start lgrey" cols="8" sm="4">
                  <v-row class="align-center pl-4">
                    <v-icon class="pr-2">{{ n.icon }}</v-icon>
                    <!-- If there is a link create an a tag otherwise just display the name -->
                    <template v-if="n.link">
                      <a :href="n.link">
                        {{ n.name }}
                      </a>
                    </template>
                    <template v-else>
                      {{ n.name }}
                    </template>
                  </v-row>
                </v-col>
                <v-col class="text-start dgrey d-none d-sm-flex" cols="6">
                  {{ n.commit }}
                </v-col>
                <v-col class="text-end dgrey pr-8">{{ n.last_modified }}</v-col>
              </v-row>
              <v-divider />
            </template>
          </v-sheet>
          <div style="height: 3vh"></div>
          <v-sheet rounded="lg" class="file-view">
            <v-container class="lgrey">
              <v-row class="pa-2 align-center">
                <v-icon class="pr-2 pl-2">mdi-file-document-outline</v-icon>
                <p class="pl-1 d-none d-sm-flex">README.md</p>
              </v-row>
            </v-container>
            <v-divider />
            <v-container class="lgrey pl-3">
              <h1>bernstern.dev</h1>
              <v-divider />
              <div class="pt-2">
                <template v-for="n in badges" :key="n">
                  <img :src="n" class="pl-1" />
                </template>
              </div>
              <template v-for="section in readme" :key="section">
                <div class="pt-3">
                  <h2>{{ section.title }}</h2>
                </div>
                <v-divider />
                <div class="pt-3">
                  <p>{{ section.content }}</p>
                </div>
              </template>
            </v-container>
          </v-sheet>
        </v-col>
        <v-col cols="12" sm="3">
          <v-sheet rounded="lg" color="background">
            <v-col class="lgrey">
              <v-row class="ma-2">
                <h3>About</h3>
                <v-spacer />
                <v-icon>mdi-cog-outline</v-icon>
              </v-row>
              <v-row class="ma-2">
                I solve complex problems with simple solutions and a little bit
                of humor.
              </v-row>
              <v-row class="ma-2 my-3">
                <v-icon>mdi-link-variant</v-icon>
                <a class="ml-2" href="https://www.linkedin.com/in/bernstern/"
                  >LinkedIn</a
                >
              </v-row>
              <v-row class="ma-2 my-3">
                <v-icon>mdi-link-variant</v-icon>
                <a class="ml-2" href="https://github.com/Bernstern">Github</a>
              </v-row>
              <v-row class="ma-2 my-3">
                <v-icon>mdi-link-variant</v-icon>
                <a class="ml-2" href="mailto:root@bernstern.dev">Email Me</a>
              </v-row>
              <v-row class="ma-2">
                <v-chip v-for="tag in tags" :key="tag" class="tag-chip ma-1">
                  {{ tag }}
                </v-chip>
              </v-row>
              <v-divider class="my-3" />
              <v-row class="ma-2">
                <h3>Contributors</h3>
              </v-row>
              <v-row
                v-for="contributor in contributors"
                :key="contributor"
                class="ma-1"
              >
                <v-col class="ma-2">
                  <v-row align="center" justify="center">
                    <v-avatar size="40" :image="contributor.image" />
                    <v-col class="ml-2">
                      <v-row>
                        <a :href="contributor.profile">
                          <h4>
                            {{ contributor.username }}
                          </h4>
                        </a>
                        <h4 class="pl-2 dgrey">{{ contributor.name }}</h4>
                      </v-row>
                    </v-col>
                  </v-row>
                </v-col>
              </v-row>
            </v-col>
          </v-sheet>
        </v-col>
      </v-row>
    </v-container>
  </v-main>
</template>

<style scoped>
.tag-chip {
  color: #316dca;
}

* {
  text-overflow: ellipsis;
}

a,
a:link,
a:focus,
a:active {
  text-decoration: none;
  color: inherit;
  background-color: transparent;
}

a:hover {
  text-decoration: underline;
}

.file-view {
  border: 2px solid #454c56;
}
.lgreen {
  color: #57ab5a;
}
.lgrey {
  color: #9cbbc8;
}
.dgrey {
  color: #758390;
}
.mgrey {
  background-color: #2d333b;
  color: #acbac7;
}

.mgreybg {
  background-color: #2d333b;
}

.frame {
  width: 90%;
}
</style>

<script>
export default {
  data() {
    return {
      tags: [
        "python",
        "rust",
        "c++",
        "ble",
        "pam",
        "go",
        "iam",
        "windows authentication",
        "devops",
        "aws",
        "azure",
        "bash/fish",
        "powershell",
        "agile",
      ],
      contributors: [
        {
          username: "cspensky",
          image: "https://avatars.githubusercontent.com/u/2789577?v=4",
          profile: "https://www.cspensky.info/",
          name: "Chad Spensky",
        },
        {
          username: "giovannivigna",
          image: "https://avatars.githubusercontent.com/u/9272002?v=4",
          profile: "https://sites.cs.ucsb.edu/~vigna/",
          name: "Giovanni Vigna",
        },
        {
          username: "mepix",
          image: "https://avatars.githubusercontent.com/u/13284555?v=4",
          profile: "https://merrickcampbell.com/",
          name: "Merrick Campbell",
        },
      ],
      readme: [
        {
          title: "Welcome!",
          content:
            "My name is Bernie Conrad (@bernstern) and this is my portfolio site. I am in the process of adding more features to it but feel free to take a look around during development.\nWhile most of my background is not working with web development, it's always fun to try a new challenge. I started programming in 4th grade taking summer python and html classes, immediately I was hooked on the ability to make just about anything I could think of with code. Now I am working on ridding the world of passwords, keys, and smart cards with Allthenticate, a cybersecurity startup out of Santa Barbara, CA. In my role I lead the development for Allthenticate's core products, our passwordless computer authentication and smart door readers as well as the companies DevOps and cloud infrastructure.",
        },
        {
          title: "Work In Progress",
          content:
            "Right now, my main focus outside of work is developing a Flutter App to facilitate a draft for a LAN party I am hosting in May. In my free time I have been learning Rust and Go, reading up on how to manage technical teams, and constantly trying to improve my Python skills. Shortly I am going to start preparing to recertify with AWS as my cloud practitioner certification is about to expire.",
        },
        {
          title: "Fun Facts",
          content:
            "Right now I am planning a trip to Europe for the fall of 2023 to visit France and Germany, if you have any recommendations for places to visit or food to eat, please let me know!",
        },
      ],
      badges: [
        "https://img.shields.io/badge/deployment-passing-green?style=for-the-badge&logo=appveyor",
        "https://img.shields.io/badge/issues-0_open-green?style=for-the-badge&logo=appveyor",
        "https://img.shields.io/badge/passing_tests-0-red?style=for-the-badge&logo=appveyor",
        // "https://github-readme-stats.vercel.app/api?username=bernstern&theme=blue-green"
      ],
      files: [
        {
          name: "README.md",
          icon: "mdi-file-document-outline",
          commit: "Updated README.md",
          last_modified: "1 Week Ago",
        },
        {
          name: "Resume.pdf",
          icon: "mdi-file-document-outline",
          commit: "Added resume, pretty sure there are no typos...",
          last_modified: "2 Weeks Ago",
          link: "https://github.com/Bernstern/bernstern.dev/blob/main/content/resume.pdf",
        },
        {
          name: "Passwordless",
          icon: "mdi-application-braces-outline",
          commit:
            "Lead the development of single device authentication on Linux, MacOS and Windows using Rust, C++ and Python @ Allthenticate",
          last_modified: "Today",
          link: "https://allthenticate.net/authentication",
        },
        {
          name: "Smart Door Readers",
          icon: "mdi-application-braces-outline",
          commit:
            "Developed the firmware for Allthenticate's smart door readers with authenitcation over BLE @ Allthenticate",
          last_modified: "Today",
          link: "https://allthenticate.net/access-control",
        },
        {
          name: "ABle",
          icon: "mdi-package-variant",
          commit:
            "Created a high performance open-source cross-platform Bluetooth Low Energy framework at Allthenticate",
          last_modified: "Today",
          link: "https://pypi.org/project/able/",
        },
        {
          name: "Gitlab Runner",
          icon: "mdi-directions-fork",
          commit:
            "Maintained a private fork of Gitlab Runner for validation testing of Allthenticate's products",
          last_modified: "1 Year Ago",
        },
        {
          name: "Bluez",
          icon: "mdi-directions-fork",
          commit:
            "Maintained a private fork of Bluez with added functionality focused on notifiying specific clients",
          last_modified: "1 Year Ago",
        },
        {
          name: "CVE 2021-43400",
          icon: "mdi-bug-check-outline",
          commit:
            "Found and fixed a use after free of a function pointer in Bluez, the Linux Bluetooth driver",
          last_modified: "1 year ago",
          link: "https://nvd.nist.gov/vuln/detail/CVE-2021-43400",
        },
        {
          name: "TheCivDraft",
          icon: "mdi-application-braces-outline",
          commit:
            "Created a Flutter app to manage a full reverse snake draft for Civ 6 for LAN parties",
          last_modified: "Last Year",
          link: "https://github.com/Bernstern/TheCivDraft",
        },
        {
          name: "Bowlmania Bot",
          icon: "mdi-application-braces-outline",
          commit:
            "Trained a Transformer + Naive Bayes Classifier to predict the winners of the 2022 College Bowl Games off of the last 10 years of data, almost won...",
          last_modified: "2 Months Ago",
          link: "https://github.com/Bernstern/Bowlmania22",
        },
        {
          name: "MagicRSVP",
          icon: "mdi-application-braces-outline",
          commit:
            "Created an open-source Python tool to RSVP dining reservations using Selenium and Cookie hijacking/borrowing",
          last_modified: "1 Month Ago",
          link: "https://github.com/Bernstern/MagicRSVP",
        },
        {
          name: "Research ChatBot",
          icon: "mdi-application-braces-outline",
          commit:
            "Made a nextjs chatbot to help with a UCSB research project that used MongoDB",
          last_modified: "2 years ago",
          link: "https://github.com/Bernstern/pabs_research",
        },
        {
          name: "AWS Cloud Practitioner",
          icon: "mdi-certificate",
          commit: "Became an AWS Certified Cloud Practitioner",
          last_modified: "3 Years Ago",
          link: "https://www.credly.com/badges/949ac0c9-ccd9-47e3-b5fd-f6f4ddae2405/linked_in_profile",
        },
      ],
    };
  },
};
</script>
