<template>
    <div>
        <button>Playlist</button>
        <article></article>
        <playList/>
        <h4></h4>
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
                    document.querySelector(`p`).style.color = `blue`;
                }else{
                    document.querySelector(`p`).style.color = `red`;
                }
                this.inPlaylist = !this.inPlaylist;
            },
            pushList() {
                document.querySelector(`article`).insertAdjacentHTML(`beforeend`, '<h3>${this.songs}</h3>');
                console.log("it moves");
            },
            listSongs(){
                let artTag = document.querySelector(`article`)
                for (let song of artTag){
                    song.addEventListener(`click`, this.pushList);
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