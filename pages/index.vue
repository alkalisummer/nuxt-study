<template>
  <div>
    <ChildComponent1 :text="text" @msg-handler="msgHandler"></ChildComponent1>
    <ChildComponent2></ChildComponent2>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import ChildComponent1 from "./child_component1.vue";
import ChildComponent2 from "./child_component2.vue";

@Component({
  components: {
    ChildComponent1,
    ChildComponent2,
  },
})
export default class Index extends Vue {
  private text = "Hello Wolrd!!";

  msgHandler(msg: string) {
    console.log("msg :" + msg);
  }
}
</script>
