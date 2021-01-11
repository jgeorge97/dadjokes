<template>
    <div>
        <SearchJokes v-on:search-text="searchText" />
        <Loader v-if="enableLoader" />
        <joke v-for="joke in jokes" :key="joke.id" :id="joke.id" :joke="joke.joke" />
    </div>
</template>

<script>
import axios from 'axios';
import Joke from '~/components/Joke.vue';
import SearchJokes from '~/components/SearchJokes.vue';
import Loader from "~/components/Loader";
export default {
  components: { Joke, SearchJokes, Loader },
    data() {
        return {
            jokes: [],
            enableLoader:false
        }
    },
    async created() {
        this.enableLoader = true;
        const config = {
            headers: {
                'Accept': 'application/json'
            }
        }

        try {
            const res = await axios.get('https://icanhazdadjoke.com/search', config);
            this.jokes = res.data.results;
            this.enableLoader = false;
        } catch (error) {
            console.error(error);
        }
    },
    head() {
        return {
            title: 'Dad Jokes',
            meta: [
                {
                    hid: "description",
                    name: "description",
                    content: "Best place for dad jokes"
                }
            ]
        }
    },
    methods: {
        async searchText(text) {
            if(text) {
                this.jokes = [];
                this.enableLoader = true;
                const config = {
                            headers: {
                                'Accept': 'application/json'
                            }
                        }

                try {
                    const res = await axios.get(`https://icanhazdadjoke.com/search?term=${text}`, config);
                    this.jokes = res.data.results;
                    this.enableLoader = false;
                } catch (error) {
                    console.error(error);
                }
            }
        }
    }
}
</script>