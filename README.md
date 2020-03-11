# Finding Lane Lines on the Road



<img src="./test_videos_output/solidYellowLeft2.gif">



## Objective 

This is to make a image processing pipiline to detect lines on the road from front camera's video. 


## Process Pipleline

The process is as below 

- copy the original image 
- For the copied image, apply following processes
    - make the copied image into grey scale
    - apply Canny edge detection to detect edges
    - Hough transforming to detect lines 
    - Remove horizontal lines - since the lane lines are generally vertical 
    - Extend the lines to the edges to the iamge 
    - Mask to use only bottom half of the image (since upper half is not the road)
    - Blur the lines to have mean value 
- Merge original image and processed image 

## Result 

- See the gif video above 


## Shortcomings and improvement potentials of the pipeline

- The paramters are modified manually, so the stability for different places and settings are quite low. Using machine learning to optimize the parameters would be an option
- Since the detection is done for each image in the video, the noise level is high. Applying certain fileters, especially that compares the previous iamges would be effective. 




<hr>

## How to run 

- To run this code it is recommended a docker container that has all dependences 
    - pull the container from Docker Hub:   `docker pull udacity/carnd-term1-starter-kit`
    - Then run the container at the container at the directory where this repository is loacated: `docker run -it --rm --entrypoint "/run.sh" -p 8888:8888 -v ${pwd}:/src udacity/carnd-term1-starter-kit` 
    - Then you can run the Jupyter Notebook in this repository

