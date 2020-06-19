---
layout: blog
title: HDILab Fall 2019 Review
---

# HDILab Fall 2019 Review

The original plan in terms of motion capture work is to build a game in which multiple actors’ animations are controlled through user input, combine body and facial mocap, integrate voice and eye-tracking in synch with the actor motion capture recording, figure out a way to perform facial mocap from pre-recorded takes, write a first draft for motion capture paper. In terms of improving my skills, the plan was to do courses on Unity and Reinforcement Learning. Additionally, the plan was to write blogs on, one, multi-person mocap and importing to unity and, two, on how to combine face and body mocap.

During the course of the semester, we completed the unity game in which multiple character animations are controlled through user input. Initially we had a lot of trouble viewing the motion capture outside of motive. This was mainly because we were not able to apply the motion capture onto a model. There were two issues associated with it. One was to separate the individual motion captures from multi-actor mocap recording and the second was to apply them onto a model and export them as fbx files.

Finding an appropriate model to apply the motion capture to consumed a lot of time. We used MotionBuilder to tackle the issues. We streamed the pre-recorded multi-actor take from Motive onto Motion Builder with the help of Optitrack Plugin downloaded in Motion Builder. We re-recorded the streaming data inside Motion Builder. We then downloaded a rigged character or model whose bone mapping convention matched that of Motion Builder’s. This is an important step, without which mapping for each bone to the mocap data needs to be done manually. We selected single character at a time and plotted the motion capture data recorded in Motion Builder to the model. For this step, we need to delete all other entities present in the take. This ‘plot character’ step is the most important of all steps. Inside Motion Builder if you just apply the motion capture to the model, it will appear that the bone mapping has been made too. However, if you export the data as fbx you will find that the model is not animating. Plotting ensures that the motion capture data is baked onto the skeleton of the model. We used the individual mocaps to develop a game in which multiple character animations can be controlled using user input. I have written blogs to outline [how to export individual fbx files from motive recordings](https://aishwarya.io/exporting-individual-fbx-files-from-motive-recordings) and [controlling animators through user input. ](https://aishwarya.io/unity-control-an-animator)

Extracting individual mocap data as Fbx from multi skeleton recordings took us almost the whole semester. It consumed way too much time! One of the reasons, I feel, contributing to the delay is the lack of better planning. For example, whenever we faced an issue in this multi-step process, we would all start looking for a solution. What would have been a much better thing to do is to divide the tasks amongst between ourselves. Each of us working on different aspects of the process, I feel, would have resulted in a much more efficient working process. We should take care to not repeat this mistake in our future projects.

On the facial motion capture front, we are successfully able to perform facial motion capture but we are yet to integrate it with body mocap. We are currently working on integrating eye tracking as a priority. The goal is to integrate eye tracking for one of the characters and design a laser connecting the character’s to the object being looked at in Unity.

Apart from I also prepared a rough draft of the motion capture paper during the semester. I was also able to complete the Beginner’s Guide to Machine Learning in Unity course. Towards the end of the semester, my labmates and I had a long discussion with Dr. Park regarding plans for future lab work. One exciting thing we did this semester is making a [video presentation](https://www.youtube.com/watch?v=Vlmr_rRW5bA) of the lab’s motion capture capabilities.

My experience of working in the HDILab has definitely been great this semester. We were plagued with not being able to export individual fbx files for a long time but the experience has taught us the importance of being perseverant.

I really like the work that we are doing and the learning environment being cultivated. As a step to improve lab seminars, a brief talk on the concepts would help though everyone comes prepared for the lab seminar by reading the chapters.

I am trying to follow the lab culture to the best of my abilities. I try to collaborate with my lab mates whenever possible. I am punctual to the lab and at times when I cannot come on time I make it a point to inform everyone. I am trying to create reproducible output. I am earnest in my work. I have the drive to learn and excel.

As a plan for next semester, on the Motion Capture front, I plan to complete the integration of eye-tracking on a priority basis. I also plan to finish reading the list of relevant papers provided by Dr.Park and focus on making a table of differences to improve the related work section of the Motion Capture paper to produce a second draft.

Additionally, I would also like to continue improving myself by doing the Unity and Reinforcement Learning course. Like suggested by Dr.Park, I will start studying and solving the ‘Pattern Recognition and Machine Learning’ book.

I found myself a little hard pressed for time this semester. Though it is the case every semester, this semester was especially taxing.
