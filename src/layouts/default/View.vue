<template>
  <v-main>
    <v-container>
      <v-row>
        <v-col cols="12" sm="9">
          <v-sheet rounded="lg" class="file-view">
            <v-container class="mgreybg">
              <v-row class="pa-2 align-center mgreybg">
                <v-col class="text-start" cols="4">
                  <v-row class="align-center mgrey">
                    <v-avatar
                      size="30"
                      image="https://avatars.githubusercontent.com/u/14945414?v=4"
                    />
                    <v-row class="align-baseline pl-2">
                      <h4 class="pl-2">bernstern</h4>
                      <p class="pl-1">Fixed bugs with deployment</p>
                    </v-row>
                  </v-row>
                </v-col>
                <v-col cols="4" />
                <v-col cols="4">
                  <v-row class="justify-end align-baseline">
                    <v-icon class="lgreen">mdi-check</v-icon>
                    <p class="dgrey pr-4">3133337 on Jun 15, 2022</p>
                    <v-icon class="pr-2">mdi-history</v-icon>
                    <h4>21</h4>
                    <p class="dgrey pl-1">commits</p>
                  </v-row>
                </v-col>
              </v-row>
            </v-container>
            <v-divider />
            <template v-for="n in files" :key="n">
              <v-row class="pl-4 pa-2 pb-2 align-center">
                <v-col class="text-start lgrey" cols="4">
                  <v-row>
                    <v-icon class="pr-2 pl-6">{{ n.icon }}</v-icon>
                    <v-col class="pl-6">
                      <v-row>
                        {{ n.name }}
                      </v-row>
                    </v-col>
                  </v-row>
                </v-col>
                <v-col class="text-start dgrey" cols="4">{{ n.commit }}</v-col>
                <v-col class="text-end dgrey pr-8" cols="4">{{
                  n.last_modified
                }}</v-col>
              </v-row>
              <v-divider />
            </template>
          </v-sheet>
          <!-- <v-sheet rounded="lg m" class="fileview">
            <v-banner
              lines="two"
              icon="mdi-format-list-bulleted"
              color="#2d333b"
            >
              Test
            </v-banner>
          </v-sheet> -->
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
                        <h4>{{ contributor.username }}</h4>
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
        "windows authentication",
        "devops",
        "aws",
      ],
      contributors: [
        {
          username: "cspensky",
          image: "https://avatars.githubusercontent.com/u/2789577?v=4",
          name: "Chad Spensky",
        },
        {
          username: "mepix",
          image: "https://avatars.githubusercontent.com/u/13284555?v=4",
          name: "Merrick Campbell",
        },
      ],
      readme: {
        title: "Career",
        main_text: "Lorem ipsum dolor sit amet, consectetur adipiscing elit. ",
      },
      files: [
        {
          name: "resume.pdf",
          icon: "mdi-file-document-outline",
          commit: "Added resume, LGTM!",
          last_modified: "1 Month Ago",
          link: "TODO",
        },
        {
          name: "resume.pdf",
          icon: "mdi-file-document-outline",
          commit: "Added resume, LGTM!",
          last_modified: "1 Month Ago",
          link: "TODO",
        },
        {
          name: "resume.pdf",
          icon: "mdi-file-document-outline",
          commit: "Added resume, LGTM!",
          last_modified: "1 Month Ago",
          link: "TODO",
        },
        {
          name: "resume.pdf",
          icon: "mdi-file-document-outline",
          commit: "Added resume, LGTM!",
          last_modified: "1 Month Ago",
          link: "TODO",
        },
        {
          name: "resume.pdf",
          icon: "mdi-file-document-outline",
          commit: "Added resume, LGTM!",
          last_modified: "1 Month Ago",
          link: "TODO",
        },
        {
          name: "resume.pdf",
          icon: "mdi-file-document-outline",
          commit: "Added resume, LGTM!",
          last_modified: "1 Month Ago",
          link: "TODO",
        },
        {
          name: "resume.pdf",
          icon: "mdi-file-document-outline",
          commit: "Added resume, LGTM!",
          last_modified: "1 Month Ago",
          link: "TODO",
        },
        {
          name: "resume.pdf",
          icon: "mdi-file-document-outline",
          commit: "Added resume, LGTM!",
          last_modified: "1 Month Ago",
          link: "TODO",
        },
        {
          name: "resume.pdf",
          icon: "mdi-file-document-outline",
          commit: "Added resume, LGTM!",
          last_modified: "1 Month Ago",
          link: "TODO",
        },
      ],
    };
  },
};
</script>
