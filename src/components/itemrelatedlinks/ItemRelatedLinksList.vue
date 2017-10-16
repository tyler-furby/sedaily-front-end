<template>
  <div>
      <item-related-link v-for="link in links" :link.sync="link"></item-related-link>
      <item-create-new-link></item-create-new-link>
  </div>

</template>
<script>

  import ItemRelatedLink from './ItemRelatedLink'
  import ItemCreateNewLink from './ItemCreateNewLink'

  export default {
    props: ['links'],
    components: {
      ItemRelatedLink,
      ItemCreateNewLink
    }
  }

</script>
