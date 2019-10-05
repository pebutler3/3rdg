<template>
  <div class="card__wrapper">
    <div
      class="card"
      v-for="(user, index) in users"
      :key="index"
      @click="toggleContactDetails($event), toggleArrow()">
      <div class="card__inner">
        <img class="card__avatar" :src="user.picture.thumbnail" />
        <ul class="card__list">
          <li class="card__list-item">{{ user.name.first }} {{ user.name.last }}</li>
          <li class="card__list-item">{{ user.location.city }}, {{ user.location.state }}</li>
        </ul>
        <i class="arrow"></i>
      </div>
      <ul class="card__contact">
        <li class="card__contact-item">Phone <span>{{ user.cell }}</span></li>
        <li class="card__contact-item">Email <span>{{ user.email }}</span></li>
      </ul>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'List',
    props: ['users'],
    methods: {
      toggleArrow() {
        const arrow = document.querySelector('.arrow');
        arrow.classList.toggle('arrow--up');
      },
      // $emit toggleContactDetails event up to parent
      toggleContactDetails(event) {
        this.$emit('toggleContactDetails', event);
      }
    }
  }
</script>

<style lang="scss" scoped>
  @import '@/assets/styles/_variables';
  @import 'List';
</style>
