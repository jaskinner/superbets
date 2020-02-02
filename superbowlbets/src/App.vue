<template>
    <div id="app" class="container">
        <div class="row">
            <div class="col-6">
                <div class="row">
                    <div class="col-6 text-center p-5">
                        <img class="img-fluid" alt="Vue logo" src="https://www.miasbliv.com/images/liv.svg">
                    </div>
                    <div class="col-12">
                        <div class="custom-control custom-switch">
                            <input type="checkbox" v-model="cond.safety.status" class="custom-control-input"
                                   id="safety">
                            <label class="custom-control-label" for="safety">{{cond.safety.label}}</label>
                        </div>
                        <div class="custom-control custom-switch">
                            <input type="checkbox" v-model="cond.koreturn.status" class="custom-control-input"
                                   id="koreturn">
                            <label class="custom-control-label" for="koreturn">{{cond.koreturn.label}}</label>
                        </div>
                        <div class="custom-control custom-switch">
                            <input type="checkbox" v-model="cond.preturn.status" class="custom-control-input"
                                   id="preturn">
                            <label class="custom-control-label" for="preturn">{{cond.preturn.label}}</label>
                        </div>
                        <div class="custom-control custom-switch">
                            <input type="checkbox" v-model="cond.missedxp.status" class="custom-control-input"
                                   id="missedxp">
                            <label class="custom-control-label" for="missedxp">{{cond.missedxp.label}}</label>
                        </div>
                        <div class="custom-control custom-switch">
                            <input type="checkbox" v-model="cond.twopc.status" class="custom-control-input" id="twopc">
                            <label class="custom-control-label" for="twopc">{{cond.twopc.label}}</label>
                        </div>
                        <div class="custom-control custom-switch">
                            <input type="checkbox" v-model="cond.bothteamlead4q.status" class="custom-control-input"
                                   id="bothteamlead4q">
                            <label class="custom-control-label"
                                   for="bothteamlead4q">{{cond.bothteamlead4q.label}}</label>
                        </div>
                        <div class="custom-control custom-switch">
                            <input type="checkbox" v-model="cond.overtime.status" class="custom-control-input"
                                   id="overtime">
                            <label class="custom-control-label" for="overtime">{{cond.overtime.label}}</label>
                        </div>
                    </div>
                </div>
            </div>
            <div class="col-6 pt-5">
                <ul class="list-group">
                    <li class="list-group-item"
                        v-bind:class="{ 'list-group-item-success': cond.safety.status && cond.overtime.status }">
                        {{cond.safety.label + ' | ' + cond.overtime.label}}
                    </li>
                    <li class="list-group-item"
                        v-bind:class="{ 'list-group-item-success': cond.koreturn.status && cond.overtime.status }">
                        {{cond.koreturn.label + ' | ' + cond.overtime.label}}
                    </li>
                    <li class="list-group-item"
                        v-bind:class="{ 'list-group-item-success': cond.preturn.status && cond.overtime.status }">
                        {{cond.preturn.label + ' | ' + cond.overtime.label}}
                    </li>
                    <li class="list-group-item"
                        v-bind:class="{ 'list-group-item-success': cond.safety.status && cond.koreturn.status }">
                        {{cond.safety.label + ' | ' + cond.koreturn.label}}
                    </li>
                    <li class="list-group-item"
                        v-bind:class="{ 'list-group-item-success': cond.safety.status && cond.preturn.status }">
                        {{cond.safety.label + ' | ' + cond.preturn.label}}
                    </li>
                    <li class="list-group-item"
                        v-bind:class="{ 'list-group-item-success': cond.missedxp.status && cond.koreturn.status }">
                        {{cond.missedxp.label + ' | ' + cond.koreturn.label}}
                    </li>
                    <li class="list-group-item"
                        v-bind:class="{ 'list-group-item-success': cond.twopc.status && cond.preturn.status }">
                        {{cond.twopc.label + ' | ' + cond.preturn.label}}
                    </li>
                    <li class="list-group-item"
                        v-bind:class="{ 'list-group-item-success': cond.bothteamlead4q.status && cond.koreturn.status }">
                        {{cond.bothteamlead4q.label + ' | ' + cond.koreturn.label}}
                    </li>
                    <li class="list-group-item"
                        v-bind:class="{ 'list-group-item-success': cond.missedxp.status && cond.preturn.status }">
                        {{cond.missedxp.label + ' | ' + cond.preturn.label}}
                    </li>
                    <li class="list-group-item"
                        v-bind:class="{ 'list-group-item-success': cond.twopc.status && cond.koreturn.status }">
                        {{cond.twopc.label + ' | ' + cond.koreturn.label}}
                    </li>
                    <li class="list-group-item"
                        v-bind:class="{ 'list-group-item-success': cond.bothteamlead4q.status && cond.preturn.status }">
                        {{cond.bothteamlead4q.label + ' | ' + cond.preturn.label}}
                    </li>
                </ul>

                <!--                <button v-on:click="addTD">Add TD</button>-->

                <!--                <ul class="list-group">-->
                <!--                    <li class="list-group-item" v-for="tdval in tdList">-->
                <!--                        {{tdval.quarter}}-->
                <!--                        {{tdval.FG}}-->
                <!--                        {{tdval.XP}}-->
                <!--                    </li>-->
                <!--                </ul>-->
            </div>
        </div>
    </div>
</template>

<script>
    // import HelloWorld from './components/HelloWorld.vue'

    export default {
        name: 'app',
        // components: {
        //     HelloWorld
        // },
        data() {
            return {
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
                    "twopc": {
                        "status": false,
                        "label": "Successful 2-point conversion"
                    },
                    "bothteamlead4q": {
                        "status": false,
                        "label": "Both teams lead in 4q"
                    }
                },
                "td": {
                    "quarter": 0,
                    "team": null,
                    "FG": false,
                    "XP": false
                },
                "tdList": []
            }
        },
        computed: {
            totalScore: function () {
                // return Number(this.Q1) + Number(this.Q2) + Number(this.Q3) + Number(this.Q4)
            },
            quarterTotals: function () {

            }
        },
        methods: {
            addTD: function () {
                let newTD = this.td;
                // newTD.quarter =
            },
        }
    }
</script>

<style lang="scss">
    @import "~bootstrap/scss/bootstrap";


</style>
