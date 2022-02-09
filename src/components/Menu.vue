<template>
  <div class="hashtag-grid">
<!--    <div v-for="(hashtag, key) in hashtags" :key="key">-->
      <div
          v-for="(hashtag, key) in hashtags" :key="key"
          :class="['hashtag-grid__item', { '--active': activeBlock === key, '--notActive': activeBlock !== key && activeBlock !== -1 }]"
          @click="toggleActive(key)"
      >{{ hashtag }}
      </div>
<!--    </div>-->
  </div>
</template>

<script lang="ts">
import {Vue} from 'vue-class-component'

export default class Menu extends Vue {
  hashtags = ['#1', '#2', '#3', '#4']
  activeBlock = 1

  toggleActive(key: number): void {
    if (key === this.activeBlock) this.activeBlock = -1
    else this.activeBlock = key
  }
}
</script>

<style scoped lang="scss">
.hashtag-grid {
  height: 100%;
  display: grid;
  grid-template-columns: repeat(2, 1fr);

  position: relative;

  background-color: #c7c7c7;

  &__item {
    margin: 5px;
    display: flex;
    justify-content: center;
    align-items: center;
    width: 240px;
    height: 240px;

    background-color: white;
    border-radius: 10px;
    transition: all 1s linear;

    &.--active {
      margin: 0;
      width: 500px;
      height: 500px;
    }

    &.--notActive {
      margin: 0;
      width: 0;
      height: 0;
    }
  }
}

@keyframes open {
  to {
    //left: 100%;
    //transform: translateX(-100%);
    //background: blue;
    //top: 0;
    //bottom: 0;
    //left: 0;
    //right: 0;
  }
}
</style>
