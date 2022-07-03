<template>
  <div>
    <h2>input:{{ recipes }}</h2>
    <h2>output:{{ answer }}</h2>
  </div>
</template>
<script>
export default {
  name: "Food",
  data() {
    return {
      recipes: [
        ["Pasta", "Tomato Sauce", "Onions", "Garlic"],
        ["Chicken Curry", "Chicken", "Curry Sauce"],
        ["Fried Rice", "Rice", "Onions", "Nuts"],
        ["Salad", "Spinach", "Nuts"],
        ["Sandwich", "Cheese", "Bread"],
        ["Quesadilla", "Chicken", "Cheese"],
      ],
      answer: [],
    };
  },
  mounted() {
    this.solution(this.recipes);
  },
  methods: {
    solution(recipes) {
      const mtf = {};
      const materialSort = [];
      recipes.forEach(function (ele) {
        const foodName = ele[0];
        for (let j = 1; j < ele.length; j++) {
          const key = ele[j];
          if (!mtf.hasOwnProperty(key)) {
            mtf[key] = [];
            materialSort.push(key);
          }
          mtf[key].push(foodName);
        }
      });
      materialSort.sort();
      materialSort.forEach((material) => {
        const row = [material, ...mtf[material]];
        this.answer.push(row);
      });
    },
  },
};
</script>
