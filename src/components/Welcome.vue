<template>
  <section id="welcome" class="overflow-hidden">
    <v-row no-gutters>
      <v-col class="hidden-sm-and-down" md="6">
        <v-img src="https://images.unsplash.com/photo-1543525324-9146d43c2a4e?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=634&q=80" height="100vh" />
      </v-col>

      <v-col
        class="align-content-space-between layout wrap pa-sm-5"
        cols="12"
        md="6"
        :class="[$vuetify.breakpoint.smAndDown ? 'pa-5' : 'pa-0']"
      >
        <base-bubble-1 style="transform: rotate(180deg) translateY(25%)" />

        <v-row align="center" justify="center">
          <v-col cols="12" md="8">
            <base-heading>
              家族の夢を終わらせますか？
            </base-heading>
            <base-text>
              土地選び、間取り、資金、住宅会社選び<br />
              資金と間取りの兼ね合い<br>
              形にしないとわからない。間取りを考えてみましょう。
            </base-text>
            <base-btn class="mt-4">
              Learn More!
            </base-btn>
          </v-col>
        </v-row>

        <base-bubble-2
          style="transform: rotate(180deg) translate(-200px, -15%)"
        />
      </v-col>
    </v-row>
  </section>
</template>

<style></style>
