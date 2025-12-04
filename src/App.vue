<template>
  <div class="container">

    <header>
      <h1>Cooking Masterclass</h1>
      <h3>Wishlist: {{ wishlistCount }}</h3>
    </header>

    <course-list 
      :courses="courses"
      @addToWishlist="increaseWishlist"
    />
  </div>
</template>

<script>
import CourseList from './components/CourseList.vue'

export default {
  name: "App",
  components: {
    CourseList
  },

  data() {
    return {
      wishlistCount: 0,

      courses: [
        { 
          id: 1, 
          title: "Beginner Cooking Basics",
          chef: "Chef Nobubele K",
          price: 299,
          level: "Beginner",
          soldOut: false
        },
        { 
          id: 2, 
          title: "Sushi Mastery",
          chef: "Chef Tsunoda ",
          price: 450,
          level: "Advanced",
          soldOut: true
        },
        { 
          id: 3, 
          title: "Italian Pasta Workshop",
          chef: "Chef Bruno",
          price: 380,
          level: "Intermediate",
          soldOut: false
        }
      ]
    }
  },

  methods: {
    increaseWishlist() {
      this.wishlistCount++
    }
  }
}
</script>

<style>
.container {
  width: 90%;
  margin: auto;
  font-family: Arial, sans-serif;
}
header {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
</style>
