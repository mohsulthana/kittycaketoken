<template>
    <v-app id="app">
        <navigation :color="color" :flat="flat" />
        <v-main class="pt-0">
            <home />
            <about />
            <features />
            <product-roadmap />
            <buy />
            <faq />
            <partners />
        </v-main>
        <v-scale-transition>
            <v-btn
                fab
                v-show="fab"
                v-scroll="onScroll"
                dark
                fixed
                bottom
                right
                color="secondary"
                @click="toTop"
            >
                <v-icon>mdi-arrow-up</v-icon>
            </v-btn>
        </v-scale-transition>
        <foote />
    </v-app>
</template>

<style>
#app {
background: linear-gradient(179.94deg, rgba(106, 0, 108, 0.9) 16.15%, rgba(45, 0, 102, 0.7) 38.81%, rgba(0, 6, 60, 0.9) 89.43%, #797EB1 100.34%, rgba(2, 4, 26, 0.72) 100.34%, #130022 100.34%);
    background-blend-mode: multiply;
    backdrop-filter: blur(100px);
}
.theme--light.v-expansion-panels
    .v-expansion-panel-header
    .v-expansion-panel-header__icon
    .v-icon {
    color: white;
}
</style>

<script>
import navigation from "./components/Navigation";
import foote from "./components/Footer";
import home from "./components/HomeSection";
import about from "./components/AboutSection";
import features from "./components/FeaturesSection";
import partners from "./components/PartnersSection";
import buy from "./components/BuySection";
import faq from "./components/FAQSection";
import ProductRoadmap from "./components/ProductRoadmap.vue";

export default {
    name: "App",

    components: {
        navigation,
        foote,
        home,
        features,
        about,
        partners,
        buy,
        faq,
        ProductRoadmap,
    },

    metaInfo: {
        title: "Kittycaketoken",
        meta: [
            { charset: "utf-8" },
            {
                name: "description",
                content: "KittyCake is an advanced hyper-deflationary auto-rewards token on the Binance Smart Chain.",
            },
            {
                name: "viewport",
                content: "width=device-width, initial-scale=1",
            },
        ],
    },

    data: () => ({
        fab: null,
        color: "",
        flat: null,
    }),

    created() {
        const top = window.pageYOffset || 0;
        if (top <= 60) {
            this.color = "transparent";
            this.flat = true;
        }
    },

    watch: {
        fab(value) {
            if (value) {
                this.color = "secondary";
                this.flat = false;
            } else {
                this.color = "transparent";
                this.flat = true;
            }
        },
    },

    methods: {
        onScroll(e) {
            if (typeof window === "undefined") return;
            const top = window.pageYOffset || e.target.scrollTop || 0;
            this.fab = top > 60;
        },
        toTop() {
            this.$vuetify.goTo(0);
        },
    },
};
</script>