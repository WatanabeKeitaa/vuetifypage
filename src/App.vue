<template>
 <v-card class="mx-auto overflow-hidden"
 height="1000">
    <v-app-bar
      color="deep-purple"
      dark
    >
    <v-app-bar-nav-icon v-on:click="drawer = true"></v-app-bar-nav-icon>
      <template v-slot:img="{ props }">
        <v-img
          v-bind="props"
          gradient="to top right, rgba(100,115,201,.7), rgba(25,32,72,.7)"
        ></v-img>
      </template>

      <v-toolbar-title>kintoreapuri</v-toolbar-title>

      <template v-slot:extension>
        <v-tabs 
        fixed-tabs
        v-model="tab"
        align-with-title
        >
        <v-tab
            v-for="item in items"
            :key="item.tab"
          >
            {{ item.tab }}
          </v-tab>
          <!-- <v-tab>つぶやき</v-tab>
          <v-tab>筋トレ</v-tab>
          <v-tab>料理</v-tab> -->
        </v-tabs>
      </template>
    </v-app-bar>

    <v-tabs-items v-model="tab">
      <v-tab-item
        v-for="item in items"
        :key="item.tab"
      >
      <v-card flat>
          <v-card-text>{{ item.content }}</v-card-text>
        </v-card>
      </v-tab-item>
    </v-tabs-items>

    <v-sheet
      id="scrolling-techniques-4"
      class="overflow-y-auto"
      max-height="600"
    >
      <v-container style="height: 1000px;"></v-container>
    </v-sheet>
    <v-navigation-drawer
      v-model="drawer"
      absolute
      temporary
    >
      <v-list
        nav
        dense
      >
        <v-list-item-group
          v-model="group"
          active-class="deep-purple--text text--accent-4"
        >
          <v-list-item>
            <v-list-item-icon>
              <v-icon>mdi-home</v-icon>
            </v-list-item-icon>
            <v-list-item-title>ホーム</v-list-item-title>
          </v-list-item>

          <v-list-item>
            <v-list-item-icon>
              <v-icon>mdi-magnify</v-icon>
            </v-list-item-icon>
            <v-list-item-title>検索</v-list-item-title>
          </v-list-item>

          <v-list-item>
            <v-list-item-icon>
              <v-icon>mdi-calendar</v-icon>
            </v-list-item-icon>
            <v-list-item-title>カレンダー</v-list-item-title>
          </v-list-item>

          <v-list-item>
            <v-list-item-icon>
              <v-icon>mdi-account</v-icon>
            </v-list-item-icon>
            <v-list-item-title>マイページ</v-list-item-title>
          </v-list-item>

        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>
  </v-card>
</template>

<script>
// import HelloWorld from './components/HelloWorld';
// import HeaderItem from './components/HeaderItem';

export default {
  name: 'App',

  components: {
    // HelloWorld,
    // headerItem
  },

  // data: () => ({
  //   //
  //   drawer: false,
  //     group: null,
  // }),
  data () {
      return {
        tab: null,
        drawer: false,
        group: null,
        items: [
           { tab: 'つぶやき', content: 'つぶやきです、Scriptタグから配列でとってきてます' },
          { tab: '筋トレ', content: '筋トレ' },
          { tab: '料理', content: '料理' },
        ],
      }
    },
};
</script>
