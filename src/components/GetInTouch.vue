<template>
  <section id="get-in-touch" class="overflow-hidden">
    <v-row class="info white--text" no-gutters>
      <v-col cols="12">
        <base-bubble-1 />
        <base-heading class="mb-5 text-center">
          お問い合わせ
        </base-heading>
      </v-col>

      <v-col class="pa-5 text-center" cols="12" md="6">
        <v-row>
          <v-col cols="6">
            <base-subheading>デバイス・ホーム</base-subheading>
            <div class="py-2"></div>
            <base-text class="pa-2"
              >デバイス・ホームは、家を売る会社ではなく、福島の皆様に安くていい家をつくっている会社です。</base-text
            >
          </v-col>
          <v-col cols="6" class="text-left">
            <base-text class="d-flex" v-for="(item, i) in items" :key="i">
              <v-icon large dark v-text="item.icon" />
              <div v-html="item.content"></div>
            </base-text>
          </v-col>
        </v-row>
      </v-col>

      <v-col class="pa-5" cols="12" md="6">
        <v-sheet color="transparent" max-width="600">
          <v-form ref="form" v-model="form" class="white--text">
            <v-text-field
              v-bind:class="{ delatearea: inputdata }"
              v-model="name"
              :rules="[rules.required]"
              autocomplete="name"
              color="info"
              label="お名前"
              solo
              flat
            />
            <base-text v-bind:class="{ delatearea: makesure }" class="mb-11"
              >お名前：{{ name }}</base-text
            >

            <v-text-field
              v-bind:class="{ delatearea: inputdata }"
              v-model="email"
              :rules="[rules.required, rules.email]"
              autocomplete="email"
              color="info"
              label="メールアドレス"
              solo
              flat
            />
            <base-text v-bind:class="{ delatearea: makesure }" class="mb-11"
              >メールアドレス：{{ email }}</base-text
            >

            <v-text-field
              v-bind:class="{ delatearea: inputdata }"
              v-model="phone"
              :rules="[rules.required, rules.phone]"
              autocomplete="tel"
              color="info"
              label="電話番号(半角数字のみ、「-」省略)"
              solo
              flat
            />
            <base-text v-bind:class="{ delatearea: makesure }" class="mb-11"
              >電話番号：{{ phone }}</base-text
            >

            <v-textarea
              v-bind:class="{ delatearea: inputdata }"
              v-model="contents"
              :rules="[rules.required]"
              color="info"
              label="お問い合わせ内容"
              solo
              flat
            />
            <base-text v-bind:class="{ delatearea: makesure }"
              >お問い合わせ内容：{{ contents }}</base-text
            >

            <v-row>
              <v-col class="d-flex" v-bind:class="{ delatearea: inputdata }">
                <base-btn @click="$refs.form.reset()">クリア</base-btn>
                <v-spacer></v-spacer>
                <base-btn @click="clickbtn" :disabled="!form"
                  ><span class="mgr-10">確</span>認</base-btn
                >
              </v-col>

              <v-col class="d-flex" v-bind:class="{ delatearea: makesure }">
                <base-btn @click="clickbtn_back">戻る</base-btn>
                <v-spacer></v-spacer>
                <base-btn>送信</base-btn>
              </v-col>
            </v-row>
          </v-form>
        </v-sheet>
      </v-col>
    </v-row>
  </section>
</template>

<script>
  export default {
    name: 'GetInTouch',

    data: () => ({
      name: undefined,
      email: undefined,
      phone: undefined,
      contents: undefined,
      form: false,
      inputdata: false,
      makesure: true,
      rules: {
        required: (value) => !!value || '必須項目です',
        email: (value) => {
          const pattern = /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/
          return pattern.test(value) || '正しい形式で入力してください'
        },
        phone: (value) => {
          const pattern = /^0\d{9,10}$/
          return pattern.test(value) || '9~10桁の番号を入力してください'
        },
      },
      items: [
        {
          icon: 'mdi-map-marker',
          content: '福島県会津若松市南千石町3-12',
        },
        {
          icon: 'mdi-email',
          content:
            '<a href="mailto:info@luckydakara.com">info@luckydakara.com</a>',
        },
        {
          icon: 'mdi-phone',
          content: '<a href="tel:0120-91-4040">0120-91-4040</a>',
        },
        {
          icon: 'mdi-instagram',
          content:
            '<a href="https://www.instagram.com/devicehome8781/">@devicehome8781</a>',
        },
        {
          icon: 'mdi-facebook',
          content:
            '<a href="https://www.facebook.com/devicehome8781/?ref=bookmarks">@devicehome8781</a>',
        },
        {
          icon: 'fab fa-line',
          content:
            '<a class="mgl-10" href="https://line.me/R/ti/p/%40lzr3109e">@lzr3109e</a>',
        },
        {
          icon: 'mdi-youtube',
          content:
            '<a href="https://www.youtube.com/channel/UCnMwPbxdcYbxJYPODfdv1fA">デバイスホーム公式チャンネル</a>',
        },
      ],
    }),

    methods: {
      clickbtn() {
        this.inputdata = true
        this.makesure = false
      },
      clickbtn_back() {
        this.inputdata = false
        this.makesure = true
      },
    },
  }
</script>

<style>
  a {
    text-decoration: none;
  }
  .mgr-10 {
    margin-right: 10px;
  }
  @media (min-width: 768px) {
    a[href^='tel:'] {
      pointer-events: none;
    }
  }
  .delatearea {
    position: absolute;
    left: -9999px;
  }
</style>
