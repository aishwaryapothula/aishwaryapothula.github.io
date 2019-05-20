---
layout: blog
title: Unity Tutorial on how to control an Animator  
---

# Unity Tutorial on how to control an Animator  



This is a very basic Unity Tutorial on how to control an animator object&#39;s behavior based on user input. For example, the animator object will perform a certain defined action when the user inputs &#39;1&#39;. In the same fashion, the animator object will perform a different action when the user inputs &#39;2&#39; on the keyboard.

Let&#39;s get started and create this simple game. You can also watch this video tutorial.


<iframe width="560" height="315" src="https://www.youtube.com/embed/_yDVf4bKz6Y" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>


Download and install [Unity3D](https://unity3d.com/unity). Open unity and create a new Unity 3D project titled &#39;Animation Game&#39;.  

Configure your unity so that the animator window is visible. To enable, go to &#39;_Window_&#39; select &#39;_Animation_&#39; and select &#39;_Animator_&#39;. You will now be able to see the &#39;_Animator_&#39; window available.

Let&#39;s talk about the input file that we have on hand. I already have with me an fbx containing a video of a few action sequences. If you don&#39;t already have one, you will be able to download fbx files online for free. This [Quora page](https://www.quora.com/What-is-the-best-free-database-of-3D-models-I-can-use-in-Unity) mentions a few resources.

Now, right-click on &#39;_Assets_&#39; to &#39;_Import New Asset&#39;_. Import the fbx file that you have. Place the asset onto &#39;_Hierarchy_&#39; to open it in &#39;_Inspector&#39;_ view. Click on the video in the assets to see tabs such as &#39;_Model_&#39;, &#39;_Rig_&#39;, &#39;_Animation&#39;_, &#39;_Materials&#39;_.  When you select the &#39;_Animation&#39;_ tab and click the play button at the bottom, you will be able to play the video.

We now need to divide the fbx file so that we can define action clips. These clips will the actions that will be performed by the animator object upon user input. We create the first clip by clicking on the video name in the &#39;_Animation_&#39; tab and renaming it to &quot;stance&quot; or any other name that you want to give the action. Now, click on &#39;_Clamp Range&#39;_ to specify  the frame ranges in the &#39;_Start_&#39; and &#39;_End_&#39; input boxes. To create the next clip, click on the &quot;_+_&quot; symbol below the clips, give the action clip a new name and repeat the procedure.

Once all the required action clips are created, click on &#39;_Create_&#39; button in the &#39;_Project_&#39; view to create &#39;_Animation Controller&#39;_. Give the &#39;_Animation Controller&#39;_ a name. I&#39;ve named it Humanoid. Select the asset/fbx file you put in &#39;_Hierarchy_&#39; and you will be able to see a &#39;_Controller_&#39; box under &#39;_Animator&#39;_ in the view. Drag and drop the newly created controller-Humanoid onto the &#39;_Controller_&#39; box. Once you create the controller you&#39;ll be able to see some blocks created in the &#39;_Animator_&#39; window. Now, click on the right arrow on the fbx file in the assets under &#39;_Project_&#39; view to expand it. You will now be able to see all the action clips that you have created. Drag and drop these clips onto the &#39;_Animator_&#39; window. Right click on the &#39;_Animator_&#39; screen and select &#39;_Create State&#39;_ and then select &#39;_Empty&#39;_ to create an empty state. Right click on the &#39;entry&#39; box in the &#39;animator&#39; window and click on &#39; _Make Transition&#39;_.  As soon as we click on &#39;_Make Transition_&#39; an extendable arrow appears. Link the arrow from the &#39;_Entry_&#39; state to the &#39;_New State_&#39;. Repeat this process until transitions from  each of the the clips in the &#39;_Animator_&#39; window  to the &#39;_New State&#39;_ are created. Creating transitions from entry and each of the states/clips to the &#39;new state&#39; ensures that the animator object returns to the initial state/starting state after performing each action. Without these transitions, the animator object will not be able to repeat an action immediately.

Now, click on the fbx file in the &#39;_Hierarchy_&#39; view and click on &#39;_Add Component&#39;_ in the &#39;_Inspector_&#39; view and select &#39;_New Script&#39;_ to create a new c# script. Now that the script is attached to the game object, we will be able control the behavior of the animator object using the script. Let&#39;s name the script &#39;action&#39;. Type in the following code

```
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class animation : MonoBehaviour
{
    public Animator ar;


    void Start()
    {
        ar = GetComponent<Animator>();


    }


    // Update is called once per frame
    void Update()
    {
        if (Input.GetKeyUp("a1"))
        {
            ar.Play("a1");
        }
        if (Input.GetKeyUp("2"))
        {
            ar.Play("a2");
        }
        if (Input.GetKeyUp("3"))
        {
            ar.Play("a3");
        }
        if (Input.GetKeyUp("4"))
        {
            ar.Play("a4");
        }
    }
}
```

In the code we create a public animator variable called &#39;ar&#39; which can be used later to hold the animator object. In &#39;start&#39; we create an object for the class &#39;animator&#39;. In the &#39;update&#39; section we are linking the user input to the actions to be performed by the animator object. Any instruction written in the update section are executed for every frame. We have now successfully created the game. Go the &#39;_Game_&#39; tab and click on play. Now, the game objects performs actions according to the keyboard inputs that we give. Inputting &#39;1&#39; on the keyboard would render action clip 1 being performed by the game object.


You can download the build from the following link. 

[Build Link](https://drive.google.com/drive/folders/1K-wgbRSq1-ugXS3X6cZ6VNCiAcjM7DUu) 
