# Geosys.Viewer.3D POC

## Install demo

Go at the root of the project
```
npm install
```

## Test it
```
npm start
```

The demo is available at `localhost:8000`. Use the mouse with left-button to rotate the view. Use the mouse wheel to zoom in/out.

## POC components

You have all you need in the demo folder:
* `demo.html` is the page to test the POC. In the header there are all the comments to know what are the different scripts and CSS. After the document is loaded, you can see a field in 3D, and a NDVI product applied on it. Under,  you have a slider to accentuate the terrain. And under again,  two buttons to change the texture. Enjoy!
* `scripts/demo.js` is the code used to manipulate the Viewer object that we have to create. In this page you have all methods to creates a 3D-scene with given parameters, to change the texture (image applied on the 3D-model), and change the scale of the 3D-model to accentuate the terrain.
* `scripts/geosys.viewer.3d.js` is the main script. That is the API to create! It has a constructor, a method to create a scene, a method to change the scale and a method to change the texture.
*  `css/demo.css` is used for the demo page.
*  `data` is the repository of images. `dem.png` is the 3D-model, the others are the textures.

## Purpose of the POC

The goal is to replace 
```
	<script src="https://cdnjs.cloudflare.com/ajax/libs/babylonjs/2.5.0/babylon.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/cannon.js/0.6.2/cannon.min.js"></script>   
    <script src="./scripts/geosys.viewer.3d.js"></script>
```
by
```
<script src="./scripts/geosys.viewer.3d.js"></script>
```
where `geosys.viewer.3d.js` contains an API with the following methods:
* `createScene` : create a 3D-scene with parameters detailed in the file.
* `changeScale`: to accentuate the terrain.
* `modifyTexture`: to change the texture.

All the parameters in the  `createScene` method can be isolated in a configuration file. Normally there are no need to change them.

