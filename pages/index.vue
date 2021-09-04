<template>
    <div>
        <div v-for="(home, index) in homes" :key="home.objectID" style="float: left; margin: 10px;">
          <nuxt-link :to="`/home/${home.objectID}`" prefetch>
            <Home-Card :home="home" :index="index" />
          </nuxt-link>
        </div>
    </div>
</template>
<script>
import homes from '~/data/homes';

export default {
  head() {
    return {
      title: 'HomePage',
      meta: [{
        name: 'description',
        content: 'This is a homepage!',
        hid: 'description'
      }]
    }
  },
  data() {
    return {
      homes: homes.slice(0, 3)
    }
  }    
}
</script>