# DBSCAN-Clusterer-NND-Maxima
%This repository contains two codes utilized in this manuscript. 


%%DBSCAN Code for SMLM Data (dSTORM)
Description: This program inputs a dSTORM image and clusters the data using DBSCAN. The resulting clusters are then sorted, and the maximum diameter, area and nearest neighbor distance of each cluster is calculated. 

What you will need to run the program:

a reconstructed dSTORM image file containing all of the x and y coordinates from the acquisition.
A computer with a recommended 16 GB of RAM.

To use the program:

We recommend using the ImageJ plugin ThunderSTORM to reconstruct the data. Reconstruct the image how you normally would. Export the image containing all of the columns. The program inputs only the 3rd and 4th columns from the results file, which, in our case, is only the XY coordinates. The user may need to adjust the columns read by the program if their XY coordinates are not the 3rd and 4th columns.

Open the MATLAB code. We recommend you run this code by each section rather than all at once.

Run the first section. The program will prompt the user to select the .csv file containing the dSTORM image data.

Before running the next section, set the minPTS (minimum number of points) and the Epsilon (radius) in the DBSCAN section of the code. These parameters may need adjusting depending on your data. This section may be rerun until adequate clusters are achieved. The program then sorts all the clusters into a struct.

The next section calculates each cluster's maximum diameter, area, and nearest neighbor distance by finding the distance between each XY pair and others in the same cluster and then finding the maximum. These values are then stored in the same struct.

The final section of the code exports the data into a .csv file. 

Program complete.

%%Maxima NND Code (SIM)
Description: This code inputs two lists of X and Y coordinates obtained from ImageJ from two channels. The code then calculates the distance from each point to another and finds the shortest one aside from itself (when applicable). The shortest distance is called the nearest neighbor distance (NND). The program compares the nearest neighbor distances from each data set to itself and the other data set. 

To use the program:

Compile a list of XY coordinates you wish to compare between two data sets. 

Run the program. The program will prompt the user to select the .csv files containing the data sets.

The program will show histograms of the comparisons and export the values as .csv files. 
