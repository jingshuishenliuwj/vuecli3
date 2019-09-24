<template>
  <div name="show">
    <ul class="goodList">
      <li v-for="good in list">
        <img v-bind:src="good.img" />
        <p>{{good.goodName}}</p>
      </li>
    </ul>
  </div>
</template>
<style >
.goodList li {
  width: 200px;
  height: 200px;
  list-style: none;
  float: left;
  color: red;
  font-size: 9px;
  margin-bottom: 30px;
}
.goodList img {
  width: 180px;
  height: 180px;
}
</style>
<script>
import { watch } from "fs";
export default {
  name: "show",
  data() {
    var that = this;
    var url=""
    if (that.goodId == 1) {
        url = "json/bijiben.json";
      } else if (that.goodId == 2) {
        url = "json/shouji.json";
      }else{
           url = "json/shouji.json";
      }
    that.$http.get(url).then(function(res) {
      that.list = res.data;
    });
    return {
      list: []
    };
  },
  props: {
    goodId: Number
  },
  watch: {
    goodId() {
      var that = this;
      var url = "";
      if (that.goodId == 1) {
        url = "json/bijiben.json";
      } else if (that.goodId == 2) {
        url = "json/shouji.json";
      }else{
           url = "json/shouji.json";
      }
      that.$http.get(url).then(function(res) {
        that.list = res.data;
      });
      return {
        list: []
      };
    }
  }
};
</script>