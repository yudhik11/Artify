# Artify

We propose an interactive GAN-based sketch-to-image translation method
that helps novice users easily create images of simple objects.
The user starts with a sparse sketch and a desired object category, and the network then recommends its plausible completion(s) and shows a corresponding synthesized image. This enables a feedback loop, where the user can edit the sketch based on the network's recommendations, while the network is able to better synthesize the image that the user might have in mind.
In order to use a single model for a wide array of object classes, we introduce a gating-based approach for class conditioning, which allows us to generate distinct classes without feature mixing, from a single generator network.

## Prerequisites
- Linux or macOS
- Python 3
- CPU or NVIDIA GPU + CUDA CuDNN

## Getting Started
- Clone this repo:
```
git clone https://github.com/arnabgho/Artify
cd Artify
```
- Install PyTorch 1.0+ and dependencies from http://pytorch.org
- Install Torchvision
- Install all requirements
```
pip install -r requirements.txt
```


### Face

<p align="center">
  <img  height="300" src='docs/resources/gifs/emoji.gif'>
</p>
- Download model weights of 'checkpoints' from google-drive [link](https://drive.google.com/open?id=125jXBRfzmNmtzP7Q2KdmTnyK64tpMAEG)
- Download model weights of 'checkpoints_face' from google-drive [link](https://drive.google.com/open?id=1ZXBEBP2Gn5Vb_sGXbz5RKR9WnNs67spa)

```
bash scripts/prepare_face.sh
```

- Play with the interface

```
bash run_face.sh
```

### Sketch

- Download model weights of 'checkpoints_sketch' from google-drive link [link](https://drive.google.com/open?id=1hbaTN_O3PAehBEKE4cKdkD8cHRmQJ5Gj)
```
bash scripts/prepare_sketch.sh
```

```
bash run_sketch.sh
```

# Interface

## Control Panel

* **Reset**: This button resets the drawing panel so that the user can start sketching from scratch.
* **Dice**: This button changes the latent code for the generator, thus changing the shadow. The user can explore the dataset using this feature.
* **Draw Stroke**: This is the default mode whereby the user can sketch in the drawing pad.
* **Move Stroke**: This feature allows the user to select part of the sketch the user has drawn and move around to explore the various modes quickly. The size of the stroke grabbing area can be changed by using the scroll button in the mouse.
* **Warp Stroke**: An experimental feature whereby the user can warp the sketch using control points. The control points can be set using the right click button. Once the user has made all the control points he/she can put the cursor close to one of the points and drag to the desired position with the left mouse button pressed.
* **Enable Shadows**: This feature enables the multiple shadows to be overlayed with the the drawing pad. Otherwise only 1 autocompletion is shown.

## Acknowledgement
Code is inspired by [pytorch-CycleGAN-and-pix2pix]( https://github.com/junyanz/pytorch-CycleGAN-and-pix2pix ). The UI is inspired by [iGAN](https://github.com/junyanz/iGAN). The pix2pixhd implementation is from [SPADE](https://github.com/NVlabs/SPADE). The warp functionality is from [Moving-Least-Squares](https://github.com/Jarvis73/Moving-Least-Squares).
