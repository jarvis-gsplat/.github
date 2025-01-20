# JARVIS - Jarvis's Awesome Realtime Virtual Imaging Systems

![jarvis-banner](https://raw.githubusercontent.com/jarvis-gsplat/.github/refs/heads/main/profile/jarvis%20banner%20black.gif)
|[Demo](https://www.youtube.com/watch?v=gfFOG19a_GA)|[Vlog](https://www.youtube.com/watch?v=1BF2jMhQyDg)|

## Introduction:

JARVIS (or Jarvis's Awesome Realtime Virtual Imaging Systems) is an innovative integration of physical and digital processing used to produce a 3D model of captured space using images of the location. The custom-made hardware utilizies 4 cameras connected to a Raspberry Pi 4, and automatically uploads the photos to the backend server, allowing these images to produce a model for a given user on the website. 
To view the pre-made 3d models the site [jarvis.diy](https://jarvis.diy/) can be visited.

JARVIS utilizes Gaussian Splatting (read: https://arxiv.org/abs/2308.04079), a technique that uses gaussians (blurs) rather than points, allowing the processing of the 3d model to be much faster. The hardware utilizes a Raspberry Pi 4 connected to 3 web-cameras in order to capture the images to feed to the model. The images are uploaded to AWS S3, downloaded by the server, and then marked for processing by the GPU.

The front-end was built using Gadget and React Native, and has capabilities for logins based on account and Google (OAuth2 integration), searching for splats by ID, and searching for splats based on username.

[Read our full writeup!](https://dorahacks.io/buidl/21579)

## Requirements 

As long as you have a WebGL capable device, you can view any of our pre trained models through [jarvis.diy](https://jarvis.diy/) !

To complete the backend processing by yourself, including the training of the 3D model, there are several software and hardware requirements. 

For software, the nerfstudio Docker installation (utilized for Gaussian Splatting) is necessary, which can be found here: https://docs.nerf.studio/quickstart/installation.html.

For hardware, processing of the actual model requires at least a 20X0 NVIDIA GPU as outlined by nerfstudio requirements.
