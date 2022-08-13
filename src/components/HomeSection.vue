<template>
    <section id="hero">
        <v-parallax dark src="@/assets/img/bghero1.jpg" height="850">
            <v-row align="center" justify="center">
                <v-col cols="10">
                    <v-row align="center" justify="center">
                        <v-col cols="12" md="6" xl="8">
                            <h1 class="display-2 font-weight-bold mb-4">
                                Hold KittyCake. <br />
                                Earn passive income paid in Cake.
                            </h1>
                            <v-btn
                                color="primary"
                                rounded
                                large
                                @click="$vuetify.goTo('#features')"
                                class="mt-5"
                            >
                                Connect Wallet <v-icon color="white">mdi-plus</v-icon>
                            </v-btn>
                            <v-btn
                                color="white"
                                rounded
                                large
                                text
                                @click="$vuetify.goTo('#features')"
                                class="mt-5"
                            >
                                Buy KittyCake
                            </v-btn>
                        </v-col>
                        <v-col
                            cols="12"
                            md="6"
                            xl="4"
                            class="hidden-sm-and-down"
                        >
                        </v-col>
                    </v-row>
                </v-col>
            </v-row>
        </v-parallax>
    </section>
</template>

<script>
export default {
    data() {
        return {
            dialog: false,
            videoId: "i8IvvHJssWE",
        };
    },
    watch: {
        dialog(value) {
            if (!value) {
                this.pause();
            }
        },
    },
    methods: {
        ready(event) {
            this.player = event.target;
        },
        playing(event) {
            // The player is playing a video.
        },
        change() {
            // when you change the value, the player will also change.
            // If you would like to change `playerVars`, please change it before you change `videoId`.
            // If `playerVars.autoplay` is 1, `loadVideoById` will be called.
            // If `playerVars.autoplay` is 0, `cueVideoById` will be called.
            this.videoId = "another video id";
        },
        stop() {
            this.player.stopVideo();
        },
        pause() {
            this.player.pauseVideo();
        },
    },
};
</script>

<style lang="scss">
.circle {
    stroke: white;
    stroke-dasharray: 650;
    stroke-dashoffset: 650;
    -webkit-transition: all 0.5s ease-in-out;
    opacity: 0.3;
}

.playBut {
    /*  border: 1px solid red;*/
    display: inline-block;
    -webkit-transition: all 0.5s ease;

    .triangle {
        -webkit-transition: all 0.7s ease-in-out;
        stroke-dasharray: 240;
        stroke-dashoffset: 480;
        stroke: white;
        transform: translateY(0);
    }

    &:hover {
        .triangle {
            stroke-dashoffset: 0;
            opacity: 1;
            stroke: white;
            animation: nudge 0.7s ease-in-out;

            @keyframes nudge {
                0% {
                    transform: translateX(0);
                }
                30% {
                    transform: translateX(-5px);
                }
                50% {
                    transform: translateX(5px);
                }
                70% {
                    transform: translateX(-2px);
                }
                100% {
                    transform: translateX(0);
                }
            }
        }

        .circle {
            stroke-dashoffset: 0;
            opacity: 1;
        }
    }
}
</style>

<style scoped>
.btn-play {
    transition: 0.2s;
}

.svg-border-waves .v-image {
    position: absolute;
    bottom: 0;
    left: 0;
    height: 3rem;
    width: 100%;
    overflow: hidden;
}

#hero {
    z-index: 0;
}
.svg-border-waves img {
    position: absolute;
    bottom: 0;
    left: 0;
    width: 100%;
    margin-bottom: -2px;
    z-index: -1;
}
</style>

<style>
section {
    position: relative;
}
</style>
