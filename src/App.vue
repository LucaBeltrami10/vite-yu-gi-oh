<template>
  <AppHeader />
  <AppMain :listCard="cardDataList" />
</template>

<script>
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import axios from 'axios';

export default {
  components: {
    AppHeader,
    AppMain,
  },
  data() {
    return {
      cardDataList: [],
      archetypesList: [],

    }
  },
  methods: {
    getCardArray() {
      axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0')
        .then((response) => {
          this.cardDataList = response.data.data;
          console.log(this.cardDataList)
        })
    },
    getArchetipe() {
      axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php')
        .then(function (response) {
          // handle success
          console.log(response);
        })
        .catch(function (error) {
          // handle error
          console.log(error);
        })
    }

  },
  created() {
    this.getCardArray();
  }

}
</script>

<style lang="scss">
@use './style/general.scss' as *;
</style>
