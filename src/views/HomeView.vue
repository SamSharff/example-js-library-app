<script>
import { createApp } from "vue";
import { HotTable } from "@handsontable/vue3";
import { registerAllModules } from "handsontable/registry";
import { createSpreadsheetData } from "./helpers";

// register Handsontable's modules
registerAllModules();

const app = createApp({
  data() {
    return {
      hotSettings: {
        data: createSpreadsheetData(6, 10),
        colHeaders: true,
        height: "auto",
        licenseKey: "non-commercial-and-evaluation",
      },
    };
  },
  components: {
    HotTable,
  },
});
app.mount("#example1");
</script>

<template>
  <div id="example1">
    <hot-table :settings="hotSettings"></hot-table>
  </div>
</template>
