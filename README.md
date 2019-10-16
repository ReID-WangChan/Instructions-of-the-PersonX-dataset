## Details of PersonX dataset and how to generate images based on the system are as follows. 

The PersonX dataset is generated by the synthetic data engine PersonX that can synthesise images under controllable cameras and environment. For researching viewpoint, six backgrounds are used in this version (as shown in above figure), including three pure color backgrounds and three scene backgrounds. There are 1266 hand-crafted identities (547 females and 719 males) and each identety has 36 viewpoints (sampled every <a href="https://www.codecogs.com/eqnedit.php?latex=0^{\circ}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?10^{\circ}" title="10^{\circ}" /></a> from <a href="https://www.codecogs.com/eqnedit.php?latex=0^{\circ}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?0^{\circ}" title="0^{\circ}" /></a> to <a href="https://www.codecogs.com/eqnedit.php?latex=0^{\circ}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?350^{\circ}" title="350^{\circ}" /></a> ).

![fig1](https://github.com/sxzrt/Dissecting-Person-Re-identification-from-the-Viewpoint-of-Viewpoint/blob/master/images/fig1.jpg)  


****
## The Link of the Dataset
We release 3D models of the identeties and the 1266 models can be downloaded from the following links:<br>
[Baidu Disk](https://pan.baidu.com/s/1oi9ObdnktrXe5ShiwIspSw)<br>
[Google Drive](https://drive.google.com/open?id=1SJ0qeKkEr7KMlk-JaeMghsJkNxRQTXcs)

## The Instructions of the Dataset
The package can be imported into any program of Unity directly. 
*  The version of Unity used in this work is [2018.1.8 f1 Personal](https://unity3d.com/unity/whatsnew/unity-2018.1.8) that can be downloaded from the [Unity Website](https://unity3d.com/).
*  "PersonX1266.unitypackage" is a Unity package that contains the original 3D models of the identities. it can be imported into the project by double-click. 
*  The scenes (backgrounds) can be selected or designed based on your demand and there are many free sources in Unity Asset Store. If you want to use the scenes used in this work, please send an email to xxsunzrt@gmail.com.

### Guide of Getting images of the person

We have supplied a example of a controller "example-controllerc.unitypackage" that can make the person to rotate and can capture the images automatically.

#### 1. Import the example-controller in to your project (*e.g.,* new project)

<div align=left><img src="https://github.com/sxzrt/Instructions-of-the-PersonX-dataset/blob/master/images/1.png" width="400" /></div>


#### 2. Add the controller (Game_Manager) into the project
<div align=left><img src="https://github.com/sxzrt/Instructions-of-the-PersonX-dataset/blob/master/images/2.png" width="400" /></div>

 There are three components in the Game_Manager: PeoplePosition, Camera and Main Camera as follows.
<div align=left><img src="https://github.com/sxzrt/Instructions-of-the-PersonX-dataset/blob/master/images/3.png" width="400" /></div>

 Here, PeoplePosition controls the rotation of the person: 
 <div align=left><img src="https://github.com/sxzrt/Instructions-of-the-PersonX-dataset/blob/master/images/4.png" width="400" /></div>
 
 Main Camera and Camera are used to generate a pair of images that have cintains the same person in same position. One is    without background and its person with a red border, which is used to caculate the bounding box of the person:
 <div align=left><img src="https://github.com/sxzrt/Instructions-of-the-PersonX-dataset/blob/master/images/5.png" width="400" /></div>


#### 3. three things to notice
 
 **!!**  two paths:
 <div align=left><img src="https://github.com/sxzrt/Instructions-of-the-PersonX-dataset/blob/master/images/6.png" width="400" /></div>

The name of path1 shoud be "Resources", in which are the models of person such as A1;

The 24th line of Manager.cs is the path to save the generated images, which is better **not** to be the sub-path of the project (because  Unity will import the generating images, which will slow the generation process.).
 
  **!!**  the ID of the first person:
  
   <div align=left><img src="https://github.com/sxzrt/Instructions-of-the-PersonX-dataset/blob/master/images/7.png" width="400" /></div>
  
To matching of the frames between two cameras, the first inputted person will loss one image. Therefore, we use ID 0 (a copy of ID 1) to initial the process, which dose not count towards the 1266 identities. 


#### 4. Run ▶️ the Game_Manager in Unity can get the images of a person with different viewpoints. 


#### 5. The script crop_bbox.m can be used to get bounding boxes of person, crop and rename images.

**** 
#####  `The original images and unity project will be released ASAP.`


**** 
If you use this dataset in your research, please kindly cite our work as, <br>
```
@inproceedings{sun2019dissecting,
	title={Dissecting Person Re-identification from the Viewpoint of Viewpoint},
	author={Sun, Xiaoxiao and Zheng, Liang},
	booktitle={CVPR},
	year={2019}
}
```
