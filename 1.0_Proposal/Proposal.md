# FYP Project Proposal: AI Model for Vehicle Identification and Tracking 
* Authors: ASIM, Uzair Bin Colangoy \[[3035603071](mailto:u3560307@connect.hku.hk)\]
* Authors: YOUNG, Chak Fung \[[3035468160](mailto:u3546816@connect.hku.hk)\]

## Project Background

### General Background
Statistically speaking, there were 352 cases of Missing Motor Vehicles in Hong Kong during the period of Jan-Jun 2022 <sup>\[1\]</sup>. This is a phenomenon that is common in urban cities. In Europe, Missing Motor Vehicles caused 7.4 billion Dollars worth of damages in 2020 <sup>\[2\]</sup>.    
The current issue with Motor Vehicles Theft is that most countries still rely on old methods for identifying and tracking down stolen vehicles. For example in the United Kindom, law enforcement relies on methods such as random street checks, licsense plate checking of stolen vehicles and tips from third-party websites <sup>\[3\]</sup>.

### Technical Problem to be solved
Despite our advances in technology, the identification and spotting of stolen vehicles is a very labour-intensive and time-consuming task.    
It requires law enforcers to watch several hundreds of hours worth of surveillance videos to try and identify potential suspects of stolen vehicles and it takes even more time and energy to investage each potential suspect.    
By the time the stolen vehicle is identified it might be too late to efficiently intercept the vehicle.

The required effort grows exponentially in high density urban spaces where there may be multiple instances of Missing Motor Vehicles every year.

### Justification of work as a solution
By enabling cameras with an efficient vehicle detection system, we will be able to achieve two goals:
1. We will be able to reduce the amount of manpower required to locate and identify vehicles.    
By setting up cameras in high-traffic areas we can effectively watch a large number of vehicles and increase our odds of catching the stolen vehicles.
2. We will be able to create a map of stolen vehicles' paths.    
By aligning the spotting of the stolen vehicle along multiple cameras at a different locations, we will be able to map out the route of the stolen vehicle and possibly predict where it is most suitable to be intercepted.

### Project Objective
This project aims at creating a system that captures a live video stream of traffic and sends a time-stamped alert to authorities whenever a stolen vehicle is identified on the camera.    
Details such as the location, time and stolen vehicle id are relayed through the internet so that law enforcers can successfully track down the stolen vehicle.    

We are considering the creation of a UI interface to allow for easy deployment of the technology. As of current we are considering three options:    
1. A mobile app interface
2. A web app
3. A modular pipeline with a cli interface

We plan on choosing the option after experimenting the user experience of each of these.

### Project Methodology
#### 1. Overview
#### 2. Design Principles

#### 3. Hardware Architecture
##### 3.a. Hardware Selection
##### 3.b. Hardware Design and Layout

#### 4. Software Architecture
##### 4.a. Data Pipeline Overview
##### 4.b. Video Stream Input
##### 4.c. CNN network
##### 4.d. Database Design
##### 4.e. API Design
##### 4.f. Geospatial Visualization
##### 4.g User Interface design

#### 5. Data Collection
#### 6. Feature Extraction and Feature Engineering
#### 7. Model Training [Design|Architecture]
#### 8. Model Deployment

### Project Schedule and Milestones
<!-- The tentative schedule of the project, i.e. when and what will be achieved at various stages of the project. -->
## Biblography IEEE Standard
1. https://www.police.gov.hk/ppp_en/09_statistics/csc.html
2. https://en.wikipedia.org/wiki/Motor_vehicle_theft
3. https://en.wikipedia.org/wiki/Motor_vehicle_theft#Recovery_of_stolen_vehicles