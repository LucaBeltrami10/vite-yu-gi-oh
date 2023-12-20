<template>
  <AppHeader />
  <AppMain :listCard="cardDataList" :archetypesList="archetypesList" @selected="selectedArchetype()" />
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
      archetypeToFilter: '',

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
    getArchetypeArray() {
      axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php')
        .then((response) => {
          this.archetypesList = response.data
          console.log(this.archetypesList)
        })
        .catch(function (error) {
          // handle error
          console.log(error);
        })
    },
    selectedArchetype(NewFilter) {
      console.log('archetipo cambiato')
      console.log(NewFilter)
      this.archetypeToFilter == NewFilter

    }

  },
  created() {
    this.getCardArray();
    this.getArchetypeArray();
  }

}
</script>

<style lang="scss">
@use './style/general.scss' as *;
</style>
