<template lang="html">
  <div class="page-wrap">
    <aside
      class="w-full md:w-72 md:fixed md:h-screen bg-white md:overflow-y-auto z-20 relative"
    >
      <!-- Branding -->
      <header class="flex justify-center flex-col items-center">
        <!-- Logomark -->
        <nuxt-link to="/">
          <app-logomark active class="mt-8 mb-0 w-12 h-12" />
        </nuxt-link>
        <!-- Logotype -->
        <nuxt-link
          to="/"
          class="bottom-0 block w-full flex justify-center my-10"
        >
          <app-logotype class="text-brand-900 fill-current w-32" />
        </nuxt-link>
      </header>

      <!-- Diagram -->
      <sidebar-collapse title="Diagram" class="">
        <a ref="dl">
          <header
            class="text-xs tracking-wider mb-0 mt-1 text-gray-950 group-hover:text-gray-950 transition ease-in-out duration-200 antialiased flex justify-between items-center"
          >
            <span class="uppercase cursor-pointer">Download</span>
            <span class="text-xs lowercase text-gray-600">
              <span class="text-brand-800 font-bold cursor-pointer">png</span>
            </span>
          </header>
        </a>
      </sidebar-collapse>

      <!-- Assumptions -->
      <sidebar-collapse title="Assumptions">
        <ol class="list-decimal list-outside pl-3 text-xs">
          <li class="pb-01">Light travels in a straight line.</li>
          <li>The Earth is a sphere with a radius of 6371 km.</li>
        </ol>
      </sidebar-collapse>
      <!-- Resources -->
      <sidebar-collapse title="Resources">
        <ul class="text-xs">
          <li>
            <a
              href="https://github.com/shifttheory/flat-earth-books/tree/master/src"
              title="Flat Earth Books"
              target="_blank"
              >Books</a
            >
          </li>
        </ul>
      </sidebar-collapse>
      <app-social />
    </aside>
    <!-- md:ml-73 md:w-sidebar -->
    <!-- pinchSpeed: 1.1, -->
    <!-- transformOrigin: {x: 0.5, y: 0.5},
          smoothScroll: true, -->
    <div
      class="diagram hidden md:flex w-full h-full absolute right-0 md:w-sidebar overflow-y-scroll md:overflow-y-hidden scrolling-touch"
    ></div>
  </div>
</template>

<script>
import AppLogomark from '~/components/AppLogomark'
import AppLogotype from '~/components/AppLogotype'
import AppSocial from '~/components/AppSocial'
import SidebarCollapse from '~/components/SidebarCollapse'

export default {
  components: {
    AppLogomark,
    AppLogotype,
    AppSocial,
    SidebarCollapse
  },
  data() {
    return {
      title: 'Shift Theory',
      description: 'The shift has begun',
      poster: 'https://shifttheory.com/images/shifttheory-meta-poster.png'
    }
  },
  methods: {},
  head() {
    return {
      title: this.title,
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: this.description
        },
        // Open Graph / Facebook
        {
          hid: 'og:url',
          property: 'og:url',
          content: this.$nuxt.$route.path
        },
        {
          hid: 'og:title',
          property: 'og:title',
          content: 'Shift Theory | ' + this.title
        },
        {
          hid: 'og:description',
          property: 'og:description',
          content: this.description
        },
        {
          hid: 'og:image',
          property: 'og:image',
          content: this.poster
        },
        // Twitter
        {
          hid: 'twitter:url',
          property: 'twitter:url',
          content: this.$nuxt.$route.path
        },
        {
          hid: 'twitter:title',
          property: 'twitter:title',
          content: 'Shift Theory | ' + this.title
        },
        {
          hid: 'twitter:description',
          property: 'twitter:description',
          content: this.description
        },
        {
          hid: 'twitter:image',
          property: 'twitter:image',
          content: this.poster
        }
      ]
    }
  }
}
</script>

<style lang="postcss">
aside {
  box-shadow: 1px 0 2px 0 rgba(31, 33, 38, 0.08);
}

#diagram-footer {
  display: none;
}
</style>
