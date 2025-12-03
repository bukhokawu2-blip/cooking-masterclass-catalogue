<template>
  <div>
    <course-card 
      v-for="item in courses" 
      :key="item.id"
      :title="item.title"
      :chef="item.chef"
      :price="item.price"
      :level="item.level"
      :soldOut="item.soldOut"
      @saveCourse="$emit('addToWishlist')"
    />
  </div>
</template>

<script>
import CourseCard from './CourseCard.vue'

export default {
  name: "CourseList",
  props: ['courses'],
  components: {
    CourseCard
  }
}
</script>
