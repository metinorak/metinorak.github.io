<!-- About Page -->
<template>
  <v-container text-xs-center class="about-page width-limit-800">
    <!-- Basic Info -->
    <basic-info-bar-row id="row"></basic-info-bar-row>
    <basic-info-bar-col id="col"></basic-info-bar-col>

    <!-- Divider  -->
    <v-container class="divider-container" pa-0 pt-3 pb-3>
      <v-divider></v-divider>
    </v-container>

    <!-- Bio  -->
    <v-card flat v-for="item in bio.content" :key="item" class="transparent">
      <v-card-text class="no-space">{{ item }}</v-card-text>
    </v-card>

    <!-- Buttons  -->
    <v-tooltip top>
      <v-btn icon flat :href="this.github" target="_blank" slot="activator" pa-0 ma-0>
          <img src="../assets/GitHub-Mark-32px.png" size="16px">
      </v-btn>
      <span>View GitHub Profile</span>
    </v-tooltip>
    <v-tooltip top>
      <v-btn icon flat :href="this.linkedin" target="_blank" slot="activator" pa-0 ma-0>
        <img src="../assets/In-Black-34px-TM.png" size="16px">
      </v-btn>
      <span>View LinkedIn Profile</span>
    </v-tooltip>
  </v-container>
</template>

<script>
import InfoText from '../components/text/InfoText.vue';
import BasicInfoBarCol from '../components/bars/BasicInfoBarCol.vue';
import BasicInfoBarRow from '../components/bars/BasicInfoBarRow.vue';
import { profile } from '../data/basic-info.js';

export default {
  name: 'about',
  data() {
    return {
      github: 'https://github.com/metinorak', // TODO: Insert github lunk
      linkedin: 'https://www.linkedin.com/in/metinorak', // TODO: insert linkedin link
      bio: profile.bio
    };
  },
  components: {
    InfoText,
    BasicInfoBarRow,
    BasicInfoBarCol,
  },
};
</script>
<style>
  /* Media Queries */
  @media (min-width: 651px) {
    #row { display: block }
    #col { display: none }
  }
  @media (min-width: 0px) and (max-width: 650px) {
    #row { display: none }
    #col { display: block }
  }

  .about-page {
    padding-top: 0;
    padding-bottom: 0;
  }

  .no-space {
    padding-top: 0px;
    padding-bottom: 16px;
  }
</style>
