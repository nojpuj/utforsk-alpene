<script>
    let bilder = [{src: "/images/skiing.jpg", alt: "stå på ski", tittel: "Shredde bakker"}, {src: "/images/hiking.jpg", alt: "hiking", tittel: "Ta en passe krevende fjelltur"}, {src: "/images/dogsledding.jpg", alt: "hundekjøring", tittel: "Bli dratt av søte hunder på slede"}, {src: "/images/glacier.jpg", alt: "vandring inne i en bre", tittel: "Vandre i titusen år gamle isbreer"}, {src: "/images/paragliding.jpg", alt: "paragliding", tittel: "Oppleve fuglefølelsen"}, {src: "/images/hottubs.jpg", alt: "boblebad", tittel: "Ta et koselig varmt boblebad i det kalde været"},]

    let index = 0;
    let kilde = bilder[index].src
    let tittel = bilder[index].tittel

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

</script>

<main>
    <h2 class="hbox-header">Hva skal man gjøre?</h2>
    <div class="label-box"><img class="label" src="orangeline.png" alt="oransj label"></div>
    <h3 class="tittel">{tittel}</h3>
    <div class="hoved-box">
        <button on:click="{forrige}">Forrige</button>
        <div><img class="bilder" src="{kilde}" alt="steder å besøke"></div>
        <button on:click="{neste}">Neste</button>
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

    .bilder {
        object-fit: cover;
        height: 80vh;
        width: 180vh;
    }

    button {
        padding: 1rem;
        height: 80vh;
    }

    .tittel {
        text-align: center;
        font-size: 1.5rem;
    }

    .label {
        width: 285px;
        height: 20px;
        padding: 0px;
    }

    .label-box {
        display: flex;
        justify-content: center;
        margin-top: -25px;
    }

</style>