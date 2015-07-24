---
title: "CodeBook Cleaning Data project"
author: "Rene Broekhoven"
date: "Thursday, July 23, 2015"
output: html_document
---

---
title: "Codebook template"
author: "Your name here"
date: "The date here"
output:
  html_document:
    keep_md: yes
---

## Project Description
Study on the effects of several activities on the human body using smartphone datagathering capablities.

##Study design and data processing
The experiments have been carried out with a group of 30 volunteers within an age bracket of 19-48 years. Each person performed six activities (WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING) wearing a smartphone (Samsung Galaxy S II) on the waist. Using its embedded accelerometer and gyroscope, we captured 3-axial linear acceleration and 3-axial angular velocity at a constant rate of 50Hz. The experiments have been video-recorded to label the data manually. The obtained dataset has been randomly partitioned into two sets, where 70% of the volunteers was selected for generating the training data and 30% the test data. 


###Collection of the raw data
The sensor signals (accelerometer and gyroscope) were pre-processed by applying noise filters and then sampled in fixed-width sliding windows of 2.56 sec and 50% overlap (128 readings/window). The sensor acceleration signal, which has gravitational and body motion components, was separated using a Butterworth low-pass filter into body acceleration and gravity. The gravitational force is assumed to have only low frequency components, therefore a filter with 0.3 Hz cutoff frequency was used. From each window, a vector of features was obtained by calculating variables from the time and frequency domain. 


##Creating the tidy datafile
From the original dataset only the mean and standard-deviation data were taken. Also al derived data from within the raw dataset were left out.

###Guide to create the tidy data file
Download the original data.
Merging the datafiles for training and test in one dataframe.
Selecting only the columns with mean and std.
Adding the "activity" (as a descriptive Factor) and "subject"" and merging them with the dataframe.
Making the variable names more easy to read and understand.
Summerizing the raw data per activity and subject as the mean of the individual measurments.



###Cleaning of the data
Goal of the script is to get a more simple set of the raw data with a summary (average) of the mean and std data variables.

See the README.md file or the run_analysis.R script

