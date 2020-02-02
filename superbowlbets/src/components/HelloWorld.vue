<template>
    <div class="hello">
        <h1>{{ msg }}</h1>
        <div class="custom-control custom-switch">
            <!--            <input type="checkbox" v-model="" class="custom-control-input" id="safety">-->
            <!--            <label class="custom-control-label" for="safety"></label>-->
        </div>
        {{ cond.safety.status }}
        {{ cond.safety.label }}
        {{ totalScore }}
    </div>
</template>

<script>
    export default {
        name: 'HelloWorld',
        props: {
            msg: String,
        },
        data: {
            cond: {
                "overtime": {
                    "status": false,
                    "label": "Goes to overtime"
                },
                "safety": {
                    "status": false,
                    "label": "Safety"
                },
                "koreturn": {
                    "status": false,
                    "label": "Kickoff return TD"
                },
                "preturn": {
                    "status": false,
                    "label": "Punt return TD"
                },
                "missedxp": {
                    "status": false,
                    "label": "Missed Extra Point Kick After TD"
                },
                "2pc": {
                    "status": false,
                    "label": "Successful 2-point conversion"
                },
                "bothteamlead4q": {
                    "status": false,
                    "label": "Both teams lead in 4q"
                }
            },
            "Q1": Number,
            "Q2": Number,
            "Q3": Number,
            "Q4": Number
        },
        computed: {
            totalScore: function () {
                return this.Q1 + this.Q2
            }
        }
    }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
    @import "~bootstrap/scss/bootstrap";

    h3 {
        margin: 40px 0 0;
    }

    ul {
        list-style-type: none;
        padding: 0;
    }

    li {
        display: inline-block;
        margin: 0 10px;
    }

    a {
        color: #42b983;
    }
</style>
