# Voxel AR

## AR.js - Augmented Reality on the Web
AR.js is a lightweight library for Augmented Reality on the Web, coming with features like Image Tracking, Location based AR and Marker tracking.

## AR types
- Image Tracking
- Location Based
- Marker Based

## Import the library
AR.js from version 3 has a new structure.

AR.js is coming in two, different build. They are both maintained. They are exclusive.

The file you want to import depends on what features you want, and also which render library you want to use (A-Frame or three.js).

AR.js uses jsartoolkit5 for tracking, but can display augmented content with either three.js or A-Frame.

You can import AR.js in one version of your choice, using the <script> tag on your HTML.

Import AR.js:
```
<script src="https://raw.githack.com/AR-js-org/AR.js/master/aframe/build/aframe-ar-nft.js">
```
For this expample, we use Image Tracking Type of AR.js with Aframe.js.
[Further Reading](https://ar-js-org.github.io/AR.js-Docs/) for another types from official docs.

Import Aframe.js:
```
<script src="https://cdn.jsdelivr.net/gh/aframevr/aframe@1c2407b26c61958baa93967b5412487cd94b290b/dist/aframe-master.min.js"></script>
```

## Getting started with Image Tracking
Natural Feature Tracking or NFT is a technology that enables the use of images instead of markers like QR Codes or the Hiro marker.

The software tracks interesting points in the image and using them, it estimates the position of the camera.

These interesting points (aka "Image Descriptors") are created using the NFT Marker Creator, a tool available for creating NFT markers.

It comes in two versions: [the Web version](https://carnaux.github.io/NFT-Marker-Creator/) (recommended), and the [node.js version](https://github.com/Carnaux/NFT-Marker-Creator). There is also a fork of this project on the AR.js Github organisation, but as for now, Daniel Fernandes version works perfectly.
[Further Reading](https://ar-js-org.github.io/AR.js-Docs/image-tracking/) from official Docs.
