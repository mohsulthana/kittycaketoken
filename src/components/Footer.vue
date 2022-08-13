<template>
    <v-footer dark>
        <v-container class="my-8">
            <v-row justify="end" align="start">
                <v-col sm="12" md="6">
                    <v-card
                        class="card-features"
                        :elevation="hover ? 10 : 4"
                        :class="[{ up: hover }, leftCardAlign]"
                        :width="`${width}%`"
                    >
                        <v-img
                            src="@/assets/img/twitter.png"
                            max-width="70px"
                            class="d-block mr-auto"
                        ></v-img>
                        <h1 class="font-weight-bold" style="color: #39a9da">
                            Stay up-to-date on Twitter!
                        </h1>
                        <v-btn block outlined rounded color="#39A9DA"
                            >Follow <v-icon>mdi-arrow-right</v-icon></v-btn
                        >
                    </v-card>
                </v-col>
                <v-col sm="12" md="6">
                    <v-card
                        class="card-features"
                        :elevation="hover ? 10 : 4"
                        :class="[{ up: hover }, rightCardAlign]"
                        :width="`${width}%`"
                    >
                        <v-img
                            src="@/assets/img/telegram.png"
                            max-width="70px"
                            class="d-block mr-auto"
                        ></v-img>
                        <h1 class="font-weight-bold" style="color: #38a1f2">
                            Join our Telegram Community!
                        </h1>
                        <v-btn block outlined rounded color="#38A1F2"
                            >Join <v-icon>mdi-arrow-right</v-icon></v-btn
                        >
                    </v-card>
                </v-col>
            </v-row>
        </v-container>
        <v-container>
            <v-row>
                <v-col class="text-center">
                    <p>Copyright @ Kittycaketoken 2022.</p>
                </v-col>
            </v-row>
        </v-container>
    </v-footer>
</template>

<style scoped>
.card-features {
    padding: 24px;
    gap: 12px;
    transition: 0.5s ease-out;
    background: rgba(255, 255, 255) !important;
    box-shadow: 15px -15px 0px #f64d95;
    border-radius: 20px !important;
}
.card-features .v-image {
    margin-bottom: 15px;
    transition: 0.75s;
}

.card-features h1 {
    margin-bottom: 10px;
}

.zoom-efect {
    transform: scale(1.1);
}

.up {
    transform: translateY(-20px);
    transition: 0.5s ease-out;
}
</style>

<script>
export default {
    data: () => ({}),
    computed: {
        width() {
            switch (this.$vuetify.breakpoint.name) {
                case "xs":
                    return 100;
                case "sm":
                    return 100;
                case "md":
                    return 60;
                case "lg":
                    return 60;
                case "xl":
                    return 60;
            }
        },
        leftCardAlign() {
            switch (this.$vuetify.breakpoint.name) {
                case "xs":
                    return 'mx-auto';
                case "sm":
                    return 'mx-auto';
                case "md":
                    return 'ml-auto';
                case "lg":
                    return 'ml-auto';
                case "xl":
                    return 'ml-auto';
            }
        },
        rightCardAlign() {
            switch (this.$vuetify.breakpoint.name) {
                case "xs":
                    return 'mx-auto';
                case "sm":
                    return 'mx-auto';
                case "md":
                    return 'mr-auto';
                case "lg":
                    return 'mr-auto';
                case "xl":
                    return 'mr-auto';
            }
        }
    },
};
</script>
