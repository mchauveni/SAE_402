<script>
    import Footer from "/src/lib/Footer.svelte";
    import Header from "/src/lib/Header.svelte";
    import { locationButtonClick } from "/src/scripts/places.ts";
    import "/src/scripts/map.ts";

    import placeIcon from "/src/assets/img/icons/place.svg";
    import distanceIcon from "/src/assets/img/icons/distance.svg";
    import playIcon from "/src/assets/img/icons/play.svg";
</script>

<Header />
<main class="main">
    <h1 class="main__title">Autour de vous</h1>
    <button class="main__locate" id="askButton" on:click={locationButtonClick()}> Activer la localisation </button>
    <section class="maps">
        <div id="map" class="maps__iframe" />
        <div class="popup">
            <svg class="close" viewBox="0 0 20 20">
                <path d="M10.185,1.417c-4.741,0-8.583,3.842-8.583,8.583c0,4.74,3.842,8.582,8.583,8.582S18.768,14.74,18.768,10C18.768,5.259,14.926,1.417,10.185,1.417 M10.185,17.68c-4.235,0-7.679-3.445-7.679-7.68c0-4.235,3.444-7.679,7.679-7.679S17.864,5.765,17.864,10C17.864,14.234,14.42,17.68,10.185,17.68 M10.824,10l2.842-2.844c0.178-0.176,0.178-0.46,0-0.637c-0.177-0.178-0.461-0.178-0.637,0l-2.844,2.841L7.341,6.52c-0.176-0.178-0.46-0.178-0.637,0c-0.178,0.176-0.178,0.461,0,0.637L9.546,10l-2.841,2.844c-0.178,0.176-0.178,0.461,0,0.637c0.178,0.178,0.459,0.178,0.637,0l2.844-2.841l2.844,2.841c0.178,0.178,0.459,0.178,0.637,0c0.178-0.176,0.178-0.461,0-0.637L10.824,10z" />
            </svg>
            <img class="popup__img" id="popup_img" alt="" />
            <div class="popup__txt">
                <p class="popup__txt--title" />
                <div class="popup__txt--place">
                    <img src={placeIcon} alt="" />
                    <h3 id="place" />
                </div>
                <div class="popup__txt--trajet">
                    <img src={distanceIcon} alt="" />
                    <h3 id="distance" />
                </div>
                <div class="popup__txt--btn">
                    <a href="#"> En savoir +</a>
                    <img src={playIcon} alt="" />
                </div>
            </div>
        </div>
    </section>
</main>
<Footer active="map" />
