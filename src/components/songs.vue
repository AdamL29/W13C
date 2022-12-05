<template>
    <div>
        <button>Playlist</button>
        <article></article>
        <playList/>
    </div>
</template>

<script>
import playList from './playlist.vue';
    export default {
        components: {
            playList,
        },
        name: "songList",
        data(){
            return{
                inPlaylist: false,
                songs: [
                    `Numb`, 
                    `Everyone's Working for the Weekend`,
                    `Sandstorm`,
                    `Eye of the Tiger`
                ],
                artists:[
                    `Linkin Park`,
                    `Loverboy`,
                    `Darude`,
                    `Survivor`
                ]
            }
        },
        methods: {
            moveList(){
                if(this.inPlaylist){
                    document.addEventListener(`click`, this.songs)
                }
            },
            pushList() {
                console.log("it moves");
            },
            listSongs(){
                for (let song of this.songs){
                    document.querySelector(`article`).insertAdjacentHTML(`beforeend`, `<p>${song}</p>`)
                }
            }
        },
        mounted () {
            document.querySelector(`button`).addEventListener(`click`, this.pushList);
            this.listSongs();
        },
    }
</script>

<style scoped>

</style>