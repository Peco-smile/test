<template>
  <section id="results" class="overflow-hidden" style="padding: 54px 0 100px">
    <v-row align="center" justify="center">
      <v-col sm="6">
        <base-bubble-1
          style="transform: rotate(180deg) translateY(70%) translateX(4%)"
        />
        <v-row align="center" justify="center" class="mt-negative">
          <v-col cols="10" md="8">
            <v-img
              :src="require('@/assets/result_title.png')"
              max-height="30px"
              max-width="340px"
              position="top"
              class="border"
            ></v-img>
            <div class="py-4"></div>
            <base-text>
              テキスト色々
            </base-text>
          </v-col>
        </v-row>
      </v-col>
      <v-col sm="6">
        <v-img
          :src="require('@/assets/1359343_m.jpg')"
          height="auto"
          max-width="400px"
        ></v-img>
      </v-col>
    </v-row>
  </section>
</template>

<style>
  .border {
    border-bottom: 2px solid #808198;
  }
  @media (min-width: 960px) {
    .mt-negative {
      margin-top: -150px;
    }
  }
</style>
