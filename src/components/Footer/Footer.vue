<template>
  <v-footer class="px-0 mt-10" color="transparent">
    <v-row no-gutters>
      <div>
        <v-btn
                v-for="icon in icons"
                :key="icon.icon"
                :href="icon.link"
                target="_blank"
                class="mr-1"
                :color=config.light.textColor
                icon
        >
          <v-icon size="24px">{{ icon.icon }}</v-icon>
        </v-btn>
      </div>
    </v-row>
  </v-footer>
</template>

<script>
import config from '../../config';

export default {
  name: 'Footer',

  data: () => ({
    config,
    icons: [
      {icon: 'mdi-facebook', link: 'https://www.facebook.com/vinicius.barth.1'},
      {icon: 'mdi-linkedin', link: 'https://www.linkedin.com/in/vinicius-barth-1728b4107/'},
      {icon: 'mdi-twitter', link: 'https://twitter.com/umcaraloko'},
      {icon: 'mdi-github', link: 'https://github.com/viniciusbarth'},

    ]
  }),
}
</script>

<style src="./Footer.scss" lang="scss"/>

