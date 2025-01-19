# JARVIS - Jarvis's Awesome Realtime Virtual Imaging Systems

## Introduction:

JARVIS (or Jarvis's Awesome Realtime Virtual Imaging Systems) is an innovative integration of physical and digital processing used to produce a 3d model of captured space using images of the location. The custom-made hardware, utilizing 3 cameras to capture the surroundings, automatically uploads the photos to the backend server, allowing these images to produce a model for a given user on the website. 
To view the pre-made 3d models the site jarvis.diy can be visited.

JARVIS utilizes a technique known as Gaussian Splatting (which can be read about here: https://arxiv.org/abs/2308.04079), a technique that uses blurs rather than points, allowing the processing of the 3d model to be much faster. The hardware utilizes a Raspberry Pi 4 connected to 4 web-cameras in order to capture the images to feed to the model. The images are uploaded to AWS, downloaded by the server, and then uploaded to processing.

The front-end was built using Gadget and React Native, and has capabilities for logins based on account and Google (oAuth2 integration), searching for images by ID, and searching for images based on username.

## Requirements 

To complete the backend processing, including the rendering of the 3d model, there are several software and hardware requirements. 

For software, the Nerve Studio Docker installation (utilized for Gaussian Splatting) is necessary, which can be found here: https://docs.nerf.studio/quickstart/installation.html.

For hardware, processing of the actual model requires [hardware info]
