<template>
  <section
    id="services"
    class="overflow-hidden"
  >
    <v-row
      class="accent"
      no-gutters
    >
      <!-- <v-col
        class="hidden-sm-and-down"
        md="6"
      >
        <v-img
          :src="require('@/assets/services.png')"
          height="100%"
        />
      </v-col> -->

      <v-col
        class="text-center pa-5"
        cols="12"
        
      >
        <v-row
          class="fill-height"
          align="center"
          justify="center"
        >
          <v-col cols="12">
            <base-bubble-2
              style="transform: translateX(55%)"
            />
            <base-heading class="info--text">
              なぜ夢の実現が可能なのか
            </base-heading>

            <base-text class="mb-5">
              私たちがお客様の理想を実現できる理由<br>
              4つのポイントがあります
            </base-text>
          </v-col>

          <v-col
            v-for="(service, i) in services"
            :key="i"
            class="text-center mb-3"
            md="3"
            cols="6"
          >
            <v-avatar
              class="elevation-6 mb-2"
              color="#69A1BB"
              size="64"
              tile
            >
              <v-icon
                dark
                size="52"
                v-text="service.icon"
              />
            </v-avatar>

            <base-text>
              <div
                class="mb-2"
                v-text="service.name"
              />
              <div v-html="service.blurb" />
            </base-text>
          </v-col>
        </v-row>
      </v-col>
    </v-row>
  </section>
</template>

<script>
  export default {
    name: 'Services',

    data: () => ({
      services: [
        {
          name: '完全自由設計',
          icon: 'mdi-clipboard-text-outline',
          blurb: 'Curabitur et nisi semper,<br> pellent e sque ',
        },
        {
          name: 'プランニング',
          icon: 'mdi-pencil-outline',
          blurb: 'Curabitur et nisi semper, <br>pellent.',
        },
        {
          name: '施工技術',
          icon: 'mdi-settings-outline',
          blurb: 'Curabitur et nisi semper, <br>pellent.',
        },
        {
          name: 'アフターサポート',
          icon: 'mdi-account',
          blurb: 'Curabitur et nisi semper, <br>pellent.',
        },
      ],
    }),
  }
</script>
