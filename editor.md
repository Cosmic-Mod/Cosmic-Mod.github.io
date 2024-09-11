---
title: Planet editor
layout: page
---


<style>
    canvas { 
        border: 1px solid black; 
        margin-right: 20px; 
    }
    .menu { 
        width: 200px; 
    }
    .planet-properties { 
        display: none; 
    }
    .property-group {
        margin-bottom: 20px;
    }


</style>

<!-- Canvas where planets (squares) are displayed and manipulated -->
<canvas id="planetCanvas" width="600" height="400"></canvas>

<!-- Menu and controls for adding planets and editing properties -->
<div class="menu">
    <!-- Button to add a new planet (square) to the canvas -->
    <button id="addPlanetBtn">Add Planet</button>

    <!-- Properties menu for editing the selected planet -->
    <div class="planet-properties">
        <h3>Planet Properties</h3>

        <table>
            <tr>
                <th>X</th>
                <th>Y</th>
                <th>Z</th>
            </tr>
            <tr>
                <td>
                    <input id="xinput" type="number" value="0"></input>
                </td>
                <td>
                    <input id="yinput" type="number" value="0"></input>
                </td>
                <td>
                    <input id="zinput" type="number" value="0"></input>
                </td>
            </tr>
            <tr>
                <th>Yaw</td>
                <th>Pitch</td>
                <th>Roll</td>
            </tr>
            <tr>
                <td>
                    <input id="yawinput" type="number" value="0"></input>
                </td>
                <td>
                    <input id="pitchinput" type="number" value="0"></input>
                </td>
                <td>
                    <input id="rollinput" type="number" value="0"></input>
                </td>
            </tr>
        </table>
        
        
        

        <!-- Group for adjusting the size of the planet -->
        <div class="property-group">
            <label for="sizeSlider">Size: </label>
            <input type="range" id="sizeSlider" min="10" max="100" value="50">
            <span id="sizeDisplay">50</span>
        </div>

        <!-- Group for selecting a texture for the planet -->
        <div class="property-group">
            <label for="textureSelect">Texture: </label>
            <select id="textureSelect">
                <option value="None">None</option>
                <option value="texture1.png">Texture 1</option>
                <option value="texture2.png">Texture 2</option>
            </select>
        </div>

        <!-- Button to delete the selected planet -->
        <button id="deletePlanetBtn">Delete Planet</button>
    </div>
</div>

<!-- Include the JavaScript file -->
<script src="planetEditor.js"></script>


