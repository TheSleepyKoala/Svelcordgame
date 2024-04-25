<script lang="ts">
    import { onMount } from "svelte";
    import { DiscordHelper } from "$lib/utils/DiscordHelper";
    import { config } from "$lib/config";

    let canvas: any;
    let discordHelper: DiscordHelper;

    onMount(() => {
        discordHelper = new DiscordHelper();
        discordHelper.setupParentIframe();
        initializeGameMaker();
    });

    function initializeGameMaker() {
        // Load the GameMaker HTML5 engine script
        const script = document.createElement("script");
        script.src = "html5game/" + config.PRODUCT_NAME + ".js";
        script.onload = () => {
            window.onload = GameMaker_Init;
        };

        document.body.appendChild(script);

        if (/iPhone|iPad|iPod|Android/i.test(navigator.userAgent)) {
            // Mobile device style: fill the whole browser client area with the game canvas:
            var meta = document.createElement("meta");
            meta.name = "viewport";
            meta.content =
                "width=device-width, height=device-height, initial-scale=1.0, user-scalable=no, shrink-to-fit=yes";
            document.getElementsByTagName("head")[0].appendChild(meta);

            canvas = document.querySelector("#canvas");
            canvas.style.width = "100%";
            canvas.style.height = "100%";
            canvas.style.position = "fixed";
            document.body.style.textAlign = "left";
        }
    }
</script>

<body>
    <div class="gm4html5_div_class" id="gm4html5_div_id">
        <canvas
            bind:this={canvas}
            id="canvas"
            width="1920"
            height="1080"
            style="
            width: 100vw;
            height: 100vh;
            background: url('html5game/splash.png') center / cover;
            "
        >
            <p>Your browser doesn't support HTML5 canvas.</p>
        </canvas>
    </div>
</body>

<style>
    body {
        margin: 0px;
        background-color: #000000;
        padding: 0px;
        text-align: center;
        border: 0;
        height: 100vh;
        width: 100vw;
        overflow: hidden;
    }
</style>
