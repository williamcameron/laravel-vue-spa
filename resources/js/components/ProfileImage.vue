<template>
  <div class="profile-image">
    <img :src="user.photo_url" class="rounded-circle profile-photo mr-1">
    <span>{{ user.name }}</span>
    </div>
</template>

<script>
export default {
    props: ['user']
}
</script>

<style>
    .profile-image {
        display: block;
        padding-left: 10px;
        margin-bottom: 5px;
        border-bottom: 1px lightblue solid;
    }
    img {
        height: 2em;
    }
    span {
        margin-left: 15px;
    }
</style>