<template>
  <div>
    <div id="header"></div>
    <div id="search-results-list">
      <drawer-search-results-list-item 
        v-for="searchResult in searchResults" 
        :key="searchResult.entity"
        :prenom="searchResult.prenom"
        :nom="searchResult.nom"
        :entity="searchResult.entity"
        :code_postal="searchResult.code_postal"
        :pays_code="searchResult.pays_code"
        :numero_piece_identite="searchResult.numero_piece_identite"
        :star="searchResult.star"
        :degree="searchResult.degree">
      </drawer-search-results-list-item>
    </div>
  </div>
</template>

<script>
import { mapGetters, mapState } from 'vuex';
import DrawerSearchResultsListItem from './DrawerSearchResultsListItem';

export default {
  components: { DrawerSearchResultsListItem },
  computed: {
    ...mapState(["searchResults"]),
    ...mapGetters(["showSearchResultsDisplayButton"])
  }
}
</script>

<style lang="scss">
@import "../scss/settings.scss";

#header { 
  height: 80px; 
  background-color: white;
  z-index: 15;
}

#search-results-list {
  position: absolute;
  top: 80px;
  left:0px;
  right:0px;
  bottom:0px;
  overflow-y: scroll;
}

</style>
