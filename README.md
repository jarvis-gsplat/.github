![jarvis-banner](https://raw.githubusercontent.com/jarvis-gsplat/.github/refs/heads/main/profile/jarvis%20banner%20black.gif)
| [Live website](https://jarvis.diy/) | [Demo](https://www.youtube.com/watch?v=gfFOG19a_GA) | [DoraHacks](https://dorahacks.io/buidl/21579) |

![jarvis-demo](https://raw.githubusercontent.com/jarvis-gsplat/.github/refs/heads/main/profile/jarvis%20demo.gif)

# JARVIS (Jarvis's Awesome Realtime Virtual Imaging Systems) 
Built in 36 hours as part of uOttaHack 7.

Jarvis is an innovative integration of physical and digital processing to produce 3D views from 2D spatial data (images/videos). It is based on the novel technique known as [gaussian splatting](https://repo-sam.inria.fr/fungraph/3d-gaussian-splatting/). Ever thought about creating a virtual tour / interactive model for your business, but don’t have the necessary equipment? This is a very budget-friendly solution that turns images/videos from ANY camera into an interactive, web-ready 3D view. Compared to traditional 360 camera options (400-500$), this is a no-brainer.

## Hardware
The custom-made hardware, utilizing 4 cameras connected to a Raspberry Pi 4 is used to capture the surroundings. On the press of the button (and the optional voice command of "Jarvis, clip that"), the last ~20 seconds of photos are uploaded to an AWS S3 server to be trained.

![20250119_083551.jpg](https://cdn.dorahacks.io/static/files/1947ee8f8a800f6afeaf3ee40a0bd0d9.jpg)

![20250119_083546.jpg](https://cdn.dorahacks.io/static/files/1947ee89b1c800a08b751e944ea9daaf.jpg)

![20250119_083601.jpg](https://cdn.dorahacks.io/static/files/1947ee843d9b6d223e148be4294a84cc.jpg)

## Backend

We adapted [Nerfstudio](https://arxiv.org/abs/2302.04264), a research paper based on [gaussian splatting](https://repo-sam.inria.fr/fungraph/3d-gaussian-splatting/). A local server periodically checks for new uploads from the AWS S3 server, then starts the GPU training (RTX 3060) in a dockerized container. The typical training time for a 200 images dataset on our machine is about 15 minutes.

![jarvis terminal.png](https://cdn.dorahacks.io/static/files/194850dbc40734d7936f44144938c6dd.png)

![jarvis training.png](https://cdn.dorahacks.io/static/files/194851686928ddcb5ae9dd94163b7ba5.png)

## Frontend

We built [jarvis.diy](https://jarvis.diy/) using React and Vite, all powered in a fullstack development environment by [Gadget](https://gadget.dev/). It comes with both internal authorization and Google OAuth2 authorization.

![aJAJAA.JPG](https://cdn.dorahacks.io/static/files/1947eb27d047b7715ba1e034fe795f3a.jpg)

Gaussian splat WebGL viewer demo (capable of 60fps on low-end laptops):
![youtube](https://youtu.be/QPllF-6R4TI)

## BONUS: A Behind-the-scene video!
[![JARVIS video demo](https://cdn.dorahacks.io/static/files/19485270eaa559d39c0c24f48fd9af7a.png)](https://www.youtube.com/watch?v=1BF2jMhQyDg)
