# Artify

In the day of Instagram, we are exposed to multiple people who draw such nice and creative comics. We were inspired by them and wanted to try our hands in making comics and we started with drawing the faces of the characters. But we failed xD. So, we went through research papers and searched for something that can help us to take baby steps in this area. And like this, *Artify* was born.

## Prerequisites
- Linux or macOS
- Python 3
- CPU or NVIDIA GPU + CUDA CuDNN

## Getting Started
- Clone this repo:
```
git clone https://github.com/yudhik11/Artify/
cd Artify
```
- Install PyTorch 1.0+ and dependencies from http://pytorch.org
- Install Torchvision
- Install all requirements
```
pip install -r requirements.txt
```


### Face

- Download model weights of `checkpoints` from google-drive [link](https://drive.google.com/open?id=125jXBRfzmNmtzP7Q2KdmTnyK64tpMAEG)
- Download model weights of `checkpoints_face` from google-drive [link](https://drive.google.com/open?id=1ZXBEBP2Gn5Vb_sGXbz5RKR9WnNs67spa)

```
bash scripts/prepare_face.sh
```

- Play with the interface

```
bash run_face.sh
```

### Sketch

- Download model weights of `checkpoints_sketch` from google-drive link [link](https://drive.google.com/open?id=1hbaTN_O3PAehBEKE4cKdkD8cHRmQJ5Gj)
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
