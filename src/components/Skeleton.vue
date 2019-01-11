<template>
  <div class="vue-skeleton" :class="{'vue-skeleton-active': active}" v-show="loading">
    <div v-show="avatar" class="vue-skeleton-header">
      <span class="vue-skeleton-avatar"></span>
    </div>
    <div class="vue-skeleton-content">
      <h3 v-show="title" class="vue-skeleton-title"></h3>
      <div v-show="paragraph" class="vue-skeleton-paragraph">
        <div class="vue-skeleton-item" v-for="i in rows" :key="i"></div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "skeleton",
  props: {
    loading: {
      type: Boolean,
      required: true,
      default: false
    },
    rows: {
      type: Number,
      default: 3
    },
    active: {
      type: Boolean,
      default: true
    },
    paragraph: {
      type: Boolean,
      default: true
    },
    title: {
      type: Boolean,
      default: true
    },
    avatar: {
      type: Boolean,
      default: true
    }
  },
};
</script>

<style scoped>
h3 {
  margin: 0;
}
.vue-skeleton {
  display: flex;
  flex-direction: row;
}
.vue-skeleton-header {
  padding-right: 15px;
}
.vue-skeleton-content {
  flex: 1;
}
.vue-skeleton-avatar {
  display: inline-block;
  height: 40px;
  width: 40px;
  line-height: 40px;
  border-radius: 50%;
}


.vue-skeleton-title {
  height: 16px;
  margin-bottom: 16px;
  width: 50%;
}

.vue-skeleton-item {
  height: 16px;
  margin-top: 16px;
  list-style: none;
}
.vue-skeleton-avatar,
.vue-skeleton-item {
  background: #f2f2f2;
}
.vue-skeleton-active .vue-skeleton-title,
.vue-skeleton-active .vue-skeleton-avatar,
.vue-skeleton-active .vue-skeleton-item {
  background: linear-gradient(90deg, #f2f2f2 25%, #e6e6e6 37%, #f2f2f2 63%);
  animation: skeleton-loading 1.4s ease infinite;
  background-size: 400% 100%;
}
.vue-skeleton-item:first-child {
  margin: 0;
}
.vue-skeleton-item:last-child {
  width: 61%;
}

@-webkit-keyframes skeleton-loading {
  0%,
  100% {
    background-position: 0 50%;
  }
  50% {
    background-position: 100% 50%;
  }
}
@keyframes skeleton-loading {
  0%,
  100% {
    background-position: 0 50%;
  }
  50% {
    background-position: 100% 50%;
  }
}
</style>