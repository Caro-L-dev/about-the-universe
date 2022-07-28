<template>
    <div class="card sticky flex tall">
        <div class="card-header">
            <h2 class="title text-primary">Planètes</h2>
            <div class="form-group">
                <select class="select pr-5" @change="filterByGender($event)">
                    <option value="">Par population</option>
                    <option value="0">0 à 100.000</option>
                    <option value="1">0 à 100.000.000</option>
                    <option value="2">+ de 100.000.000</option>
                </select>
            </div>
            <div class="form-group">
                <div class="form-group form-group-search">
                    <input type="text" class="form-control searchbar" id="searchbar"
                        placeholder="Faites votre recherche" />
                    <span class="fas fa-search icon"></span>
                </div>
            </div>
        </div>

        <div class="table" v-if="planets">
            <table>
                <thead>
                    <tr>
                        <th>Nom</th>
                        <th>Terrain</th>
                    </tr>
                </thead>
                <tbody>
                    <tr v-for="p in planets" v-bind:key="p.name" @click="showPresentation(p)">
                        <td>{{ p.name }}</td>
                        <td>{{ p.terrain }}</td>
                    </tr>
                </tbody>
            </table>
        </div>
        <div class="card-footer">
            <div class="medium-information mt-5">
                <span class="info">{{ planets.length }} resultat(s)</span>
            </div>
        </div>
    </div>
</template>

<script>
//import axios from 'axios';

export default {
    name: 'AppListPlanets',
    data() {
        return {
            planets: [],
            planetsSaved: []
        }
    },
    methods: {
        showPresentation(p) {
            this.$emit('presentation-planet', p);
        },
        filterByGender(event) {
            this.planets = this.planetsSaved;
            if (event.target.value === '0') {
                this.planets = this.planets.filter(p => p.population !== 'unknown' && Number(p.population) < 100000);
            } else if (event.target.value === '1') {
                this.planets = this.planets.filter(p => p.population !== 'unknown' && Number(p.population) > 100000 && Number(p.population) < 100000000);
            } else if (event.target.value === '2') {
                this.planets = this.planets.filter(p => p.population !== 'unknown' && Number(p.population) > 100000000);
            } else {
                this.planets = this.planetsSaved;
            }
        }
    },
    mounted() {
        for (let i = 1; i < 7; i++) {
            // axios.get(`https://swapi.dev/api/planets/?page=${i}`)
            //     .then(response => {
            //         response.data.results.forEach(item => {
            //             this.planets.push(item)
            //         })
            //         this.planetsSaved = this.planets;
            //     })
        }
    }
}
</script>

<style scoped >

</style>

