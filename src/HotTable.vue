<template>
  <div class="ht-wrapper" :id="this.root"></div>
</template>

<script>
  import Handsontable from '../dist/handsontable.full';
  import SettingsMapper from './settingsMapper';
  import {
    hotInit,
    hotDestroy,
    propFactory,
    propWatchFactory,
    updateHotSettings,
    updateBulkHotSettings
  } from './helpers';

  export default {
    name: 'HotTable',
    props: propFactory(),
    props: propFactory(),
    data: function() {
      return {
        instance: Handsontable
      }
    },
    watch: propWatchFactory(updateHotSettings, updateBulkHotSettings),
    mounted: function() { return hotInit(this); },
    beforeDestroy: function() { return hotDestroy(this); },
  };
</script>

<style>
  @import "../dist/handsontable.full.css";
 // @import "../dist/main.css";
</style>
