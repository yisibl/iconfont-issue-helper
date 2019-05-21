<template>
  <nav class="app-header">
    <div class="container">
      <a class="brand" target="_blank" href="https://www.iconfont.cn" rel="noopener noreferrer">
        <img
          class="logo"
          src="//gw.alicdn.com/tfs/TB1wyVMXRCw3KVjSZR0XXbcUpXa-106-19.svg"
          alt="iconfont's logo"
          height="24"
        >
        Issue Helper
      </a>

      <ul class="nav">
        <li
          v-for="(locale, key) in $root.$locales"
          :key="key"
          class="nav-item"
        >
          <a
            class="nav-link"
            :class="{ active: lang === key }"
            @click="$emit('change-lang', key)"
          >
            {{ locale._label }}
          </a>
        </li>
      </ul>
    </div>
  </nav>
</template>

<script>
export default {
  props: ['lang']
}
</script>

<style lang="stylus" scoped>
@import "../style/imports"

.app-header
  background #000
  border-bottom solid 1px #333

  &,
  .container,
  .brand,
  .nav
    h-box()
    box-center()

  .container
    max-width $page-width
    flex 100% 1 1
    justify-content space-between
    padding 24px
    box-sizing border-box

  .brand
    color $iconfont-ui-color-dark
    .logo
      margin-right 8px

  .nav
    margin 0

  .nav-item
    list-style none
  .nav-item + .nav-item
    margin-left 8px

  .nav-link
    cursor default
    &:not(.active)
      cursor pointer
      color $iconfont-ui-color-dark

</style>