##Description of the variables in the tiny_data.txt file

 - Dimensions of the dataset are 181 75
 
 - Summary of the data :
               activity     subject     time_body_acceleration_mean...X
 LAYING            :30   Min.   : 1.0   Min.   :0.2348                 
 SITTING           :30   1st Qu.: 8.0   1st Qu.:0.2718                 
 STANDING          :30   Median :15.5   Median :0.2760                 
 WALKING           :30   Mean   :15.5   Mean   :0.2744                 
 WALKING_DOWNSTAIRS:30   3rd Qu.:23.0   3rd Qu.:0.2796                 
 WALKING_UPSTAIRS  :30   Max.   :30.0   Max.   :0.2885                 
 time_body_acceleration_mean...Y time_body_acceleration_mean...Z
 Min.   :-0.051871               Min.   :-0.14633               
 1st Qu.:-0.019833               1st Qu.:-0.11232               
 Median :-0.017513               Median :-0.10822               
 Mean   :-0.017824               Mean   :-0.10894               
 3rd Qu.:-0.015206               3rd Qu.:-0.10542               
 Max.   : 0.006485               Max.   :-0.08361               
 time_body_acceleration_std...X time_body_acceleration_std...Y
 Min.   :-0.9945                Min.   :-0.9835               
 1st Qu.:-0.9609                1st Qu.:-0.9148               
 Median :-0.6876                Median :-0.5708               
 Mean   :-0.6031                Mean   :-0.5006               
 3rd Qu.:-0.2624                3rd Qu.:-0.1453               
 Max.   : 0.2400                Max.   : 0.5917               
 time_body_acceleration_std...Z time_gravity_acceleration_mean...X
 Min.   :-0.9864                Min.   :-0.5290                   
 1st Qu.:-0.9191                1st Qu.: 0.4701                   
 Median :-0.6791                Median : 0.8568                   
 Mean   :-0.6067                Mean   : 0.6634                   
 3rd Qu.:-0.3463                3rd Qu.: 0.9241                   
 Max.   : 0.5534                Max.   : 0.9662                   
 time_gravity_acceleration_mean...Y time_gravity_acceleration_mean...Z
 Min.   :-0.472843                  Min.   :-0.47148                  
 1st Qu.:-0.218447                  1st Qu.:-0.06164                  
 Median :-0.088654                  Median : 0.04312                  
 Mean   : 0.003909                  Mean   : 0.09473                  
 3rd Qu.: 0.195040                  3rd Qu.: 0.21593                  
 Max.   : 0.732958                  Max.   : 0.84479                  
 time_gravity_acceleration_std...X time_gravity_acceleration_std...Y
 Min.   :-0.9926                   Min.   :-0.9948                  
 1st Qu.:-0.9780                   1st Qu.:-0.9708                  
 Median :-0.9676                   Median :-0.9552                  
 Mean   :-0.9649                   Mean   :-0.9543                  
 3rd Qu.:-0.9575                   3rd Qu.:-0.9419                  
 Max.   :-0.8859                   Max.   :-0.7511                  
 time_gravity_acceleration_std...Z time_body_acceleration_jerk_mean...X
 Min.   :-0.9903                   Min.   :0.03475                     
 1st Qu.:-0.9591                   1st Qu.:0.07370                     
 Median :-0.9443                   Median :0.07768                     
 Mean   :-0.9388                   Mean   :0.07883                     
 3rd Qu.:-0.9224                   3rd Qu.:0.08467                     
 Max.   :-0.7535                   Max.   :0.11455                     
 time_body_acceleration_jerk_mean...Y time_body_acceleration_jerk_mean...Z
 Min.   :-0.025519                    Min.   :-0.037964                   
 1st Qu.: 0.002132                    1st Qu.:-0.012129                   
 Median : 0.008483                    Median :-0.004818                   
 Mean   : 0.008146                    Mean   :-0.004682                   
 3rd Qu.: 0.013990                    3rd Qu.: 0.003326                   
 Max.   : 0.055642                    Max.   : 0.025154                   
 time_body_acceleration_jerk_std...X time_body_acceleration_jerk_std...Y
 Min.   :-0.9940                     Min.   :-0.9884                    
 1st Qu.:-0.9669                     1st Qu.:-0.9489                    
 Median :-0.7172                     Median :-0.6891                    
 Mean   :-0.6335                     Mean   :-0.5990                    
 3rd Qu.:-0.3515                     3rd Qu.:-0.3034                    
 Max.   : 0.1403                     Max.   : 0.2624                    
 time_body_acceleration_jerk_std...Z time_body_gyroscope_mean...X
 Min.   :-0.99157                    Min.   :-0.12545            
 1st Qu.:-0.96634                    1st Qu.:-0.04316            
 Median :-0.81742                    Median :-0.03012            
 Mean   :-0.75618                    Mean   :-0.03028            
 3rd Qu.:-0.60569                    3rd Qu.:-0.01923            
 Max.   :-0.05565                    Max.   : 0.10860            
 time_body_gyroscope_mean...Y time_body_gyroscope_mean...Z time_body_gyroscope_std...X
 Min.   :-0.190316            Min.   :-0.08741             Min.   :-0.9908            
 1st Qu.:-0.087160            1st Qu.: 0.07794             1st Qu.:-0.9543            
 Median :-0.075270            Median : 0.08702             Median :-0.7471            
 Mean   :-0.075188            Mean   : 0.08790             Mean   :-0.7172            
 3rd Qu.:-0.062944            3rd Qu.: 0.10066             3rd Qu.:-0.5023            
 Max.   :-0.002533            Max.   : 0.15745             Max.   :-0.0315            
 time_body_gyroscope_std...Y time_body_gyroscope_std...Z
 Min.   :-0.9899             Min.   :-0.9898            
 1st Qu.:-0.9436             1st Qu.:-0.9400            
 Median :-0.7246             Median :-0.6947            
 Mean   :-0.6754             Mean   :-0.6478            
 3rd Qu.:-0.4801             3rd Qu.:-0.4197            
 Max.   : 0.3559             Max.   : 0.4891            
 time_body_gyroscope_jerk_mean...X time_body_gyroscope_jerk_mean...Y
 Min.   :-0.15176                  Min.   :-0.07737                 
 1st Qu.:-0.10511                  1st Qu.:-0.04590                 
 Median :-0.09765                  Median :-0.04094                 
 Mean   :-0.09682                  Mean   :-0.04221                 
 3rd Qu.:-0.09228                  3rd Qu.:-0.03831                 
 Max.   :-0.03631                  Max.   :-0.01762                 
 time_body_gyroscope_jerk_mean...Z time_body_gyroscope_jerk_std...X
 Min.   :-0.08253                  Min.   :-0.99491                
 1st Qu.:-0.06030                  1st Qu.:-0.96257                
 Median :-0.05491                  Median :-0.79311                
 Mean   :-0.05485                  Mean   :-0.72462                
 3rd Qu.:-0.05022                  3rd Qu.:-0.55076                
 Max.   :-0.01084                  Max.   : 0.01999                
 time_body_gyroscope_jerk_std...Y time_body_gyroscope_jerk_std...Z
 Min.   :-0.99590                 Min.   :-0.99456                
 1st Qu.:-0.96867                 1st Qu.:-0.96857                
 Median :-0.85865                 Median :-0.80302                
 Mean   :-0.77853                 Mean   :-0.73251                
 3rd Qu.:-0.65416                 3rd Qu.:-0.55775                
 Max.   : 0.05309                 Max.   :-0.01026                
 time_body_acceleration_magnitude_mean.. time_body_acceleration_magnitude_std..
 Min.   :-0.9871                         Min.   :-0.9851                       
 1st Qu.:-0.9257                         1st Qu.:-0.9193                       
 Median :-0.6258                         Median :-0.6849                       
 Mean   :-0.5417                         Mean   :-0.5858                       
 3rd Qu.:-0.1935                         3rd Qu.:-0.2840                       
 Max.   : 0.2616                         Max.   : 0.1904                       
 time_gravity_acceleration_magnitude_mean.. time_gravity_acceleration_magnitude_std..
 Min.   :-0.9871                            Min.   :-0.9851                          
 1st Qu.:-0.9257                            1st Qu.:-0.9193                          
 Median :-0.6258                            Median :-0.6849                          
 Mean   :-0.5417                            Mean   :-0.5858                          
 3rd Qu.:-0.1935                            3rd Qu.:-0.2840                          
 Max.   : 0.2616                            Max.   : 0.1904                          
 time_body_acceleration_jerk_magnitude_mean..
 Min.   :-0.9926                             
 1st Qu.:-0.9637                             
 Median :-0.7277                             
 Mean   :-0.6421                             
 3rd Qu.:-0.3710                             
 Max.   : 0.1390                             
 time_body_acceleration_jerk_magnitude_std.. time_body_gyroscope_magnitude_mean..
 Min.   :-0.9930                             Min.   :-0.9769                     
 1st Qu.:-0.9554                             1st Qu.:-0.9215                     
 Median :-0.7133                             Median :-0.6537                     
 Mean   :-0.6198                             Mean   :-0.5992                     
 3rd Qu.:-0.3298                             3rd Qu.:-0.3458                     
 Max.   : 0.1195                             Max.   : 0.3037                     
 time_body_gyroscope_magnitude_std.. time_body_gyroscope_jerk_magnitude_mean..
 Min.   :-0.9781                     Min.   :-0.9964                          
 1st Qu.:-0.9236                     1st Qu.:-0.9712                          
 Median :-0.7105                     Median :-0.8257                          
 Mean   :-0.6553                     Mean   :-0.7549                          
 3rd Qu.:-0.4377                     3rd Qu.:-0.5826                          
 Max.   : 0.1894                     Max.   :-0.1165                          
 time_body_gyroscope_jerk_magnitude_std.. frequency_body_acceleration_mean...X
 Min.   :-0.99590                         Min.   :-0.9939                     
 1st Qu.:-0.96599                         1st Qu.:-0.9610                     
 Median :-0.84587                         Median :-0.7025                     
 Mean   :-0.77019                         Mean   :-0.6174                     
 3rd Qu.:-0.62425                         3rd Qu.:-0.2905                     
 Max.   :-0.02664                         Max.   : 0.1362                     
 frequency_body_acceleration_mean...Y frequency_body_acceleration_mean...Z
 Min.   :-0.9849                      Min.   :-0.9870                     
 1st Qu.:-0.9224                      1st Qu.:-0.9373                     
 Median :-0.6082                      Median :-0.7367                     
 Mean   :-0.5281                      Mean   :-0.6579                     
 3rd Qu.:-0.1613                      3rd Qu.:-0.4442                     
 Max.   : 0.4934                      Max.   : 0.1934                     
 frequency_body_acceleration_std...X frequency_body_acceleration_std...Y
 Min.   :-0.9949                     Min.   :-0.9842                    
 1st Qu.:-0.9599                     1st Qu.:-0.9135                    
 Median :-0.6842                     Median :-0.5732                    
 Mean   :-0.5990                     Mean   :-0.5193                    
 3rd Qu.:-0.2796                     3rd Qu.:-0.2040                    
 Max.   : 0.2761                     Max.   : 0.5393                    
 frequency_body_acceleration_std...Z frequency_body_acceleration_jerk_mean...X
 Min.   :-0.9865                     Min.   :-0.99408                         
 1st Qu.:-0.9173                     1st Qu.:-0.96770                         
 Median :-0.6773                     Median :-0.73252                         
 Mean   :-0.6123                     Mean   :-0.65061                         
 3rd Qu.:-0.3642                     3rd Qu.:-0.37004                         
 Max.   : 0.6092                     Max.   : 0.07395                         
 frequency_body_acceleration_jerk_mean...Y frequency_body_acceleration_jerk_mean...Z
 Min.   :-0.9881                           Min.   :-0.99006                         
 1st Qu.:-0.9498                           1st Qu.:-0.96410                         
 Median :-0.6980                           Median :-0.79914                         
 Mean   :-0.6205                           Mean   :-0.73674                         
 3rd Qu.:-0.3547                           3rd Qu.:-0.56727                         
 Max.   : 0.1813                           Max.   : 0.04056                         
 frequency_body_acceleration_jerk_std...X frequency_body_acceleration_jerk_std...Y
 Min.   :-0.9945                          Min.   :-0.9896                         
 1st Qu.:-0.9691                          1st Qu.:-0.9515                         
 Median :-0.7317                          Median :-0.6908                         
 Mean   :-0.6491                          Mean   :-0.6032                         
 3rd Qu.:-0.3777                          3rd Qu.:-0.2958                         
 Max.   : 0.1067                          Max.   : 0.2647                         
 frequency_body_acceleration_jerk_std...Z frequency_body_gyroscope_mean...X
 Min.   :-0.9916                          Min.   :-0.9893                  
 1st Qu.:-0.9692                          1st Qu.:-0.9480                  
 Median :-0.8271                          Median :-0.7074                  
 Mean   :-0.7745                          Mean   :-0.6662                  
 3rd Qu.:-0.6324                          3rd Qu.:-0.4219                  
 Max.   :-0.1544                          Max.   : 0.1960                  
 frequency_body_gyroscope_mean...Y frequency_body_gyroscope_mean...Z
 Min.   :-0.9911                   Min.   :-0.9888                  
 1st Qu.:-0.9535                   1st Qu.:-0.9439                  
 Median :-0.7741                   Median :-0.7083                  
 Mean   :-0.6983                   Mean   :-0.6366                  
 3rd Qu.:-0.5130                   3rd Qu.:-0.4081                  
 Max.   : 0.1792                   Max.   : 0.2939                  
 frequency_body_gyroscope_std...X frequency_body_gyroscope_std...Y
 Min.   :-0.9913                  Min.   :-0.9891                 
 1st Qu.:-0.9574                  1st Qu.:-0.9410                 
 Median :-0.7587                  Median :-0.7176                 
 Mean   :-0.7351                  Mean   :-0.6673                 
 3rd Qu.:-0.5364                  3rd Qu.:-0.4776                 
 Max.   :-0.1067                  Max.   : 0.4884                 
 frequency_body_gyroscope_std...Z frequency_body_acceleration_magnitude_mean..
 Min.   :-0.9911                  Min.   :-0.9872                             
 1st Qu.:-0.9448                  1st Qu.:-0.9317                             
 Median :-0.7226                  Median :-0.6639                             
 Mean   :-0.6857                  Mean   :-0.5793                             
 3rd Qu.:-0.4745                  3rd Qu.:-0.2529                             
 Max.   : 0.4173                  Max.   : 0.2181                             
 frequency_body_acceleration_magnitude_std..
 Min.   :-0.9854511                         
 1st Qu.:-0.9235241                         
 Median :-0.7359995                         
 Mean   :-0.6557012                         
 3rd Qu.:-0.4164302                         
 Max.   : 0.0005415                         
 frequency_body_body_acceleration_jerk_magnitude_mean..
 Min.   :-0.9924                                       
 1st Qu.:-0.9545                                       
 Median :-0.7042                                       
 Mean   :-0.6128                                       
 3rd Qu.:-0.3100                                       
 Max.   : 0.1667                                       
 frequency_body_body_acceleration_jerk_magnitude_std..
 Min.   :-0.99269                                     
 1st Qu.:-0.95539                                     
 Median :-0.72252                                     
 Mean   :-0.63222                                     
 3rd Qu.:-0.35504                                     
 Max.   : 0.09385                                     
 frequency_body_body_gyroscope_magnitude_mean..
 Min.   :-0.9842                               
 1st Qu.:-0.9414                               
 Median :-0.7518                               
 Mean   :-0.6894                               
 3rd Qu.:-0.4847                               
 Max.   : 0.0459                               
 frequency_body_body_gyroscope_magnitude_std..
 Min.   :-0.9783                              
 1st Qu.:-0.9245                              
 Median :-0.7381                              
 Mean   :-0.6945                              
 3rd Qu.:-0.5182                              
 Max.   : 0.1088                              
 frequency_body_body_gyroscope_jerk_magnitude_mean..
 Min.   :-0.99600                                   
 1st Qu.:-0.96638                                   
 Median :-0.84333                                   
 Mean   :-0.77240                                   
 3rd Qu.:-0.62422                                   
 Max.   :-0.03189                                   
 frequency_body_body_gyroscope_jerk_magnitude_std..
 Min.   :-0.99573                                  
 1st Qu.:-0.96725                                  
 Median :-0.85320                                  
 Mean   :-0.78442                                  
 3rd Qu.:-0.65187                                  
 Max.   :-0.09892                                  
 angle.t_body_accelerationMean.gravity.
 Min.   :-0.100554                     
 1st Qu.:-0.013471                     
 Median : 0.009415                     
 Mean   : 0.007994                     
 3rd Qu.: 0.027223                     
 Max.   : 0.099552                     
 angle.t_body_acceleration_jerkMean..gravity_mean.
 Min.   :-0.136374                                
 1st Qu.:-0.019413                                
 Median : 0.006206                                
 Mean   : 0.002584                                
 3rd Qu.: 0.024558                                
 Max.   : 0.160354                                
 angle.t_body_gyroscopeMean.gravity_mean. angle.t_body_gyroscope_jerkMean.gravity_mean.
 Min.   :-0.36060                         Min.   :-0.1546346                           
 1st Qu.:-0.02651                         1st Qu.:-0.0486234                           
 Median : 0.02355                         Median :-0.0004307                           
 Mean   : 0.01749                         Mean   :-0.0087300                           
 3rd Qu.: 0.06807                         3rd Qu.: 0.0277883                           
 Max.   : 0.34575                         Max.   : 0.1266475                           
 angle.X.gravity_mean. angle.Y.gravity_mean. angle.Z.gravity_mean.
 Min.   :-0.9029       Min.   :-0.65233      Min.   :-0.67598     
 1st Qu.:-0.7363       1st Qu.:-0.07694      1st Qu.:-0.15045     
 Median :-0.6297       Median : 0.14395      Median :-0.01336     
 Mean   :-0.4900       Mean   : 0.06292      Mean   :-0.05637     
 3rd Qu.:-0.3123       3rd Qu.: 0.23282      3rd Qu.: 0.06427     
 Max.   : 0.6310       Max.   : 0.41932      Max.   : 0.37080     
 
 - Variables present in the dataset :
 
 [1] "activity"                                              
 [2] "subject"                                               
 [3] "time_body_acceleration_mean...X"                       
 [4] "time_body_acceleration_mean...Y"                       
 [5] "time_body_acceleration_mean...Z"                       
 [6] "time_body_acceleration_std...X"                        
 [7] "time_body_acceleration_std...Y"                        
 [8] "time_body_acceleration_std...Z"                        
 [9] "time_gravity_acceleration_mean...X"                    
