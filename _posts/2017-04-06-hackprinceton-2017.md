---
layout: post
title: "HackPrinceton 2017"
date: "2017-04-06 18:32:03 -0400"
categories: tech
---

This past weekend I visited Princeton campus to attend HackPrinceton, a hackathon hosted by the university.
Out of the 10+ hackathons iv went to I feel this was one of the best hackathon experiences iv had. 
Everything from the sleeping arrangements to the overall structure and layout of the hackathon felt well organized.

<amp-img width="1000" height="558" layout="responsive" src="{{ site.baseurl }}/assets/images/resize_Princeton-2.jpg" alt="Princeton Campus"></amp-img> _Princeton campus looked amazing_

I attended this hackathon with two of my coworkers and one new friend I met at Princeton. We spent a week trying to
come up with ideas before the hackathon began and ultimately settled on creating the “Photo-Orb”. This would be a device
capable of circling a human or an object and taking a 360-degree portrait of it. All 360 cameras take an outward facing
image so we wanted to make an inward facing solution. 

There were three components to this project: assembling the hardware, programming the hardware,
and programming a web page to take many images and stitch them together.

Since my web skills are not as strong as my teammates and they hadn't worked with hardware very much, I decided to
help with creating the device. We planned to make it an RC car with a selfie stick attached to the top so it could
drive around the individual while taking pictures with the phone attached to it. We quickly assembled the RC car
without any problems using two DC motors and some wheels. We used a H-bridge to control the direction the motors
were spinning. Using DC motors with an H-bridge created lots of problems for us later on because we weren't able to accurately control the vehicle's position.

<amp-img width="810" height="770" layout="responsive" src="{{ site.baseurl }}/assets/images/rsz_princeton-1.jpg" alt="Hardware image"></amp-img> _The work in progress car_

My teammate and I wrote some python code to prototype a movement scheme where we would run one motor longer than the other to turn in a circle. It worked! We got excited and wanted to solder it together to create moving vehicle but our limited soldering experience created lots of problems as well. Many of our connections weren't as solid as we needed them to be for a moving vehicle. Sometimes a random motor would stop running or would spin in random directions. We spent many hours following the wiring connections and cleaning up the soldering but then realized it was a bug in the code controlling the H-bridge. 

<amp-img width="810" height="910" layout="responsive" src="{{ site.baseurl }}/assets/images/rsz_princeton-3.jpg" alt="Demo image"></amp-img> _Finished product_

Ultimately we finished fixed the bug and the other half of the team finished the website/camera part and everything
was ready for demoing. We impressed many judges and were awarded Nvidia Shield mobile gaming consoles.

Other than the project, I spent a lot of time playing around with a 3D printer and exploring the beautiful campus.
Some things I printed out were: a Jeep logo, a Pontiac logo, a coin with the Bitcoin logo on it and the totem from the movie
Inception. 

<amp-img width="1080" height="736" layout="responsive" src="{{ site.baseurl }}/assets/images/Princeton-4.jpg" alt="3D printed Jeep Logo"></amp-img> _3D printed Jeep logo_
