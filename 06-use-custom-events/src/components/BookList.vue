<template>
  <div>
    <div v-for="(book, index) in books" :key="index" class="book">
      <h3>{{ book.title }}</h3>
      <button @click="toggleBookmark(book)">
        {{ book.isBookmarked ? "Remove Bookmark" : "Add Bookmark" }}
      </button>
    </div>
  </div>
</template>

<script>
export default {
  props: ["books"],
  methods: {
    toggleBookmark(book) {
      book.isBookmarked = !book.isBookmarked;
      this.$emit("bookmark-changed", book);
    },
  },
};
</script>