[10] "time_gravity_acceleration_mean...Y"                    
[11] "time_gravity_acceleration_mean...Z"                    
[12] "time_gravity_acceleration_std...X"                     
[13] "time_gravity_acceleration_std...Y"                     
[14] "time_gravity_acceleration_std...Z"                     
[15] "time_body_acceleration_jerk_mean...X"                  
[16] "time_body_acceleration_jerk_mean...Y"                  
[17] "time_body_acceleration_jerk_mean...Z"                  
[18] "time_body_acceleration_jerk_std...X"                   
[19] "time_body_acceleration_jerk_std...Y"                   
[20] "time_body_acceleration_jerk_std...Z"                   
[21] "time_body_gyroscope_mean...X"                          
[22] "time_body_gyroscope_mean...Y"                          
[23] "time_body_gyroscope_mean...Z"                          
[24] "time_body_gyroscope_std...X"                           
[25] "time_body_gyroscope_std...Y"                           
[26] "time_body_gyroscope_std...Z"                           
[27] "time_body_gyroscope_jerk_mean...X"                     
[28] "time_body_gyroscope_jerk_mean...Y"                     
[29] "time_body_gyroscope_jerk_mean...Z"                     
[30] "time_body_gyroscope_jerk_std...X"                      
[31] "time_body_gyroscope_jerk_std...Y"                      
[32] "time_body_gyroscope_jerk_std...Z"                      
[33] "time_body_acceleration_magnitude_mean.."               
[34] "time_body_acceleration_magnitude_std.."                
[35] "time_gravity_acceleration_magnitude_mean.."            
[36] "time_gravity_acceleration_magnitude_std.."             
[37] "time_body_acceleration_jerk_magnitude_mean.."          
[38] "time_body_acceleration_jerk_magnitude_std.."           
[39] "time_body_gyroscope_magnitude_mean.."                  
[40] "time_body_gyroscope_magnitude_std.."                   
[41] "time_body_gyroscope_jerk_magnitude_mean.."             
[42] "time_body_gyroscope_jerk_magnitude_std.."              
[43] "frequency_body_acceleration_mean...X"                  
[44] "frequency_body_acceleration_mean...Y"                  
[45] "frequency_body_acceleration_mean...Z"                  
[46] "frequency_body_acceleration_std...X"                   
[47] "frequency_body_acceleration_std...Y"                   
[48] "frequency_body_acceleration_std...Z"                   
[49] "frequency_body_acceleration_jerk_mean...X"             
[50] "frequency_body_acceleration_jerk_mean...Y"             
[51] "frequency_body_acceleration_jerk_mean...Z"             
[52] "frequency_body_acceleration_jerk_std...X"              
[53] "frequency_body_acceleration_jerk_std...Y"              
[54] "frequency_body_acceleration_jerk_std...Z"              
[55] "frequency_body_gyroscope_mean...X"                     
[56] "frequency_body_gyroscope_mean...Y"                     
[57] "frequency_body_gyroscope_mean...Z"                     
[58] "frequency_body_gyroscope_std...X"                      
[59] "frequency_body_gyroscope_std...Y"                      
[60] "frequency_body_gyroscope_std...Z"                      
[61] "frequency_body_acceleration_magnitude_mean.."          
[62] "frequency_body_acceleration_magnitude_std.."           
[63] "frequency_body_body_acceleration_jerk_magnitude_mean.."
[64] "frequency_body_body_acceleration_jerk_magnitude_std.." 
[65] "frequency_body_body_gyroscope_magnitude_mean.."        
[66] "frequency_body_body_gyroscope_magnitude_std.."         
[67] "frequency_body_body_gyroscope_jerk_magnitude_mean.."   
[68] "frequency_body_body_gyroscope_jerk_magnitude_std.."    
[69] "angle.t_body_accelerationMean.gravity."                
[70] "angle.t_body_acceleration_jerkMean..gravity_mean."     
[71] "angle.t_body_gyroscopeMean.gravity_mean."              
[72] "angle.t_body_gyroscope_jerkMean.gravity_mean."         
[73] "angle.X.gravity_mean."                                 
[74] "angle.Y.gravity_mean."                                 
[75] "angle.Z.gravity_mean."      


