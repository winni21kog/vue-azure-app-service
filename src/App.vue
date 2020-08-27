<template>
  <v-app>

    <!-- 側邊導覽列 -->
    <v-navigation-drawer app v-model="drawer">

      <!-- 網頁標題 -->
      <v-list-item to="/">
        <v-list-item-content>
          <v-list-item-title class="title"> MAWI </v-list-item-title>
        </v-list-item-content>
      </v-list-item>

      <v-divider></v-divider>

      <!-- 選單 -->
      <v-list dense>
        <v-list-item>
          <v-list-item-icon>
            <v-icon>mdi-*</v-icon>
          </v-list-item-icon>
          <v-list-item-content>
            <v-list-item-title v-for='(n,i) in info' :key=i>
              <v-card
              class="mx-auto"
              max-width="344"
              outlined
            >
              <v-list-item three-line>
                <v-list-item-content>
                  <v-list-item-title class="headline mb-1" v-text='n.Text'></v-list-item-title>
                  <v-list-item-subtitle v-text='n.Value'></v-list-item-subtitle>
                </v-list-item-content>
              </v-list-item>
            </v-card>
            </v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>

    </v-navigation-drawer>

    <!-- 頂部導覽列 -->
    <v-app-bar app color="blue" dark collapse>
      <v-app-bar-nav-icon @click.stop="drawer = !drawer"></v-app-bar-nav-icon>
    </v-app-bar>

    <!-- 內容區塊 -->
    <v-content>
      <v-container fluid>
        <HelloWorld :open='open'></HelloWorld>
      </v-container>
    </v-content>

    <!-- footer -->
    <v-footer app class="justify-center"></v-footer>

  </v-app>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue';

export default {
  // name: 'App',
  components: {
    HelloWorld,
  },
  data() {
    return {
      drawer: false,
      info: [
        {
          Text: 'Name',
          Value: 'Dave',
        },
        {
          Text: 'Age',
          Value: '25',
        },
      ],
    };
  },

};
</script>
