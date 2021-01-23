# Voxel AR
<img src="https://raw.githubusercontent.com/MaksumRifai/voxelar/master/preview.jpg" width="200">
For this Project, I used AR.js and Aframe.js library, Image Descriptor, and Voxel.

https://github.com/MaksumRifai/voxelar (Repo) | https://maksumrifai.github.io/voxelar (Live)

With that cam ready on your phone, Scan BekasiDev Sticker or open logo from bekasidev.org with your Laptop or PC.

## AR.js
AR.js is a lightweight library for Augmented Reality on the Web, coming with features like Image Tracking, Location based AR and Marker tracking.

## Aframe.js
Web framework for building virtual reality experiences. I created a VR project with aframe if you want to read: 
https://github.com/MaksumRifai/digitaltalent (Repo) | https://digitaltalent.netlify.app (Live)

### Import the library

Import AR.js:
```
<script src="https://raw.githack.com/AR-js-org/AR.js/master/aframe/build/aframe-ar-nft.js">
```

Import Aframe.js:
```
<script src="https://cdn.jsdelivr.net/gh/aframevr/aframe@1c2407b26c61958baa93967b5412487cd94b290b/dist/aframe-master.min.js"></script>
```
For this expample, we use Image Tracking Type of AR.js with Aframe.js.
[Further Reading](https://ar-js-org.github.io/AR.js-Docs/) for another types from AR.js official docs.

## Image Tracking
Natural Feature Tracking or NFT is a technology that enables the use of images instead of markers like QR Codes or the Hiro marker.
It comes in two versions: [the Web version](https://carnaux.github.io/NFT-Marker-Creator/) (recommended), and the [node.js version](https://github.com/Carnaux/NFT-Marker-Creator).
### Create Descriptors:
<img src="https://raw.githubusercontent.com/MaksumRifai/voxelar/master/photo.jpg" width="150">
We create descriptor with this picture (photo.jpg) by uploading to NFT creator web version above then return 3 files to use:

.fset, .fset3, .iset. Each of them will have the same prefix before the file extension. That one will be the Image Descriptor name that you will use on the AR.js web app. For example: with files photo.fset, photo.fset3 and photo.iset, your Image Descriptors name will be photo.

### Create Object
You can download and use 3D models or object from anywhere or create your own with Blender. For this repo, I created my own model based on [Bekasidev](https://bekasidev.org) Logo with MagicaVoxel, you can watch tutorial on my youtube channel here for DTS Kominfo Logo:

- [10 Menit Membuat Logo 3D (Digital Talent Scholarship)](https://www.youtube.com/watch?v=0GfNYFcDjMU&t=6s)

## Render Content to the Scene
```
<!-- Main Scene -->
  <a-scene
    vr-mode-ui="enabled: false;"
    renderer="logarithmicDepthBuffer: true;"
    embedded
    arjs="trackingMethod: best; sourceType: webcam;debugUIEnabled: false;"
  >
    <!-- we use cors proxy to avoid cross-origin problems -->
    <a-nft
      type="nft"
      url="https://arjs-cors-proxy.herokuapp.com/https://raw.githack.com/MaksumRifai/voxelar/master/photo"
      smooth="true"
      smoothCount="10"
      smoothTolerance=".01"
      smoothThreshold="5"
    >
    <!-- as a child of the a-nft entity, you can define the content to show. here's a OBJ model entity -->
    <a-entity rotation="-135 -90 90" scale="5 5 5" position="0 0 0" obj-model="obj: #tree-obj; mtl: #tree-mtl"></a-entity>
    </a-nft>
    <!--Load assets to use by nft entity above-->
       <a-assets>
        <a-asset-item id="tree-obj" src="https://arjs-cors-proxy.herokuapp.com/https://raw.githack.com/MaksumRifai/voxelar/master/bekdev.obj"></a-asset-item>
        <a-asset-item id="tree-mtl" src="https://arjs-cors-proxy.herokuapp.com/https://raw.githack.com/MaksumRifai/voxelar/master/bekdev.mtl"></a-asset-item>
       </a-assets>
    <!--End of assets-->
    <!-- static camera that moves according to the device movemenents -->
    <a-entity camera></a-entity>
  </a-scene>
  <!--End of Scene-->
```

You can refer to [A-Frame docs](https://aframe.io/docs/1.0.0/introduction/) to know everything about content and customization. You can add geometries, 3D models, videos, images. And you can customize their position, scale, rotation and so on.

The only custom component here is the a-nft, the Image Tracking HTML anchor.
