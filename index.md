---
title: Cosmic Horizons Wiki
subtitle: The wiki for the Cosmic Horizons mod
layout: page
hero_tag: true
hero_tag_class: is-large is-danger 
hero_tag_text: "Warning: This mod is in alpha"
---

# A brand new Minecraft space mod!

This mod adds many new planets, moons and even solar systems!

<style>

      

      body {

        overflow: hidden;

        width: 100%;

        height: 100%;

        margin: 0;

        padding: 0;

      }



      #renderCanvas {

        width: 10%;

        height: 10%;

        touch-action: none;

      }

    </style>



<script src="https://cdn.babylonjs.com/babylon.js"></script>

<script src="https://cdn.babylonjs.com/loaders/babylonjs.loaders.min.js"></script>

<script src="https://code.jquery.com/pep/0.4.3/pep.js"></script>






<canvas class="card" id="renderCanvas" touch-action="none"></canvas>





<script>

      const canvas = document.getElementById("renderCanvas"); // Get the canvas element

      const engine = new BABYLON.Engine(canvas, true); // Generate the BABYLON 3D engine



      // Add your code here matching the playground format

      const createScene = function () {

        const scene = new BABYLON.Scene(engine);



        BABYLON.MeshBuilder.CreateBox("box", {});



        const camera = new BABYLON.ArcRotateCamera("camera", -Math.PI / 2, Math.PI / 2.5, 15, new BABYLON.Vector3(0, 0, 0));

        camera.attachControl(canvas, true);

        const light = new BABYLON.HemisphericLight("light", new BABYLON.Vector3(1, 1, 0));



        return scene;

      };



      const scene = createScene(); //Call the createScene function



      // Register a render loop to repeatedly render the scene

      engine.runRenderLoop(function () {

        scene.render();

      });



      // Watch for browser/canvas resize events

      window.addEventListener("resize", function () {

        engine.resize();

      });

</script>



MOD STAGE : Very Alpha (can be only played in creative mode)

For questions and help, join out [discord](https://discord.gg/cdc6sgEExF)!

## Galactic Expansion

This mod uses its very own render system, bringing space to life...

Players can now visit planets in a spaceship, and feel the incredible
expanse of space even on lower end PCs thanks to this mods optimisations!

This mod renders planets even outside of render distance, and can even
be played with other performance enhancing mods like sodium!

*Make sure to take a look at the gallery!*

## Planetary Exploration

The mod also adds its own gravity system, and adds dimensions
for all planets, all very rich with minerals and new blocks.

## Technological Expansion

The mod provides various new blocks with interactive Guis, 
as well as its own electricity system and metal progressions.

## Exploration

The mod also adds its own way to travel to space, using a spaceship
which can be upgraded to survive in diffente conditions and go faster.

## Multiplayer Compatibility

The mod also supports multiplayer gameplay, allowing players to embark
on space adventures together and explore the cosmos as a team.

## Datapack Support

The mod comes with datapack support, allowing people to make their own 
solar systems, planets, and planet dimensions. This makes it super easy to
make use of the wonderful rendering system!

## Special thanks to:

Wakaba(Sumeshi)

Nerdypuzzle

Pacific Cyan

*As well as:*

Ovonsame

NorthWestTrees 
