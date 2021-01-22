# ROI Analysis for Cortical Thickness (Using CIVET and the Human Brainnetome Atlas)

 ____________
  Hey there! 
 ------------
        \   ^__^
         \  (oo)\_______
            (__)\       )\/\  
                ||----w |
                ||     ||


This set of scripts is intended to be fed with:
a) a region from the Human Brainnetome Atlas (specifically, a region probability map),
b) cortical thickness files (outputted from CIVET) of a subjects group,
c) a cortical 3-D mesh representing the group average, and:
d) a .csv file with the variables associated with the subjects.

What this set of scripts does is:
--> convert BNA NIFTI probability map to MINC format 
--> convert it to a binary mask according to the desired treshold
--> use that mask to threshold individual CT measures
--> apply a linear model (and FDR correction) over the dataset according to the specified\ 
    dependent and independent variables.

It takes the following arguments:  

[1]: BNA probability map (e.g. 025.nii) 		
[2]: Directory where cortical thickness files (.txt, outputted from CIVET) are located
[3]: average cortical 3-D mesh (single hemisphere, e.g. lh_average.obj) 
[4]: dataframe (.csv file; important: IDs' column must be named: id 
[5]: Derired threshold for delimiting the probability map		
[6]: Predictor variable(s) (which can take the form accepted by R formulae; e.g. group+age)	
[7]: If comparing two groups, here you must input the code of the experimental group
[8]: And control group's code

Note: You should execute these scripts from the same directory where the required files are located.

marcoseliseo.da at gmail dot com
