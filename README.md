# Voxel AR

<img src="https://raw.githubusercontent.com/MaksumRifai/voxelar/master/voxelar-preview.gif">
For this Project, I used AR.js and Aframe.js library, Image Descriptor, and Voxel.

https://github.com/MaksumRifai/voxelar (Repo) | https://maksumrifai.github.io/voxelar (Live)

Open Live Demo with Chrome Mobile Browser or AR/VR/XR Devices, When cam ready, Scan BekasiDev Sticker or Logo from bekasidev.org Or you can use image below.

<img src="https://raw.githubusercontent.com/Bekasi-Dev-Community/bekasidev/master/assets/img/brand/bekasidev-stiker.png" width="450">

Note for Desktop Browser you need latest Chrome or Edge that suported and enabled for WebVR Experiences, and also good desktop camera (Webcam), Recommended use Mobile Browser.

# Libraries

## AR.js
AR.js is a lightweight library for Augmented Reality on the Web, coming with features like Image Tracking, Location based AR and Marker tracking.

## Aframe.js
Web framework for building virtual reality experiences. 

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

### Choose Good Images
If you want to understand the creation of markers in more depth, check out the NFT Marker Creator [wiki](https://github.com/Carnaux/NFT-Marker-Creator/wiki/Creating-good-markers). It explains also why certain images work way better than others. An important factor is the DPI of the image: a good dpi (300 or more) will give a very good stabilization, while low DPI (like 72) will require the user to stay very still and close to the image, otherwise tracking will lag.

### Create Image Descriptors:
<img src="https://raw.githubusercontent.com/MaksumRifai/voxelar/master/photo.jpg" width="150">
We create descriptor with this picture (photo.jpg) by uploading to NFT creator web version above then return 3 files to use:

.fset, .fset3, .iset. Each of them will have the same prefix before the file extension. That one will be the Image Descriptor name that you will use on the AR.js web app. For example: with files photo.fset, photo.fset3 and photo.iset, your Image Descriptors name will be photo.

### Create Object
You can download and use 3D models or object from anywhere or create your own with Blender. For this repo, I created my own model based on [Bekasidev](https://bekasidev.org) Logo with MagicaVoxel, this logo vector and raster is also originaly created by me.

<img src="https://raw.githubusercontent.com/MaksumRifai/voxelar/master/ss-mv-bekdev.jpg">

You can watch tutorial on my youtube channel here for DTS Kominfo Logo:

- [10 Menit Membuat Logo 3D (Digital Talent Scholarship)](https://www.youtube.com/watch?v=0GfNYFcDjMU&t=6s)
- [Membuat rumah dengan MagicaVoxel](https://www.youtube.com/watch?v=nbfeWj46R3c)
- [Tutorial Blender 3D Basic : View, Navigation, Transformation](https://www.youtube.com/watch?v=tEAuDC7SjsQ&t=33s)


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

The only custom component here is the a-nft, the Image Tracking HTML anchor. You may see my other project for references.

- 360° Image VR, Add 3D bus into 360 Degree Image ([Repo](https://github.com/MaksumRifai/360vr) | [Demo](https://maksumrifai.github.io/360vr))
- Simple Object and Animation VR, Add 3D DTS logo Into Environment ([Repo](https://github.com/MaksumRifai/digitaltalent) | [Demo](https://digitaltalent.netlify.app))
- WebAR Image Tracking with Kumparan Logo Umbrella ([Repo](https://github.com/MaksumRifai/kumparan-ar) | [Demo](https://maksumrifai.github.io/kumparan-ar))

<a href="https://maksumrifai.github.io/360vr"><img src="https://raw.githubusercontent.com/MaksumRifai/360vr/master/360vr-preview.gif"></a>
<a href="https://digitaltalent.netlify.app"><img src="https://raw.githubusercontent.com/MaksumRifai/digitaltalent/master/dts-preview.gif"></a>
<a href="https://maksumrifai.github.io/kumparan-ar"><img src="https://raw.githubusercontent.com/MaksumRifai/kumparan-ar/master/kumparan-preview.gif"></a>

## How to use this template

### Clonning
Run the following command to clone this template to your local directory:
```
$ git clone https://github.com/MaksumRifai/voxelar.git

```
### Download
Use green button above and click "Download Zip" or simply click [here](https://github.com/MaksumRifai/voxelar/archive/master.zip)

## Customizing
In case you want to use your own models, simply replace the [.obj .mtl .png](https://en.m.wikipedia.org/wiki/Wavefront_.obj_file) files with yours. Don't forget to export your MagicaVoxel or Blender project properly.

And edit this repo as you needed, you only need to replace URL/File name with yours, and the descripted files (fset, iset, fset3) you created with your own source image, use your favorite code editor, directly in web browser or github desktop.

<img src="https://raw.githubusercontent.com/MaksumRifai/kumparan/master/ss-vsc.jpg">

For better and faster development or debugging this project, you can use [Spck Code/Git Editor](http://play.google.com/store/apps/details?id=io.spck) for Android, I mainly use this way.

<a href="https://github.com/MaksumRifai/360vr/blob/master/360vr.gif"><img src="https://raw.githubusercontent.com/MaksumRifai/360vr/master/360vr.gif"></a>
<br/><br/>

# References & Resources

## A-Frame Boilerplate

Web framework for building virtual reality experiences.

[Github](https://github.com/aframevr/aframe) | [Website](https://aframe.io).

Alternatively, check out the [A-Frame Starter on
glitch.com](https://glitch.com/~aframe) for a more interactive way on getting
started.

## MagicaVoxel @ephtracy

A free lightweight GPU-based voxel art editor and interactive path tracing renderer.

[Github](https://github.com/ephtracy) | [Website](https://ephtracy.github.io/) | [Demo](https://youtu.be/mfKx4j-C6nI)

## Tutorial Videos

- [Youtube: Ephtracy](https://youtu.be/d_WymsNdRBA)
- [Youtube: Aaron Robbins](https://www.youtube.com/playlist?list=PLHtmobOgsDvlikllA1MBk7pk_DWlmtR_S)
- [Youtube: Maksum Rifai](https://www.youtube.com/watch?v=0GfNYFcDjMU&t=42s)

## Articles

- [Publishing Voxel Designs from MagicaVoxel to Sketchfab](https://blog.sketchfab.com/publishing-voxel-designs-from-magicavoxel-to-sketchfab/)
- [Building with MagicaVoxel and export to A-Frame (WebVR framework)](https://aframe.io/docs/0.3.0/guides/building-with-magicavoxel.html)
- [Script for animating MagicaVoxel rendering](http://drinkdecaf.com/magicavoxel_animate)

### Support Me
<a href="https://www.paypal.me/maksumrifai"><img src="https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcSRU16oC9ndfwmD5a14Df0X7B96ummOHmQGsg&usqp=CAU" width="200"></a> <a href="https://invoice.xendit.co/donation/Dukungan"><img src="https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcROR5VQJr0XTxLh-kmhGyyyQA0i8ISLTxQRcg&usqp=CAU" width="200"></a>

<a href="https://github.com/desainerhub"><img src="https://raw.githubusercontent.com/MaksumRifai/360vr/master/learn.png" width="200"></a>
<a href="https://github.com/Bekasi-Dev-Community"><img src="https://raw.githubusercontent.com/Bekasi-Dev-Community/bekasidev/master/assets/img/brand/bekasidev-banner.png" width="200"></a>
