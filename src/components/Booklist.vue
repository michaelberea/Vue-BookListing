<template>
    <div>
        <h1>{{ title }}</h1>
        <ul>
            <book-item v-for="book in books" v-bind:book="book"/>
        </ul>
        <book-form @addBook='appendBook'/>
    </div>
</template>

<script>
    import './BookItem';
    import BookItem from './BookItem.vue';
    import BookForm from './BookForm';

    export default {
        name: 'Booklist',
        components: {
            BookItem,
            BookForm
        },
        methods: {
            appendBook(bookTitle, bookAuthor) {
                this.books.push({ title: bookTitle, author: bookAuthor });
            }
        },
        data () {
            return {
                title: 'All Books',
                books: [    
                    {title: 'Self-Reliance', author: 'Ralph Waldo Emerson'},
                    {title: 'American Gods', author: 'Neil Gaiman'},
                    {title: 'Amusing Ourselves to Death', author: 'Neil Postman'},
                ],
            };
        },
        appendBook() {

        }
    }
</script>

<style>

</style>