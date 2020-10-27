<template>
  <section>
    <v-row no-gutters>
      <v-carousel
        cycleq
        height="100vh"
        :show-arrows="false"
        hide-delimiters
        touchless
      >
        <v-carousel-item
          v-for="(item, i) in items"
          :key="i"
          :src="item.src"
          transition="fade-transition"
          reverse-transition="fade-transition"
        >
          <v-theme-provider dark class="z-index">
            <v-container fill-height>
              <v-row
                align="center"
                class="white--text mx-auto"
                justify="center"
              >
                <v-col class="white--text text-center" cols="12" tag="h1">
                  <span
                    :class="[
                      $vuetify.breakpoint.smAndDown ? 'display-3' : 'display-4',
                    ]"
                    class="font-weight-black"
                  >
                    DEVICE HOME
                  </span>

                  <br />

                  <span
                    :class="[
                      $vuetify.breakpoint.smAndDown ? 'display-1' : 'display-2',
                    ]"
                    class="font-weight-light"
                  >
                    <strong class="red--text font-weight-bold"
                      >今月限り！</strong
                    >売り建て販売イベント開催！
                  </span>
                </v-col>

                <v-btn
                  class="align-self-end"
                  fab
                  outlined
                  @click="$vuetify.goTo('#welcome')"
                >
                  <v-icon>mdi-chevron-double-down</v-icon>
                </v-btn>
              </v-row>
            </v-container>
          </v-theme-provider>
        </v-carousel-item>
      </v-carousel>
    </v-row>
  </section>
</template>

<script>
  export default {
    data: () => ({
      items: [
        {
          src: require('@/assets/top01.jpg'),
        },
        {
          src: 'https://www.luckydakara.com/sinchiku/images/IMG_0709.jpeg',
        },
        {
          src:
            'https://images.unsplash.com/photo-1596204976717-1a9ff47f74ef?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1350&q=80',
        },
        {
          src:
            'https://images.unsplash.com/photo-1601628828688-632f38a5a7d0?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1211&q=80',
        },
      ],
    }),
  }
</script>

<style>
  .z-index {
    position: relative;
    z-index: 5;
  }
</style>
