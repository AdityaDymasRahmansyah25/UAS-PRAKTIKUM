<template>
  <q-layout view="hHh lpR fFf">

    <q-header elevated class="bg-cream text-brown">
      <q-toolbar>

        <q-toolbar-title>
          <router-link to="/" class="router-link">UAS Praktikum</router-link>
        </q-toolbar-title>

        <q-btn-dropdown color="brown" label="Daftar Tugas" dropdown-icon="^">
          <q-list>
            <q-item clickable v-close-popup>
              <router-link to="/" class="router-link">
                <q-item-section>
                  <q-item-label>Cuaca</q-item-label>
                </q-item-section>
              </router-link>
            </q-item>
            <q-item clickable v-close-popup>
              <router-link to="/tugas1" class="router-link">
                <q-item-section>
                  <q-item-label>Tugas 1</q-item-label>
                </q-item-section>
              </router-link>
            </q-item>
            <q-item clickable v-close-popup>
              <router-link to="/tugas2" class="router-link">
                <q-item-section>
                  <q-item-label>Tugas 2</q-item-label>
                </q-item-section>
              </router-link>
            </q-item>
            <q-item clickable v-close-popup>
              <router-link to="/tugas3" class="router-link">
                <q-item-section>
                  <q-item-label>Tugas 3</q-item-label>
                </q-item-section>
              </router-link>
            </q-item>
            <q-item clickable v-close-popup>
              <router-link to="/tugas4" class="router-link">
                <q-item-section>
                  <q-item-label>Tugas 4</q-item-label>
                </q-item-section>
              </router-link>
            </q-item>
            <q-item clickable v-close-popup>
              <router-link to="/tugas5" class="router-link">
                <q-item-section>
                  <q-item-label>Tugas 5</q-item-label>
                </q-item-section>
              </router-link>
            </q-item>
            <q-item clickable v-close-popup>
              <router-link to="/tugas6" class="router-link">
                <q-item-section>
                  <q-item-label>Tugas 6</q-item-label>
                </q-item-section>
              </router-link>
            </q-item>
            <q-item clickable v-close-popup>
              <router-link to="/tugas7" class="router-link">
                <q-item-section>
                  <q-item-label>Tugas 7</q-item-label>
                </q-item-section>
              </router-link>
            </q-item>
          </q-list>
        </q-btn-dropdown>
      </q-toolbar>
    </q-header>

    <q-page-container>
      <router-view></router-view>
    </q-page-container>

  </q-layout>
</template>

<script>
export default {
  data() {
    return {
      drawerLeft: false
    };
  },
  methods: {
    toggleDrawer() {
      this.drawerLeft = !this.drawerLeft;
    },
  },
};
</script>

<style scoped>
* {
  font-family: 'Times New Roman', Times, serif;
}

.bg-cream {
  background-color: #f5f1ea;
}

.text-brown {
  color: #8b5d33;
}

.router-link {
  text-decoration: none;
  color: #8b5d33; 
}

.router-link:hover {
  text-decoration: double;
}
</style>
