<template>
  <div class="cft-search-criteria">
    <b-button squared variant="primary" @click="changeQueryType">
      {{ queryType }}
    </b-button>
    <span class="cft-search-item-criteria"> of the criteria are met.</span>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";

@Component
export default class TaskListSearchType extends Vue {
  private queryType: string = "ALL";

  changeQueryType () {
    this.queryType === "ALL"
      ? (this.queryType = "ANY")
      : (this.queryType = "ALL");
    this.$root.$emit("call-updateSearchQueryType", {
      queryType: this.queryType,
    });
  }
}
</script>
