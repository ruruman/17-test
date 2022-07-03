<template>
  <div calss="container">
    <div v-if="this.type1List.length > 0">
      <h2>type1</h2>
      <div class="typeOne center">
        <div
          class="item center"
          v-for="(item, index) in type1List"
          :key="index"
        >
          <h5>student:{{ item.name }}</h5>
          <h5>year:{{ item.year }}, Room:{{ item.class }}</h5>
        </div>
      </div>
    </div>
    <div v-if="this.type2List.length > 0">
      <h2>type2</h2>
      <div class="typeTwo center">
        <div
          class="item center"
          v-for="(item, index) in type2List"
          :key="index"
        >
          <h5>Title:{{ item.title }}</h5>
          <h5>category:{{ item.category }}|{{ item.rating }}likes</h5>
        </div>
      </div>
    </div>
    <div v-if="this.type3List.length > 0">
      <h2>type3</h2>
      <div class="typeThree">
        <h3>Top 3 Winners</h3>
        <div class="item" v-for="(item, index) in type3List" :key="index">
          {{ item.rank }} {{ item.winner }}
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "List",
  props: {
    data: {
      type: Array,
      required: true,
    },
  },
  data() {
    return {
      type1List: [],
      type2List: [],
      type3List: [],
    };
  },
  mounted() {
    this.filterList(this.data);
  },
  methods: {
    /**
     * 將list分為type1,type2,type3
     */
    filterList(data) {
      this.type1List = data.filter((ele) => ele.class);
      this.type2List = data.filter((ele) => ele.title);
      this.type3List = data.filter((ele) => ele.rank);
    },
  },
};
</script>
<style>
.container {
  width: 100vw;
  height: 100vh;
}
.typeOne {
  width: 100%;
  height: 200px;
  background-color: #aaa;
}
.typeOne .item {
  height: 70px;
}
.typeTwo {
  width: 100%;
  height: 200px;
  background-color: #aaa;
}
.typeTwo .item {
  height: 70px;
}
.item h5 {
  margin: 0;
}
.typeThree {
  width: 100%;
  height: 200px;
  background-color: #000;
}
.typeThree h3 {
  padding: 15px;
  color: #fff;
}
.center {
  display: flex;
  flex-direction: column;
  justify-content: center;
}
.item {
  background-color: #fff;
  margin: 5px;
  padding: 5px;
  border-radius: 5px;
}
</style>
