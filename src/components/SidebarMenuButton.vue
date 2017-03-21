<template>
  <li :class="['pageLink', active && 'active']">
    <router-link :to="to">
      <i v-if="icon" :class="['fa', icon, 'text-yellow']"></i>
      <span class="page"> {{label}}</span>
      </slot>
    </router-link>
  </li>
</template>
<script>
import {mapState} from 'vuex'

export default {
  name: 'SidebarMenuButton',
  props: {
    to: {
      type: String
    },
    label: {
      type: String
    },
    icon: {
      type: String
    }
  },
  data () {
    return {
      active: false
    }
  },
  watch: {
    route: {
      handler: function (route) {
        console.log(route)
      },
      immediate: true
    }
  },
  compute: {
    ...mapState(['route'])
  }
}
</script>
