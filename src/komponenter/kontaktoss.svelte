<script>
    import Main from "./main.svelte";

	let visning;

	function sidevisning(side) {
		visning = side;
        alert("Meldingen ble sendt! Trykk på OK for å gå tilbake til hovedsiden")
    }

</script>

<main>
    <form on:submit="{() => sidevisning('Main')}">
        <div class="skjema">
            <label class="label" for="navn">Navn:</label>
            <input class="input" type="text" required placeholder="John">
            <br>
            <br>
            <label class="label" for="etternavn">Etternavn:</label>
            <input class="input" type="text" required placeholder="Appleseed">
            <br>
            <br>
            <label class="label" for="epost">Epost:</label>
            <input class="input" type="text" required placeholder="eksempel@gmail.com">
            <br>
            <br>
            <label class="label" for="melding">Melding:</label>
            <textarea class="input2" type="text" id="melding" required placeholder="Lorem ipsum dolor sit amet, consecteur adipiscing elit..."></textarea>
            <br>
            <br>
            <button type="submit" class="submit">Send</button>
        </div>
    </form>
</main>

<style>
    .skjema {
        background-color: #f3f3f3;
        padding: 30px;
        flex-direction: column;
    }

    .label {
        padding: 5px;
    }

    .input {
        width: 200px;
        border: 1px solid orange;
    }

    .input2 {
        border: 1px solid orange;
    }

    #melding {
        height: 200px;
        width: 100vh;
    }

    .submit {
        padding: 10px;
        text-align: center;
        width: 200px;
        font-size: 1.5rem;
        border-radius: 10px;
        border: 1px solid orange;
    }

    .submit:hover {
        cursor: pointer;
        background-color: lightgray;
    }

</style>