###Variable 1
Describes the activity performed by a subject
Class : Factor Character
    
Unique values/levels : 
1 WALKING
2 WALKING_UPSTAIRS
3 WALKING_DOWNSTAIRS
4 SITTING
5 STANDING
6 LAYING
 
###Variable 2
Id of a subject (30 subjects)
Class : number integer
    
###Variable 3 through 68
Recorded or calculated data form the smartphone.
Class : number float
The features selected come from the accelerometer and gyroscope 3-axial raw signals time_acceleration-XYZ and time_Gyroscope-XYZ. 
The time domain signals were captured at a constant rate of 50 Hz. 
Then they were filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise. 
Similarly, the acceleration signal was separated into body and gravity acceleration signals (time_body_acceleration-XYZ and time_gravity_acceleration-XYZ) using another low pass Butterworth filter with a corner frequency of 0.3 Hz. 

The body linear acceleration and angular velocity were derived in time to obtain Jerk signals (time_body_acceleration_jerk-XYZ and time_body_gyroscope_jerk-XYZ). 
Also the magnitude of these three-dimensional signals were calculated using the Euclidean norm (time_body_acceleration_magnitude, time_gravity_acceleration_magnitude, time_body_acceleration_Jerk_magnitude, time_body_gyroscope_magnitude, time_body_gyroscope_jerk_magnitude). 

Finally a Fast Fourier Transform (FFT) was applied to some of these signals producing frequency domain signal.(variables staring with "frequency") 
These signals were used to estimate variables of the feature vector for each pattern:  

'-XYZ' is used to denote 3-axial signals in the X, Y and Z directions.


###Variable 69 through 75
Recorded or calculated data form the smartphone.
Class : number float
The set of variables that were estimated from the variables 3:68.
Angle is the angle between two vectors. (in the X, Y, Z direction)


