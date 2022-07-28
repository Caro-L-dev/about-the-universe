<template>
    <main class="container container-1-2">
        <app-list-planets @presentation-planet="setPlanet"></app-list-planets>
        <div>
            <div class="card info text-secondary" v-if="!planet">
                Sélectionner le contenu à afficher !
            </div>
            <div class="card" v-if="planet">
                <div class="information mb-5">
                    <div>
                        <h2 class="title text-secondary">{{ planet.name }}</h2>
                        <div class="info mb-3"><span class="text-secondary">Population :</span> {{ planet.population !==
                                'unknown' ? planet.population : 'Inconnu'
                        }}</div>
                    </div>
                </div>
                <div class="d-grid-2 mt-5 mb-5 w-100">
                    <div class="information">
                        <span class="far fa-circle fa-3x img text-secondary"></span>
                        <div>
                            <div class="bold text-secondary">
                                Diamètre
                            </div>
                            <p>{{ planet.diameter !== 'unknown' ? planet.diameter : 'Inconnu' }}</p>
                        </div>
                    </div>
                    <div class="information">
                        <span class="fas fa-thermometer-full fa-3x img text-secondary"></span>
                        <div>
                            <div class="bold text-secondary">
                                Climat
                            </div>
                            <p>{{ planet.climate !== 'unknown' ? planet.climate : 'Inconnu' }}</p>
                        </div>
                    </div>
                </div>
                <div class="d-grid-2 mt-5 mb-5 w-100">
                    <div class="information">
                        <span class="fas fa-magnet fa-3x img text-secondary"></span>
                        <div>
                            <div class="bold text-secondary">
                                Gravité
                            </div>
                            <div class="info">{{ planet.gravity !== 'unknown' ? planet.gravity : 'Inconnu' }}</div>
                        </div>
                    </div>
                    <div class="information">
                        <span class="fas fa-tree fa-3x img text-secondary"></span>
                        <div>
                            <div class="bold text-secondary">
                                Terrain
                            </div>
                            <div class="info">{{ planet.terrain !== 'unknown' ? planet.terrain : 'Inconnu' }}</div>
                        </div>
                    </div>
                </div>
                <div class="mt-5 d-flex right">
                    <div class="btn">En savoir plus</div>
                </div>
            </div>
        </div>
    </main>
</template>

<script>
import AppListPlanets from '@/components/AppListPlanets.vue';

export default {
    name: 'PresentationPlanet',
    data() {
        return {
            planet: false,
        }
    },
    methods: {
        setPlanet(p) {
            this.planet = p;
        },
    },
    components: { AppListPlanets },
}
</script>
