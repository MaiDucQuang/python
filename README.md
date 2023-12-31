# # PyDTI -- a Python library for drug-target interaction prediction


# --------
# This package is written by:

# Mohammad Amin Khodamoradi

# Email: khodamoradi1992@gmail.com

# Department of Computer Science, Shahid Beheshti university, Tehran, Iran
# Joint Schoole of Bioinformatic, IPM, Tehran, Iran

# For any questions regarding to this library, please feel free to contact the author.

# --------
# PyDTI is implemented by Python 3.6.7, which can be downloaded from: https://www.python.org/downloads/release/python-367/. PyDTI requires several other Python packages, including Numpy, scikit-learn, Scipy, tensorflow == 1.7, edward, matplotlib, zmq, pyzmq  and pymatbridge (a bridge between Python and Matlab).

# The original packages can be found here:
# http://www.numpy.org/
# http://scikit-learn.org/stable/
# http://www.scipy.org/
# http://arokem.github.io/python-matlab-bridge/
# .
# .
# .

# Note that zmq, pyzmq and pymatbridge are only required by matlab implementations. The 64-bit Windows binaries of Numpy, scikit-learn, and Scipy can also be found at: http://www.lfd.uci.edu/~gohlke/pythonlibs/.

# 1. Add the folder "$PYTHON_ROOT$/Scipts/" to the system path. Please replace "$PYTHON_ROOT$" with the root folder of Python in your system.

# 2. Install the packages using pip utility. Open a console and type the following to install

# pip install numpy scipy scikit-learn


# --------
# To get the results of different methods, please run PyDTI.py by setting suitable values for the following parameters:

# 	--method 			set DTI prediction method
# 	--dataset: 			choose the benchmark dataset, i.e., nr, gpcr, ic, e
# 	--folder:			set the the folder that contains the datasets (default "datasets/")
# 	--csv:				choose the cross-validation setting, 1 for CVS1, 2 for CVS2, and 3 for CVS3, (default 1)
# 	--specify-arg:		0 for choosing optimal arguments, 1 for using default/specified arguments (default 1)
# 	--method-opt:		set arguments for each method (method ARGUMENTS have the form name=value)
# 	--predict-num:		0 for not predicting novel DTIs, a positive integer for predicting top-N novel DTIs (default 0)

# 	Here are some examples:

# 	(1) run a method with default arguments
# 		python PyDTI.py --method="nrlmf" --dataset="nr"
# 		python PyDTI.py --method="nrlmf" --dataset="nr" --cvs=2
# 		python PyDTI.py --method="nrlmf" --dataset="nr" --cvs=2 --specify-arg=1

# 	(2) run a method with specified arguments

# 		python PyDTI.py --method="nrlmf" --dataset="nr" --cvs=1 --specify-arg=1 --method-opt="r=100"

# 		python PyDTI.py --method="nrlmf" --dataset="nr" --cvs=1 --specify-arg=1 --method-opt="c=5 K1=5 K2=5 r=100 lambda_d=0.125 lambda_t=0.125 alpha=0.25 beta=0.125 theta=0.5"

# 		You can refer to lines 47-58 in the PyDTI.py for the default parameters of each DTI prediction method.

# 	(3) choose the optimal parameters for a method

# 		python PyDTI.py --method="nrlmf" --dataset="nr" --cvs=1 --specify-arg=0

# 	(4) predict the top-100 novel DTIs

# 		python PyDTI.py --method="nrlmf" --dataset="nr" --predict-num=100 --method-opt="r=100"

# 4. You can run sat_analysis.py for the statistical comparision between NRLMF and other baseline methods on all datasets, under different cross-validation settings. Note that you should first obtain the auc and aupr results of each method.

# 	python sta_analysis.py
