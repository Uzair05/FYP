# FYP Project Proposal: AI Model for Vehicle Identification and Tracking 
* Authors: ASIM, Uzair Bin Colangoy \[[3035603071](mailto:u3560307@connect.hku.hk)\]
* Authors: YOUNG, Chak Fung \[[3035468160](mailto:u3546816@connect.hku.hk)\]

## Project Background

### General Background
Statistically speaking, there were 352 cases of Missing Motor Vehicles in Hong Kong during the period of Jan-Jun 2022 \[1\]. This is a phenomenon that is common in urban cities. In Europe, Missing Motor Vehicles caused 7.4 billion Dollars worth of damages in 2020 \[2\].  
The current issue with Motor Vehicles Theft is that most countries still rely on old methods for identifying and tracking down stolen vehicles. For example in the United Kindom, law enforcement relies on methods such as random street checks, licence plate checking of stolen vehicles and tips from third-party websites \[2\].

### Technical Problem to be solved
Despite our advances in technology, the identification and spotting of stolen vehicles is a very labour-intensive and time-consuming task.  
It requires law enforcers to watch several hundreds of hours worth of surveillance videos to try and identify potential suspects of stolen vehicles and it takes even more time and energy to investigate each potential suspect.  
By the time the stolen vehicle is identified, it might be too late to efficiently intercept the vehicle.

The required effort grows exponentially in high-density urban spaces where there may be multiple instances of Missing Motor Vehicles every year.

### Justification of work as a solution
By enabling cameras with an efficient vehicle detection system, we will be able to achieve two goals:
1. We will be able to reduce the amount of manpower required to locate and identify vehicles.  
By setting up cameras in high-traffic areas we can effectively watch a large number of vehicles and increase our odds of catching the stolen vehicles.
2. We will be able to create a map of stolen vehicles' paths.  
By aligning the spotting of the stolen vehicle along multiple cameras at a different locations, we will be able to map out the route of the stolen vehicle and possibly predict where it is most suitable to be intercepted.

## Project Objective
This project aims at creating a system that captures a live video stream of traffic and sends a time-stamped alert to authorities whenever a stolen vehicle is identified on the camera.  
Details such as the location, time and stolen vehicle id are relayed through the internet so that law enforcers can successfully track down the stolen vehicle.  

We are considering the creation of a UI interface to allow for easy deployment of the technology. As of current, we are considering three options:  
1. A mobile app interface
2. A web app
3. A modular pipeline with a CLI interface

We plan on choosing the option after experimenting with the user experience of each of these.

## Project Methodology

### 1. Overview
In this section of Methodology, we will first discuss the design principles, before looking at the hardware architecture, software architecture, data collection and manipulation, training and finally deployment.  
As of current, these decisions are still in the preliminary design phase and we intend to correct and amend any design changes as we proceed with the development.

### 2. Design Principles
We want to obtain three additional goals alongside achieving our project objective. 
* We wish to be able to create a scalable project that can be upscaled to accommodate new features and functionality.  
For this, we have to take into consideration the design of our project and the open-source tools used in the project.
* We wish to be able to ensure that the project is modular and parallelizable so that it can run multiple, independent, instances across multiple cameras.   
This would help enable the system to utilize more computing power efficiently and it would be easier to upscale the project in multiple small phases.
* We wish that the project is easy to maintain.  
This can be ensured by following strict coding etiquettes and robust algorithm design.

### 3. Hardware Architecture
#### 3.a. Hardware Selection
The required hardware for the project is a set of cameras and computers.  
The camera quality has to mimic street cameras, in this scenario we can simply use the cameras of our smartphones and process the image frames to downscale the video quality.  
For the model training and testing, we plan to use the University's GPU Cluster.

#### 3.b. Hardware Design and Layout
We plan to set up the camera in an elevated position with high visibility. The camera should be able to have a clear view of the car and ideally be able to see the License plate as well.  
We plan to take multiple videos with varying angles for better data quality.

### 4. Software Architecture
#### 4.a. Data Pipeline Overview
The video feed from the cameras is processed and fed to a trained CNN model. This extracts the details of the vehicle such as make, model, colour and licence plate number. These details can then be compared against a database of known missing vehicles. If a search result has a very high probability of being a stolen vehicle then a POST request is sent to law enforcers to notify them of details concerning the vehicle and its sighting.

#### 4.b. Video Stream Input
The video stream input will be manipulated and processed to resemble the quality of street cameras.  
We plan to use methods such as gaussian filters and maxpooling to try and downscale the image quality. While this will help train the model to adapt to realistic scenarios it will also help our model train faster and avoid unnecessary power consumption.  
We also plan to adjust the colour range to match the quality of street cameras as well.

#### 4.c. CNN network
In this project, we plan to make use of two techniques to help improve our experiments. We plan to make use of transfer learning to take advantage of existing pre-trained networks.  
We also plan to use Keras auto-tuning to help us decide on appropriate hyperparameters.

#### 4.d. Database Design
The project will SQLAlchemy for the database engine, but we might change it if we find a better option in the future.  
While the current schema design has not yet been finalized, we plan to make use of a "distance-mechanism" to help calculate the closest match. This may help the model avoid the pitfall of false negatives.

### 5. Model Training Design
We plan to use a Stratified K-Fold method for training our model and plan to score it against an F1 score. By scoring our model against an F1 score we can make achieve an accurate understanding of performance while taking false positives and false negatives into account.

### 6. Model Deployment
For this project, we will deploy the model onto an AWS server so that we can test the model understands real-life circumstances. This will also help us debug any issues we might face in deployment and help us counter these problems.

We will also be able to test the models' ability of parallelization.

## Project Schedule and Milestones
Milestone | Expected Date
:---|:---:
Proposal Creation | 02/10/2022
Website Creation | 02/10/2022
Data Collection | 23/10/2022
Model Creation | 25/10/2022
Data Labelling | 30/10/2022
Preliminary Model Testing and Tuning | 13/11/2022
Interim Report | 25/11/2022


## Bibliography IEEE Standard
\[1\] Hong Kong Police Force. (2022, Sep 1). Crime Statistics Comparison \[Online\]. Available: https://www.police.gov.hk/ppp_en/09_statistics/csc.html \[Accessed: 2022 Oct 01\]  
\[2\] Wikipedia. (2022, Sep 29). Motor vehicle theft \[Online\]. Available: https://en.wikipedia.org/wiki/Motor_vehicle_theft \[Accessed: 2022 Oct 01\]