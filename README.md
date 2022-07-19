# My first OpenGL scene

## You can find the code [here](https://github.com/PaulOwO/GPR5300).

## Preview
![](https://github.com/PaulOwO/Portfolio.github.io/blob/39770161c20a4e999548c14b091dd06c9c981836/gif/opengl.gif)
![image](https://user-images.githubusercontent.com/71375990/179767972-c7dbc421-7940-4034-84d6-7f6214cd5a84.png)

We are going to see overall how the scene evolve throuout 2 months and thanks to wich techniques.

## The setup

- First of all this project was done for the module GPR3500 at the SAE institute of Geneva.
- The project was done on [OpenGL](https://www.opengl.org) which allow us to do graphics programming on a lot of platforms.
- We used [SDL](https://www.libsdl.org) to create our application window and take input.
- In addition to our course, we used the site [Learn OpenGL](https://learnopengl.com) to help us throught programming.

Each week we saw different graphic programming thecnique and had to implement thus we needed/wanted in our final scene,
so let's get started!

## Triangle

![image](https://user-images.githubusercontent.com/71375990/179768284-5b9686e6-d962-4ae1-9ea8-929e58fea4b0.png)

We started with a triangle, the simplest shape that we use to create every object in the scene.
We created our first shader, Vertex Buffer Objects, Array Buffer Objects and uniform and with that we had some kind of basis.


## Square

![image](https://github.com/PaulOwO/Portfolio.github.io/blob/02a3d8f235728be558430498f548190e9ad871d4/gif/ezgif.com-gif-maker%20(2).gif)
![image](https://user-images.githubusercontent.com/71375990/179768462-facfb500-d9c9-48a9-bc36-859986572c28.png)

To make a square we learnd about indices and Elements Buffer Objects that allow us not to draw again the part of our trinagle that would overlap.


## Texture

![image](https://user-images.githubusercontent.com/71375990/179745115-248daba2-09db-4006-a679-e35d046dd60c.png)

To aply texture, we first need to load and bind it using multiple openGl command, than give the texure coordonates to our shader.

## Cube 

![image](https://user-images.githubusercontent.com/71375990/179782553-dd2f8e6b-6a78-439e-812e-16fabe0c14d4.png)

Than we did 3d for the first time by adding some vertexs and indices plus creating a model, view and projection matrix to locate it in our space. 

## Lighting 
![image](https://user-images.githubusercontent.com/71375990/179768731-092ceabe-0103-487c-b858-e8a18b145df6.png)

Lighting is done with the help of the light position/direction and by setting uniforms for the power of 3 differents light coponent.
The ambiant light is the color of the object when it isn't dirrectly lit.
The diffuse light is the color of the object when it is dirrectly lit.
The specular is when the normal of the object goes directly in our eye (the camera), it gives this realy bright point.

![image](https://user-images.githubusercontent.com/71375990/179768971-ac7b7109-312c-45f0-9f37-9f0bb56d34c1.png)

For our lighting to work we also need it to work with multiple and different source of light.
We calculate how each light have impact on the object (by changing it's abiant, diffuse, specular) and had it together.
In our scene there is currently 3 lights.
A directional light create light in a direction everywhere. (like the sun)
A point light send light all around it. (like a lamp)
A spotlight that act like a point light but only in one direction. (in our scene it's the camera direction so it's like a flaslight.

Each object also have a material that tell how the object should react to light.

![image](https://user-images.githubusercontent.com/71375990/179787503-3603d213-a661-4b66-a0ec-2fedec43e3a3.png) Lighing map/specular map

A specular map tells if the object should or should not have a specular.

## Model

![image](https://user-images.githubusercontent.com/71375990/179769376-0a20b970-ce75-4f99-a1b4-1fa72236a0d5.png)

We load the data of our model (vertex, texure coordonate, ect...) from all sort of format like ".obj". Thanks to assimp we can access the data easyly and draw ieach mesh that constitute our model

## Frame Buffer 

![image](https://user-images.githubusercontent.com/71375990/179769553-ccf5a45b-4021-4e83-9a1d-ee6cf223a8a0.png)

Frame Buffers allow us to draw things on a different buffer that the one we show at the end. We use this buffer to store what we draw as a new texture we can use later. In this case we drew our entire scene in framebuffer, turn it into a texture than apply some effet on it. 


## Stencil

![image](https://user-images.githubusercontent.com/71375990/179769841-d4e823a4-d38a-47ef-9be8-522a64f61c55.png)

A stencil is a buffer that can be written on and that can discard fragment.
In our scene we draw again our model a bit larger and discard what's in front of our smaller model. We get an outline.

## Cube Mapping

![image](https://user-images.githubusercontent.com/71375990/179770334-0d911b0e-7840-43f9-a475-c540f59a7855.png)

Cube mapping allow us to create a cube of texture with 6 textures.

![image](https://user-images.githubusercontent.com/71375990/179773535-61be525d-2e7a-4545-85df-16821d4ff444.png)

In our case we use it to make a skybox.

## Instancing

![image](https://user-images.githubusercontent.com/71375990/179776948-b769951f-5abd-42ce-88fe-2d4bd4e9cbda.png)

Instancing is an optimization that allow us to use one draw call for the same object .

## Normal Mapping

![image](https://user-images.githubusercontent.com/71375990/179770099-59ef1fc3-2ee6-49d2-9148-bd05f2edcd13.png)

We use normal mapping to create the ilusion of depth thanks to lighting.

![image](https://user-images.githubusercontent.com/71375990/179773268-06a2c26d-6cd1-4c47-872d-9e693d938da0.png)

![image](https://user-images.githubusercontent.com/71375990/179773353-c38ca374-4762-45d8-8b08-7f4dbe8b0d89.png) Normal maps

A normal map is used to redifine the normals of our object that we use in our light calculation. We can create more details without adding any triangles.  

## Shadow Mapping

![image](https://user-images.githubusercontent.com/71375990/179770514-ea955139-1a51-4ce1-baef-87f5ee616ede.png)

Shadow mapping is used to create shadow!

To do so we bind a frambuffer than draw our scene from the point of view our light in depth only. Than we draw in another buffer the scene normaly whith our shadow map that we just got.

In our case the light being a directional light doesn't have a positon so we made an aproximation to have it cover our scene.

![image](https://user-images.githubusercontent.com/71375990/179773754-915ccec7-9d31-4361-9ace-73e11f9d937f.png) Shadow map

## Final Scene

![image](https://user-images.githubusercontent.com/71375990/179767972-c7dbc421-7940-4034-84d6-7f6214cd5a84.png)

From what we saw before, let's see what element we put in our scene :

Lighting :






## What more could have been done

### View frustrum culling
![image](https://user-images.githubusercontent.com/71375990/179771229-966a2c75-50d0-440b-b3d1-3879989746c8.png)

In the current scene the only "camera view" optimisation is the backface culling that that does not draw the back of the object.
View fustrum culling is an optimistaion that allow objects that are not in the camera to be not drawn and it's one i would have liked to had in my scene.

### Shadow Cube Mapping

![image](https://user-images.githubusercontent.com/71375990/179773570-8f002a60-b217-49ee-a87d-d9f5457c13a5.png)

![image](https://user-images.githubusercontent.com/71375990/179773754-915ccec7-9d31-4361-9ace-73e11f9d937f.png)

As previously said in "Shadow Mapping", my shadow only work for directionnal lighting. We could make it work for a point light by creating a cube map of shadow map, it means that we would have to draw how scene from six different points of view.

## What's next

To go deeper into graphycs programming there are multiple things that could be done, the first one being finishing the scene with some more effect and adding PBR that is the lighting thecnique mostly used in the industrie. Then the next step would be to do again the scene but in DirectX 11 to learn many things!

## Conclusion 

That's it for the overview of my scene, we saw all the thecniques i used and what they do in the scene.
I appreciated this course and can't wait to learn about more tecknique used in the industrie. 








