<script lang="ts">
  import '@arcgis/core/assets/esri/themes/dark/main.css';
  import './../index.css';

  import { defineCustomElements } from '@arcgis/map-components/dist/loader';

  import type { ArcgisMapCustomEvent } from '@arcgis/map-components';

  defineCustomElements();

  function handleMapLoad(e: ArcgisMapCustomEvent<void>) {
    console.log('Map loaded', e);
  }

  const popup = {
    dockEnabled: true,
    dockOptions: {
      position: 'bottom-right',
      breakpoint: false
    }
  };

  const theme = {
    accentColor: 'purple',
    textColor: [125, 255, 13, 0.9]
  };
</script>

<arcgis-map
  item-id="d5dda743788a4b0688fe48f43ae7beb9"
  on:arcgisViewReadyChange={handleMapLoad}
  {popup}
  {theme}
>
  <arcgis-search position="top-right" />
  <arcgis-expand position="bottom-left">
    <arcgis-area-measurement-2d />
  </arcgis-expand>
</arcgis-map>

<style>
  arcgis-map {
    height: 100%;
    width: 100%;
  }
</style>
