<template>
   <v-container>
     <v-row class="text-center">
      <v-col cols="12">
        <v-carousel hide-delimiters>
          <v-carousel-item
            v-for="(item,i) in items"
            :key="i"
            :src="item.src"
            cover
          ></v-carousel-item>
        </v-carousel>
      </v-col>

      <v-col class="mb-16 my-16">
        <h1 class="display-2 font-weight-bold mb-3">
          Category Game 
        </h1><br>      
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    message: String
  },
  data: () => ({
    ecosystem: [
      {
        text: 'vuetify-loader',
        href: 'https://github.com/vuetifyjs/vuetify-loader'
      },
      {
        text: 'github',
        href: 'https://github.com/vuetifyjs/vuetify'
      },
      {
        text: 'awesome-vuetify',
        href: 'https://github.com/vuetifyjs/awesome-vuetify'
      }
    ],
    importantLinks: [
      {
        text: 'Documentation',
        href: 'https://vuetifyjs.com'
      },
      {
        text: 'Chat',
        href: 'https://community.vuetifyjs.com'
      },
      {
        text: 'Made with Vuetify',
        href: 'https://madewithvuejs.com/vuetify'
      },
      {
        text: 'Twitter',
        href: 'https://twitter.com/vuetifyjs'
      },
      {
        text: 'Articles',
        href: 'https://medium.com/vuetify'
      }
    ],
    items: [
        { src: 'https://img.4gamers.com.tw/news-image/b5fef64a-57d8-49e0-b016-6ad5b1d9f805.jpg' },
        { src: 'https://www.riotgames.com/darkroom/1000/e69e5ec20508361cd841bc66730f4797:2651bc6bea7cd3f81703426410705268/110322-xbox-pass-1920x1080-article.png' },
        { src: 'https://mpics.mgronline.com/pics/Images/556000000095001.JPEG' },
        // เพิ่มรูปภาพเพิ่มเติมตามต้องการ
      ],

    whatsNext: [
      {
        text: 'Explore components',
        href: 'https://vuetifyjs.com/components/api-explorer'
      },
      {
        text: 'Select a layout',
        href: 'https://vuetifyjs.com/getting-started/pre-made-layouts'
      },
      {
        text: 'Frequently Asked Questions',
        href: 'https://vuetifyjs.com/getting-started/frequently-asked-questions'
      }
    ]
  }),
  created() {
    this.$EventBus.$on('getUsername', this.getUsername)
    this.getUsername()
  },
  methods: {
    getUsername () {
      if (localStorage.getItem('username') !== null) {
        this.username = localStorage.getItem('username')
      } else {
        this.username = 'Vuetify'
      }
    }
  },
  gotoHomepage() {
      this.$router.push("/Homepage");
    },
}
</script>