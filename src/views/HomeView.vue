<template>
  <div class="home">
    <h1>Blogs</h1>
    <PostList :posts="posts"/>
  </div>
</template>

<script>
import { ref } from "vue";
import PostList from '@/components/PostList.vue';

export default {
  name: "HomeView",
  components: { PostList },
  setup() {
    const posts = ref([
      {
        id: 1,
        title: "The Benefits of Yoga for Mental Health",
        body: "Yoga has been practiced for thousands of years and has numerous physical and mental health benefits. In particular, practicing yoga can be incredibly beneficial for mental health. It can help to reduce stress, anxiety, and depression by calming the mind and improving overall well-being. Yoga involves deep breathing and meditation, which can help to lower cortisol levels and promote relaxation. Additionally, yoga can improve flexibility, balance, and strength, which can lead to better overall health.",
      },
      {
        id: 2,
        title: "The Importance of Sleep for Optimal Health",
        body: "Getting enough sleep is crucial for overall health and well-being. Sleep helps to restore and repair the body, and plays a role in memory consolidation and learning. Lack of sleep can lead to a range of health problems, including obesity, diabetes, heart disease, and depression. To improve sleep, it's important to establish a regular sleep routine, avoid caffeine and alcohol before bed, and create a comfortable sleep environment.",
      },
      {
        id: 3,
        title: "5 Easy Ways to Incorporate Exercise into Your Daily Routine",
        body: "Regular exercise is important for maintaining good health, but it can be difficult to find the time and motivation to do it. Luckily, there are many simple ways to incorporate exercise into your daily routine. Some ideas include taking the stairs instead of the elevator, going for a walk during your lunch break, doing bodyweight exercises at home, or joining a fitness class. By finding ways to move your body throughout the day, you can improve your overall health and fitness.",
      },
      {
        id: 4,
        title: "The Benefits of Eating a Plant-Based Diet",
        body: "Eating a plant-based diet can have numerous health benefits. Plant-based diets are rich in fiber, vitamins, and minerals, and are typically lower in saturated fat and calories than animal-based diets. Eating a plant-based diet can reduce the risk of heart disease, stroke, diabetes, and certain types of cancer. Additionally, plant-based diets can be more environmentally sustainable and ethical than animal-based diets. Some plant-based foods to include in your diet are fruits, vegetables, whole grains, legumes, nuts, and seeds.",
      },
      {
        id: 5,
        title: "Tips for Improving Your Mental Health",
        body: "Taking care of your mental health is just as important as taking care of your physical health. There are many things you can do to improve your mental health, such as getting enough sleep, exercising regularly, practicing relaxation techniques like deep breathing or meditation, and seeking support from friends, family, or a mental health professional. It's also important to prioritize self-care, set realistic goals, and practice positive self-talk. By making mental health a priority, you can improve your overall well-being and quality of life.",
      },
    ]);

    return { posts };
  },
};
</script>
