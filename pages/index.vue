<template>
  <div>
    <button @click="showTopic('1')">題目1</button>
    <button @click="showTopic('2')">題目2</button>
    <button @click="showTopic('3')">題目3</button>
    <button @click="showTopic('4')">TodoList</button>
    <List :data="type" v-show="topic === '1'" />
    <Food v-show="topic === '2'" />
    <Question v-show="topic === '3'" />
    <TodoList v-show="topic === '4'" />
  </div>
</template>

<script>
export default {
  name: "IndexPage",
  data() {
    return {
      type: [
        {
          name: "Anna",
          year: 10,
          class: "A",
        },
        {
          name: "Mark",
          year: 10,
          class: "M",
        },
        {
          title: "Javascript Info",
          category: "book",
          rating: 10,
        },
        {
          title: "Fantasy",
          category: "movie",
          rating: 5,
        },
        {
          winner: "Amy",
          rank: 1,
        },
        {
          winner: "Bob",
          rank: 2,
        },
        {
          winner: "Jack",
          rank: 2,
        },
      ],
      topic: "1",
    };
  },
  mounted() {},
  methods: {
    /**
     * 切換題目
     */
    showTopic(topic) {
      this.topic = topic;
    },
  },
};
</script>
