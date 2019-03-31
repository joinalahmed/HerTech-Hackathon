# HerTech-Hackathon
This is our solution submission for the Hertech hackathon:
https://hertech.hackerearth.com/

We chose problem statement 2: 

-----------------------------------------------------------------------------------------------------------------------------
Safe Zone: For women who self-drive to work, AI could utilize a range of traffic data sets on safe routes to travel through 
humanlike decisions on route selection. With information on dynamic tolls and traffic flows on links, AI can identify public spots,
safe zones around the area for safety, alleviating cities of this major issue.
-----------------------------------------------------------------------------------------------------------------------------

Our solution to the problem was to come up with Safety Index, for as many locations as possible. Using these safety index, 
find routes which has the highest safety metric for the selected source and destination.

The product would be rolled out in  3 phases:

Phase 1: The user selects source and destination and we use Google maps API's to get all possible routes. For each of the route 
returned, the intermediate points in the route are also returned. For each of those intermediate points returned, we calculate 
a safety index. We define a set of negative and positive features to come up with this safety index. For e.g., number of police 
stations, gas stations, hospitals contribute as positive features. The number of accidents, crime rate,etc would contribute to 
negative features. We intend to use as much real-time data and hence are picking these feature attributes with Google map API's. 
Once we have safety index calculated for all the intermediate points, we sum them up with user-defined weights for each feature 
and calculate a safety score for the whole route. Similar calculations are performed for all the suggested routes and the route
with highest safety score is suggested to the user to be the safest.

Phase 2: As we roll out Phase 1, we ask users for their feedback. This feedback is incorporated into the system. For e.g., we 
assume that a petrol bunk is a positive feature. But if there is a petrol bunk which was unsafe for a user when she approached, 
she will mark it as unsafe. This would be incorporated in the system. We intend to have a community of users who actively give us 
such feedback. This let's us come up with a more validated dataset. 

Phase 3: We would want to collaborate with government authorities to get real-time data. For e.g., if there is an accident, we 
would want to get an alert from the traffic department about the location of accident. Static data is not much of use here and hence
we would approach as many civic and government bodies to get live date.

At the end of Phase 3, we will have a dataset which will have real-time data from Phase 1 and phase 3 and user-feedback data from 
phase 2.Clubbing all three, we will be able to generate a labeled dataset which can be used to calculate safety scores real-time.
The system would evolve each day with the feedback that it gets. 
