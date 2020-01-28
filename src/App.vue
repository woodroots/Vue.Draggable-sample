<template>
  <div id="app" class="container-fluid">
    <div class="row">
      <div class="col-6">
        <tree v-model="datas"></tree>
      </div>
      <div class="col-6">
        <div class="bg-light p-3 mt-4">
          <pre>{{ raw }}</pre>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import tree from "./components/tree.vue";
import "bootstrap/dist/css/bootstrap.css";
import "bootstrap-vue/dist/bootstrap-vue.css";

export default {
  components: {
    tree
  },
  computed: {
    raw() {
      return JSON.stringify(this.datas, null, 2);
    }
  },
  data() {
    return {
      datas: [
        {
          name: "あいうえお",
          checked: false,
          child: [
            {
              name: "子供A",
              checked: false,
              child: [
                { name: "孫A", checked: false, child: [] },
                { name: "孫B", checked: false, child: [] }
              ]
            }
          ]
        },
        { name: "かきくけこ", checked: false, child: [] },
        { name: "さしすせそ", checked: false, child: [] },
        {
          name: "ABCD",
          checked: false,
          child: [
            { name: "子B", checked: false, child: [] },
            { name: "子C", checked: false, child: [] }
          ]
        },
        { name: "EFGH", checked: false, child: [] },
        {
          name: "RGB",
          child: [
            {
              name: "子D",
              checked: false,
              child: [{ name: "孫C", checked: false, child: [] }]
            }
          ]
        }
      ]
    };
  }
};
</script>

<style>
</style>
