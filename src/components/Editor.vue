<template>
    <b-container>
        <b-card
                title="Editor"
                class="mb-2 mx-auto"
        >
            <b-textarea
                    v-model="content"
                    placeholder="Enter something"
                    rows="3"
                    max-rows="6"
                    class=""
            >
            </b-textarea>
        </b-card>
        <b-card
                title="Previewer"
                class="mx-auto"
        >
            <span v-html="mark(content)">
            </span>
        </b-card>
    </b-container>
</template>

<script>

    import marked from "marked";

    marked.setOptions({
        breaks: true
    })

    export default {
        name: "Editor",
        data() {
            return {
                content: ''
            }
        },
        methods: {
            mark(val) {
                return marked(val)
            },

        }
    }
</script>

<style scoped>

</style>