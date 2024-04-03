<template>
  <div id="app">
    <book-list
      :books="books"
      @bookmark-changed="handleBookmarkChanged"
    ></book-list>
  </div>
</template>

<script>
import BookList from "./components/BookList.vue";

export default {
  name: "App",
  components: {
    BookList,
  },
  data() {
    return {
      books: [
        { title: "Book Title 1", isBookmarked: false },
        { title: "Book Title 2", isBookmarked: false },
      ],
    };
  },
  methods: {
    handleBookmarkChanged(book) {
      // Handle bookmark change here
      console.log(
        "Bookmark changed for:",
        book.title,
        "New state:",
        book.isBookmarked
      );
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
