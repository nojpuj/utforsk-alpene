<script>
    import { fade } from 'svelte/transition';

    let bilder = [{src: "/images/austria.jpg", alt: "austria", tittel: "Østerrike"}, {src: "/images/france.jpg", alt: "france", tittel: "Frankrike"}, {src: "/images/germany.jpg", alt: "germany", tittel: "Tyskland"}, {src: "/images/italy.jpg", alt: "italy", tittel: "Italia"}, {src: "/images/slovenia.jpg", alt: "slovenia", tittel: "Slovenia"}, {src: "/images/swiss.jpeg", alt: "swiss", tittel: "Sveits"}]
    let bilder2 = [{src: "/images/zermatt.jpg", alt: "zermatt", tittel: "Zermatt"}, {src: "/images/courchevel.jpg", alt: "courchevel", tittel: "Courchevel"}, {src: "/images/cortina.jpg", alt: "cortina d'ampezzo", tittel: "Cortina D'Ampezzo"}, {src: "/images/madonna.jpg", alt: "madonna di campiglio", tittel: "Madonna di Campiglio"}, {src: "/images/chamonix.jpeg", alt: "chamonix", tittel: "Chamonix"}, {src: "/images/kitzbühel.jpg", alt: "kitzbühel", tittel: "Kitzbühel"}, {src: "/images/meribel.png", alt: "meribel", tittel: "Meribel"}, {src: "/images/soelden.jpg", alt: "soelden", tittel: "Soelden"},]

    let index = 0;
    let index2 = 0;
    let tittel = bilder[index].tittel
    let tittel2 = bilder2[index].tittel
    let kilde = bilder[index].src
    let kilde2 = bilder2[index].src

    function neste() {
        index += 1;
        if (index == bilder.length) {
            index = 0;
        }
        kilde = bilder[index].src
        tittel = bilder[index].tittel
    }

    function forrige() {
        index -= 1;
        if (index < 0) {
            index = (bilder.length - 1)
        }
        kilde = bilder[index].src
        tittel = bilder[index].tittel
    }
    
    function neste2() {
        index2 += 1;
        if (index2 == bilder2.length) {
            index2 = 0;
        }
        kilde2 = bilder2[index2].src
        tittel2 = bilder2[index2].tittel
    }

    function forrige2() {
        index2 -= 1;
        if (index2 < 0) {
            index2 = (bilder2.length - 1)
        }
        kilde2 = bilder2[index2].src
        tittel2 = bilder2[index2].tittel
    }

</script>

<main>
    <h2 class="hbox-header">Steder å besøke</h2>
    <div class="label-box"><img class="label" src="orangeline.png" alt="oransj label"></div>
    <h3 class="tittel">{tittel}</h3>
    <div class="hoved-box">
        <button on:click="{forrige}">Forrige</button>
        <div><img class="bilder" src="{kilde}" alt="steder å besøke"></div>
        <button on:click="{neste}">Neste</button>
    </div>
    <h2 class="hbox-header">Beste skianlegg</h2>
    <div class="label-box"><img class="label" src="orangeline.png" alt="oransj label"></div>
    <h3 class="tittel">{tittel2}</h3>
    <div class="hoved-box">
        <button on:click="{forrige2}">Forrige</button>
        <div><img class="bilder" src="{kilde2}" alt="skianlegg"></div>
        <button  on:click="{neste2}">Neste</button>
    </div>
    <br>
</main>

<style>
    main {
		text-rendering: optimizeLegibility;
		scroll-behavior: smooth;
    }

    .hoved-box {
        display: flex;
        justify-content: center;
    }

    .hbox-header {
        text-align: center;
        font-size: 2rem;
    }

    .tittel {
        text-align: center;
        font-size: 1.5rem;
    }

    .bilder {
        object-fit: cover;
        height: 80vh;
        width: 180vh;
    }

    button {
        padding: 1rem;
        height: 80vh;
    }

    .label {
        width: 230px;
        height: 20px;
        padding: 0px;
    }

    .label-box {
        display: flex;
        justify-content: center;
        margin-top: -25px;
    }

</style>