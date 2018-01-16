<template>
    <div id="container">
        <div class="row">
            <div class="col-xs-12">
                <button @click="selectedComponent = 'appQuote'">Quote</button>
                <button @click="selectedComponent = 'appAuthor'">Author</button>
                <button @click="selectedComponent = 'appNew'">New</button>
                <hr>
                <p>{{selectedComponent}}</p>
                <keep-alive>
                    <component :is="selectedComponent">
                        <p>Default content</p>
                    </component>
                </keep-alive>
                <!--<app-quote>-->
                    <!--<h2 slot="title">{{ quoteTitle }}</h2>-->
                    <!--&lt;!&ndash;<p>A Wonderful Quote</p>&ndash;&gt;-->
                <!--</app-quote>-->
            </div>
        </div>
    </div>
</template>

<script>
    import Quote from './component/Quote.vue'
    import Author from './component/Author.vue'
    import New from './component/New.vue'
    export default {
        data() {
            return {
                quoteTitle: 'The Quote',
                selectedComponent: "appQuote"
            }
        },
        components: {
            appQuote: Quote,
            appAuthor: Author,
            appNew: New
        }
    }
</script>

<style>

</style>

