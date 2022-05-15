<template>
  <div>
    <h1>
      {{ title }}
    </h1>
    <book-form  @addbook='appendBook'></book-form>
    <ul>
      <book-item v-for="book in books" :book="book"></book-item>
    </ul>
  </div>
</template>

<script>
import BookItem from './BookItem';
import BookForm from './BookForm';

export default {
    name: 'BookList',
    data: {
        title: 'All Books',
        books: [
            { title: 'Self-Reliance', author: 'Ralph Waldo Emerson' },
            { title: 'American Gods', author: 'Neil Gaiman' },
            { title: 'Amusing Ourselves to Death', author: 'Neil Postman' },
        ]
    },
    components: {
        BookItem,
        BookForm
    },
    methods: {
        appendBook(bookTitle, bookAuthor) {
            this.books.push( { title: bookTitle, author: bookAuthor} );
        }
    }
}
</script>

<style scoped>
h1,
h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}
</style>