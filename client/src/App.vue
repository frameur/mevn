<template>
  <v-app id="inspire">
    <v-navigation-drawer v-model="drawer" app>
      <v-list-item>
        <v-list-item-content>
          <v-list-item-title> R.CREAWEBFRAM </v-list-item-title>
          <v-list-item-subtitle>
            Essentiel Design
          </v-list-item-subtitle>
        </v-list-item-content>
      </v-list-item>
      <v-divider></v-divider>
      <v-list dense>
        <v-list-item-group color="deep-orange">
          <v-list-item v-for="(item, i) in items" :key="i" :to="item.link" link>
            <v-list-item-icon>
              <v-icon v-text="item.icon"></v-icon>
            </v-list-item-icon>
            <v-list-item-content>
              <v-list-item-title v-text="item.title"></v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar color="blue lighten-4" app>
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>
      <v-toolbar-title>RECIPES AND OTHER</v-toolbar-title>
    </v-app-bar>

    <v-main>
      <router-view></router-view>
    </v-main>
  </v-app>
</template>

<script>
export default {
  data: () => ({
    drawer: null,
    items: [
      { title: "Accueil", icon: "mdi-home", link: "/" },
      {
        title: "Ajouter",
        icon: "mdi-note-plus",
        link: "/add-post",
      },
      { title: "A propos", icon: "mdi-help-box", link: "/about" },
      { title: "RecipesAPI", icon: "mdi-food-fork-drink", link: "/recipesapi" },
      { title: "Contact", icon: "mdi-message-bulleted", link: "/contact" },
    ],
  }),
};
</script>
