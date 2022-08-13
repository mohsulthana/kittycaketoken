<template>
    <section id="partners">
        <v-container fluid>
            <h1 class="display-3 text-center white--text font-weight-bold">
                Our Partners
            </h1>
            <v-row align="center" justify="center" style="padding-top: 40px">
                <v-col>
                    <v-sheet class="mx-auto" max-width="1200">
                        <v-slide-group multiple show-arrows>
                            <v-slide-item
                                v-for="(partner, index) in partners"
                                :key="index"
                            >
                                <img
                                    :src="partner.image"
                                    :alt="partner.name"
                                    style="max-height: 64px; margin: 0 16px"
                                />
                            </v-slide-item>
                        </v-slide-group>
                    </v-sheet>
                </v-col>
            </v-row>
        </v-container>
    </section>
</template>

<style scoped>
#partners {
    background: rgba(255, 255, 255, 0.13);
    backdrop-filter: blur(100px);
    border-radius: 40px 40px 0px 0px;
    padding: 80px 0;
}
.theme--light.v-sheet {
    background-color: transparent;
}
.v-icon.notranslate.mdi.mdi-chevron-right.theme--light {
    color: white !important;
}
</style>

<script>
export default {
    data: () => ({
        partners: [
            {
                name: "blockfolio",
                image: require("@/assets/img/partners/blockfolio.png"),
            },
            {
                name: "coingecko",
                image: require("@/assets/img/partners/coingecko.png"),
            },
            {
                name: "indoe",
                image: require("@/assets/img/partners/indoe.png"),
            },
            {
                name: "coinmarket",
                image: require("@/assets/img/partners/coinmarket.png"),
            },
        ],
    }),
    computed: {
        size() {
            const size = { md: "large", xl: "x-large" }[
                this.$vuetify.breakpoint.name
            ];
            return size ? { [size]: true } : {};
        },
    },
};
</script>