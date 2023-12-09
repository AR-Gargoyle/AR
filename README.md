ARjs is a lightweight library written in javascript for building augmented reality applications for the web.

The library has the ability to take advantage of markers, images or geolocation to position elements in the real world.

Function Description:

To use the library to build an augmented reality application we need to import the libraries using the <script> tag.
![image](https://github.com/AR-Gargoyle/AR/assets/151898888/6cf6cd88-f3da-4a11-8928-9826932b83db)
In the body of the document we have a scene, a text and a camera:

The scene is the set of 2D and 3D elements that will be displayed on the camera with the help of markers or location services.

The text only helps us debug errors or lack of content to view.

The camera is the virtualization of our mobile camera as it is responsible for abstracting the position and rotation of the mobile to view 3D objects from the same perspective and superimposing it on the image obtained by the camera. Cameras are usually used in video games to project the elements of a scene from a perspective established for the player and thus display them on the screen.
![image](https://github.com/AR-Gargoyle/AR/assets/151898888/83468a9c-b87e-4d20-aa5a-2120bcb503df)
The code contained in the project is located in the index.html file, as an embedded javascript.


In the code there is a method called window.onload which executes the code once the page has been completely loaded.
To show 3D objects within an application through geolocation, we obtain the coordinates of the user's mobile phone through the method or function:

navigator.geolocation.getCurrentPosition();

Inside we place an arrow function where the parameter to use is position, this position class allows us to access the current coordinates by calling the coords property dividing the longitude and latitude.

![image](https://github.com/AR-Gargoyle/AR/assets/151898888/704a8958-05a1-4a31-ac27-e3dabbe0401d)
Within the arrow function we are going to instantiate each of the 3D models and to simplify the code we load them in an array calling each file by its name.
![image](https://github.com/AR-Gargoyle/AR/assets/151898888/13debc5b-659d-4ded-ba28-4fe4fb69833e)

3D models with the .glb extension contain the point mesh of the object, its UV map as well as the texture maps, so it will not be necessary to add them in a separate material.

In another arrangement we store the coordinates of each of the 3D models based on latitude and longitude, saving them as string variables.

![image](https://github.com/AR-Gargoyle/AR/assets/151898888/d96d1f0b-ce49-4b6a-87ef-b44f8a451206)
Finally, within a for loop, we are going to process each element of our two arrays in order to load each of the models, to do this we create an a-entity which will be the representation
of a 3D model.

The model variable will be this instance for our 3D object and in it we will configure
its properties through the setAttribute method, where we will assign a pair of parameters established as property and value.

![image](https://github.com/AR-Gargoyle/AR/assets/151898888/95f380a1-963a-4d78-ae5d-0d122dd68e30)

Properties

gps-entity-place

It has the function of assigning a real world position to our object, in the value we send the coordinates in string format accessing the array object with the current index of the for loop.

gps-entity-place-update-position

This property allows us to update the position of the object in real time, and the minimum distance at which it can be viewed in relation to the camera position is sent as a parameter.


gltf-model

Load the model in memory for visualization, as a parameter we send the path to the file.


rotation

Initial orientation for the 3D model, as configuration parameters the rotations in X, Y and Z are sent, rotating the specified degrees in each axis in that order.

material

The type of material assigned to the object, for the project we send the shader:flat property to specify that it is a solid object and lighting type.

scale

We set the initial scale of the object, values 0.5, 0.5, 0.5 indicate that the object will be displayed at half size.
