<script>
    import { onMount } from 'svelte';
    import mapboxgl from 'mapbox-gl';
    import "mapbox-gl/dist/mapbox-gl.css";
    import iconHospital from '$lib/assets/hospital.svg'; // ensure this path is correct

    // MAPBOX_TOKEN from .env
    mapboxgl.accessToken = import.meta.env.VITE_MAPBOX_TOKEN;

    let map;

    onMount(() => {
        map = new mapboxgl.Map({
            container: 'map',
            style: 'mapbox://styles/mapbox/light-v10',
            center: [24.031111, 49.841944], // coordinates of Lviv, Ukraine
            zoom: 13
        });

        // Add a marker to the map for the clinic
        function createMarker(lngLat) {
            const el = document.createElement('div');
            el.className = 'marker';
            el.style.backgroundImage = `url(${iconHospital})`;
            el.style.width = '50px';
            el.style.height = '50px';
            el.style.backgroundSize = 'cover';
            el.style.borderRadius = '50%';
            el.style.backgroundColor = 'white';
            el.style.backgroundSize = '50%';
            el.style.backgroundPosition = 'center';
            el.style.backgroundRepeat = 'no-repeat';
            el.style.cursor = 'pointer';

            const popup = new mapboxgl.Popup({ offset: 25 })
                .setHTML('<h3>VitalityCare Clinic</h3>')
                .setMaxWidth("250px");

            const marker = new mapboxgl.Marker(el)
                .setLngLat(lngLat)
                .setPopup(popup)
                .addTo(map);

            el.addEventListener('click', () => {
                marker.togglePopup();
            });
        }

        [[24.031111, 49.841944], [24.041111, 49.841944]].map(createMarker);
    });

    function toggleList() {
        // Logic to toggle the list view
    }
</script>

<style>
    #map {
        width: 100%;
        height: 100vh;
    }

    .marker {
        background-image: url('$lib/assets/hospital.svg'); /* Replace with the actual path to your icon */
        background-size: cover;
        width: 50px;
        height: 50px;
        border-radius: 50%;
        cursor: pointer;
    }

    .list-button {
        position: absolute;
        bottom: 20px;
        right: 20px;
        z-index: 1;
        background: #fff;
        border: none;
        padding: 10px 20px;
        border-radius: 20px;
        font-size: 16px;
        cursor: pointer;
    }

    /* Popup styling */
    .mapboxgl-popup {
        font-family: Arial, sans-serif;
        font-size: 12px;
        padding: 10px;
    }
</style>

<div id="map"></div>
<button class="list-button" on:click={toggleList}>List</button>

<!--<script>-->
<!--    import { onMount } from 'svelte';-->
<!--    import mapboxgl from 'mapbox-gl';-->
<!--    import "mapbox-gl/dist/mapbox-gl.css"-->

<!--    // Your Mapbox access token-->
<!--    mapboxgl.accessToken = 'pk.eyJ1IjoidW5kcmZpbmVkIiwiYSI6ImNscGE0c2NrazAzYWQya25rbXlheWNucTkifQ.dmjp-rr6QooNA80NrRfZfw';-->

<!--    onMount(() => {-->
<!--        const map = new mapboxgl.Map({-->
<!--            container: 'map', // container ID-->
<!--            style: 'mapbox://styles/mapbox/light-v10', // style URL-->
<!--            center: [24.031111, 49.841944], // starting position [lng, lat]-->
<!--            zoom: 12 // starting zoom-->
<!--        });-->

<!--        // Add markers to the map (example for one marker)-->
<!--        new mapboxgl.Marker()-->
<!--            .setLngLat([24.031111, 49.841944])-->
<!--            .addTo(map);-->

<!--        // Add more markers based on your data-->

<!--        // Add popup logic here-->
<!--    });-->
<!--</script>-->

<!--<style>-->
<!--    #map {-->
<!--        width: 100%;-->
<!--        height: 100vh;-->
<!--    }-->

<!--    .map-overlay {-->
<!--        position: absolute;-->
<!--        top: 0;-->
<!--        left: 0;-->
<!--        width: 100%;-->
<!--        padding: 20px;-->
<!--        box-sizing: border-box;-->
<!--        z-index: 10;-->
<!--    }-->

<!--    /* Add styles for the overlay elements, search bar, list button, etc. */-->
<!--</style>-->

<!--<div class="map-overlay">-->
<!--    &lt;!&ndash; Add your search bar, list button, and other UI elements here &ndash;&gt;-->
<!--</div>-->
<!--<div id="map"></div>-->
