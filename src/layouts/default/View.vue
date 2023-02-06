<template>
  <v-main>
    <v-container>
      <v-row>
        <v-col>
          <v-sheet min-height="30vh" rounded="lg" class="file-view">
            <!--  -->
          </v-sheet>
        </v-col>
        <v-col cols="3">
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
                    <v-avatar size="40">
                      <img :src="contributor.image" />
                    </v-avatar>
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
  border: 1px solid #75838e;
}
.lgrey {
  color: #9cbbc8;
}
.dgrey {
  color: #758390;
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
    };
  },
};
</script>
