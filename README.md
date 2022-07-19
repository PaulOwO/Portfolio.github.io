# My first OpenGL scene

## Preview
![](https://github.com/PaulOwO/Portfolio.github.io/blob/39770161c20a4e999548c14b091dd06c9c981836/gif/opengl.gif) The blur is done willingly !
![image](https://user-images.githubusercontent.com/71375990/179767972-c7dbc421-7940-4034-84d6-7f6214cd5a84.png)

We are going to see overall how the scene evolve throuout 2 months and thanks to wich techniques.
We are also going to stop to realy see how I did my normal mapping.

## The setup

- First of all this project was done for the module GPR3500 at the SAE institute of Geneva.
- The project was done on [OpenGL](https://www.opengl.org) which allow us to do graphics programming on a lot of platforms.
- We used [SDL](https://www.libsdl.org) to create our application window and take input.
- In addition to our course, we used the site [Learn OpenGL](https://learnopengl.com) to help us throught programming.

Each week we saw different graphic programming thecnique and had to implement thus we needed/wanted in our final scene,
so let's get started!

## Triangle

![image](https://user-images.githubusercontent.com/71375990/179768284-5b9686e6-d962-4ae1-9ea8-929e58fea4b0.png)


## Square

![gif](https://github.com/PaulOwO/Portfolio.github.io/blob/02a3d8f235728be558430498f548190e9ad871d4/gif/ezgif.com-gif-maker%20(2).gif)
![image](https://user-images.githubusercontent.com/71375990/179768462-facfb500-d9c9-48a9-bc36-859986572c28.png)


## Texture

![image](https://user-images.githubusercontent.com/71375990/179745115-248daba2-09db-4006-a679-e35d046dd60c.png)

## Lighting 
![image](https://user-images.githubusercontent.com/71375990/179768731-092ceabe-0103-487c-b858-e8a18b145df6.png)
![image](https://user-images.githubusercontent.com/71375990/179768971-ac7b7109-312c-45f0-9f37-9f0bb56d34c1.png)

lighing map 
spotlight
pointlight dir light

## Model

![image](https://user-images.githubusercontent.com/71375990/179769376-0a20b970-ce75-4f99-a1b4-1fa72236a0d5.png)


## Frame Buffer 

![image](https://user-images.githubusercontent.com/71375990/179769553-ccf5a45b-4021-4e83-9a1d-ee6cf223a8a0.png)


## Stencil

![image](https://user-images.githubusercontent.com/71375990/179769841-d4e823a4-d38a-47ef-9be8-522a64f61c55.png)

## Cube Mapping

![image](https://user-images.githubusercontent.com/71375990/179770334-0d911b0e-7840-43f9-a475-c540f59a7855.png)

![image](https://user-images.githubusercontent.com/71375990/179773535-61be525d-2e7a-4545-85df-16821d4ff444.png)


## Normal Mapping

![image](https://user-images.githubusercontent.com/71375990/179770099-59ef1fc3-2ee6-49d2-9148-bd05f2edcd13.png)

![image](https://user-images.githubusercontent.com/71375990/179773268-06a2c26d-6cd1-4c47-872d-9e693d938da0.png)

![image](https://user-images.githubusercontent.com/71375990/179773353-c38ca374-4762-45d8-8b08-7f4dbe8b0d89.png)




## Shadow Mapping

![image](https://user-images.githubusercontent.com/71375990/179770514-ea955139-1a51-4ce1-baef-87f5ee616ede.png)

![image](https://user-images.githubusercontent.com/71375990/179773570-8f002a60-b217-49ee-a87d-d9f5457c13a5.png)




only work for directionnal light

## What more could have been done

### View frustrum culling
![image](https://user-images.githubusercontent.com/71375990/179771229-966a2c75-50d0-440b-b3d1-3879989746c8.png)

In the current scene the only "camera view" optimisation is the backface culling that that does not draw the back of the object.
View fustrum culling is an optimistaion that allow objects that are not in the camera to be not drawn and it's one i would have liked to had in my scene.

### Shadow Cube Mapping

As previously said in "Shadow Mapping", my shadow only work for directionnal lighting. But we could had it by simply using a cube map of shadow map instead of just one ! 
![image](https://user-images.githubusercontent.com/71375990/179773754-915ccec7-9d31-4361-9ace-73e11f9d937f.png)






