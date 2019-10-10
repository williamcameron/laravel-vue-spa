<template>
  <card :title="$t('home')">
    {{ $t('you_are_logged_in') }}
    <ProfileImage v-for="user of users" :key="user.name" :user="user" />
  </card>
</template>

<script>
import ProfileImage from "../components/ProfileImage.vue";

export default {
  middleware: 'auth',

  data: () => ({
    users: []
    
  }),
  metaInfo () {
    return { title: this.$t('home') }
  }, 
  components: {
    ProfileImage
  }, 
  async created () {
    const users = await fetch('/api/users');
    this.users = await users.json();
          console.log(this.users);
    
  }
}
</script>
