# slime-drone
Unofficial SlimeVR compatible firmware using Drone.

# Why?
Good question. Drone has solid tooling for building embedded Rust on as many targets as possible.

# Why not Embassy?
Another good question. I'd break it into three main points.
1) The Slime firmware is currently written for Embassy but Embassy requires handwritten HALs for a chip (to my knowledge). Drone has a lesser known crate that allows HALs to be automagically generated from SVD files. However Drone lacks Wifi/BT support. So the project will probably be broken into this repo, a crate for IMU support, and then a general crate for bringing radio support to Drone.
2) Drone is interrupt driven. For something as power hungry as Slime style FBT can be with radios and on-device fusion, I would like to try and not do polling wherever I can with this project.
3) I have a general disdain for async await frameworks. I think the ergonomics should make async code an exception and not the default. 
