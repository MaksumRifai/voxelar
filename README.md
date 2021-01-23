# Voxel AR
For this tutorial, we use AR.js and Aframe.js library, Image Descriptor, and Voxel.

## AR.js
AR.js is a lightweight library for Augmented Reality on the Web, coming with features like Image Tracking, Location based AR and Marker tracking.

## Aframe.js
Web framework for building virtual reality experiences.

### Import the library

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

## Image Tracking
Natural Feature Tracking or NFT is a technology that enables the use of images instead of markers like QR Codes or the Hiro marker.
It comes in two versions: [the Web version](https://carnaux.github.io/NFT-Marker-Creator/) (recommended), and the [node.js version](https://github.com/Carnaux/NFT-Marker-Creator).
### Create Descriptors
<img src="https://raw.githubusercontent.com/MaksumRifai/voxelar/master/photo.jpg" width="150">
We create descriptor with this picture (photo.jpg) by uploading to NFT creator web version above then return 3 files to use:  
.fset, .fset3, .iset. Each of them will have the same prefix before the file extension. That one will be the Image Descriptor name that you will use on the AR.js web app. For example: with files photo.fset, photo.fset3 and photo.iset, your Image Descriptors name will be photo.

