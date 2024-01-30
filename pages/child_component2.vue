<template>
  <div>{{ childMsg }}</div>
</template>
<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import EventBus from "@/utils/event-bus";
@Component({})
export default class ChildComponent2 extends Vue {
  private childMsg = "";
  mounted() {
    EventBus.$on("msgEventBus", (msg: string) => {
      this.childMsg = msg;
    });
  }
}
</script>
