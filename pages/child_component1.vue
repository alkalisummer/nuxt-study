<template>
  <div>
    {{ text }}
    <input type="text" v-model="message" />
    <button @click="msgHandler">저장</button>
  </div>
</template>
<script lang="ts">
import { Component, Emit, Prop, Vue } from "vue-property-decorator";
import EventBus from "@/utils/event-bus";

@Component({})
export default class ChildComponent extends Vue {
  @Prop({ type: String, default: "" }) readonly text!: string;
  private message = "";

  @Emit()
  private msgHandler() {
    EventBus.$emit("msgEventBus", this.message + " Bus!!!");
    return this.message + "hi";
  }
}
</script>
