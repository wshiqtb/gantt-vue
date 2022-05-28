<template>
  <div ref="gantt"></div>
</template>

<script>
import { gantt } from "dhtmlx-gantt";
export default {
  name: "gantt",
  props: {
    tasks: {
      type: Object,
      default() {
        return { data: [], links: [] };
      },
    },
  },

  mounted: function () {
    gantt.config.xml_date = "%Y-%m-%d";
    gantt.config.columns = [
      { name: "text", label: "任务名称", tree: true, width: "*" },
      { name: "start_date", label: "开始时间", align: "center" },
      { name: "duration", label: "持续时间", align: "center" },
    ];

    gantt.init(this.$refs.gantt);
    gantt.parse(this.$props.tasks);
  },
};
</script>

<style>
@import "~dhtmlx-gantt/codebase/dhtmlxgantt.css";
</style>
