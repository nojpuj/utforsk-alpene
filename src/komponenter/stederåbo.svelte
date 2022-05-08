<script>

</script>

<main>
    <h2 class="hbox-header">Hotell i Alpene</h2>
    <div class="label-box"><img class="label" src="orangeline.png" alt="oransj label"></div>
    <br>
        <div class="canvas">
            <iframe width="1080" height="800" id="gmap_canvas" src="https://maps.google.com/maps?q=Hotel%20Soelden&t=&z=15&ie=UTF8&iwloc=&output=embed" frameborder="0" scrolling="no" marginheight="0" marginwidth="0" title="maps"></iframe>
        </div>
    <br>
</main>

<style>
    main {
		text-rendering: optimizeLegibility;
		scroll-behavior: smooth;
    }

    .canvas {
        display: flex;
        justify-content: center;
        height: 800px;
        width: 1080px;
    }

    .hbox-header {
        text-align: center;
        font-size: 2rem;
    }

    #gmap_canvas {
        position: absolute;
        margin-left: 50%;
        margin-right: 37%;
    }

    .label {
        width: 215px;
        height: 20px;
        padding: 0px;
    }

    .label-box {
        display: flex;
        justify-content: center;
        margin-top: -25px;
    }

    iframe {
        border: 2px solid orange;
    }

</style>