<template>
  <div>
    <el-button @click="openDialog">Open</el-button>
    <FeedbackDialog ref="feedback" />
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import FeedbackDialog from '~/components/FeedbackDialog.vue'

export default Vue.extend({
  name: 'IndexPage',

  components: {
    FeedbackDialog,
  },

  methods: {
    openDialog() {
      const feedbackRef: any = this.$refs.feedback
      //TODO: need to send following info when dialog opens.
      let feedback = {
        email: 'feedback@gmail.com',
        auth_token: 'authtoken',
        sdk_version: 'current sdk',
        app_version: 'latest',
        user_agent: 'Mac Pro',
        device_id: 'test',
        feedback_url: 'http://localhost/api/v1/common/feedback',
        media_url: 'http://localhost/api/v1/media',
      }
      feedbackRef.openDialog(feedback)
    },
  },
})
</script>
