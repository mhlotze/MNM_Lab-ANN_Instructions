# ANN-Instructions
This instruction sheet is intended to be used to help students working on the ANN model for HECC phase predictions in the Modeling of Nuclear Materials research group.

## How to run
After downloading the folder from github, follow the steps bellow to run the ANN.

### Install Conda
If you do not have Conda installed on your computer, make sure to install as we will need to create a Conda environment to run the ANN

### Install Tensorflow
The ANN only runs in a tensorflow (tf) environment, so tensorflow must be installed before doing anything else.  
`conda install tf`

### Create a New Environment
The ANN will only run if a specialized python environment is created. Attempting to run the ANN in the base environment will result in errors. First, create this environment by running the command:  
`conda create --name tf tensorflow`  
After creating the environment, it will need to be initialized for Bash; run
`conda initialize bash`
Next, make sure that you are operating out of it by running:  
`conda activate tf`  
You will know that you are successful if the blue dot switched from the base environment to the tf environment.

### Install Additional Libraries
Install any additional libraries within the tf environment. The following were libraries I had to install, but you may need to install more:
`conda install conda-forge::pymatgen`  
`conda install anaconda::scikit-learn`

### Run!
To test that the ANN is working run the following line of code:  
`WRAPT_DISABLE_EXTENSIONS=true python predict_modify.py --formula TiVCrNbTa VCrNbMoTa TiVCrZrMo` 
If the ANN is working properly it should output:  
```
Phase code: Single phase: 0.0; multi phase: 1.0

Prediction(s) from ANN: 0.049 0.047 1.000
Prediction(s) from SVM: 0.000 0.000 1.000
```
As shown in the example above, multiple formulas can be included at a single time and the output will show the results of each. This can save time as you do not need to run a new calculation for each individual formula.


## Common Errors
-make sure to run the code from the tensorflow environment instead of the base environment. You know you are doing this correctly when the dot next to the tf environment is blue.  
-if you are running into a path error try copying the path directly from the file you want and pasting it

## Questions?
contact me at emals2@illinois.edu  
(thank you Wenwen for showing me how to run the code!)
