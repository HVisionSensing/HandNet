# HandNet
Code repository for visualizing and manipulating HandNet.

Current project page is [here](http://www.cs.technion.ac.il/~twerd/HandNet/). 
Data needs to be downloaded from here (into respective folders):
* [Train (12.5 GB) ](http://gip.cs.technion.ac.il/files/HandNet/TrainData.rar)
* [Test (627 MB) ](http://gip.cs.technion.ac.il/files/HandNet/TestData.zip)
* [Validation (174 MB)](http://gip.cs.technion.ac.il/files/HandNet/ValidationData.zip)
* [Train_DerotGT (10.5 GB) ] (http://gip.cs.technion.ac.il/files/HandNet/TrainData_DerotGT.zip)
* [Validation_DerotGT (174 MB)] (http://gip.cs.technion.ac.il/files/HandNet/ValidationData_DerotGT.zip)
* [Test_Perturbed (521 MB) ](http://gip.cs.technion.ac.il/files/HandNet/TestData_Perturbed.zip)
* [Validation_Perturbed (144 MB)](http://gip.cs.technion.ac.il/files/HandNet/ValidationData_Perturbed.zip)

The DerotGT versions were generated by applying the ```derotate``` function on the ground truth
orientation of each example and then using ```rotateData```. This was then applied as an oracle to create the "ground truth
derotated" training and validation data. 
The Perturbed versions were generated by randomly rotating (uniformly between [-90,90]) the 
original data around the camera focal point in both 2D (in-plane) and 3D (around the z-axis)
also using the ```rotateData``` function. 
The reason for this was to ensure that the validation and test data were not similar to any of the 
training data. Perturbing the data in this way provides a very strong test of generalization
of any learning method on the original data. The perturbed versions of our results are those used in
in our BMVC'15 paper. They can be downloaded here:
* [Test_Perturbed_Results (167 MB)](http://gip.cs.technion.ac.il/files/HandNet/TestData_Perturbed_Results.mat)
* [Validation_Perturbed_Results (23 MB)](http://gip.cs.technion.ac.il/files/HandNet/ValidationData_Perturbed_Results.mat)

We dont recommend using the the non-perturbed version of the results but for the sake of completeness
we provide our results here:
* [Test_Results (167 MB)](http://gip.cs.technion.ac.il/files/HandNet/TestData_Results.mat)
* [Validation_Results (23 MB)](http://gip.cs.technion.ac.il/files/HandNet/ValidationData_Results.mat

## Explore the results
Run the script ShowResults.m after downloading the results data. This script can also easily be used to benchmark your own
results.

## Visualize HandNet data
For Matlab or Octave users just run DisplaySession.m to explore the data and change
the desired visualization accordingly. 

Current examples dont include Python. However the data is in MAT format
and reading it with Python is straightforward:

For example (assuming you downloaded the validation data to Validation folder):
```python
import scipy.io
data = scipy.io.loadmat('Validation/Data_0000000.mat')
```

## Citation
Please cite this paper ([LINK] (http://bmvc2015.swansea.ac.uk/proceedings/papers/paper033/index.html)) if you use HandNet in your work.

    @article{wetzlerBMVC15,
      Author = {Wetzler, Aaron and Slossberg, Ron and Kimmel, Ron},
      Journal = {British Machine Vision Conference},
      Title = {Rule of Thumb: Deep Derotation for Improved Fingertip Detection,},
      Year = {2015}
    }

	