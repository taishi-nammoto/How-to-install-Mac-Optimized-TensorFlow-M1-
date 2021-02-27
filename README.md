# How to install Mac Optimized TensorFlow (M1) under Anaconda Environment

Since installing Tensorflow for M1 Macbook was not easy, I made a complete instruction to install TensorFlow 2.4.0-rc0.
Follow [this instruction](https://github.com/taishi-nammoto/How-to-install-Mac-Optimized-TensorFlow-M1-/blob/main/instruction.ipynb)

In the future, I will test the speed of TensorFlow 2.4.0-rc0.

## 1. Install Xcode Command Line Tools
Open terminal and type:
~~~
xcode-select --install
~~~

## 2. Download Miniforge3
[Click here](https://github.com/conda-forge/miniforge/releases/latest/download/Miniforge3-MacOSX-arm64.sh) to download Miniforge3

## 3. Make sure your current environment
Open a new terminal and type the following command
~~~
conda env list
~~~

Your current environment should be base under miniforge3. <br>
The output should have * /Users/username/miniforge3
~~~
base       * /Users/username/miniforge3
~~~

## 4. Set variables

Open Terminal and type (***Change the username with yours***):
~~~
sh /Users/username/Downloads/Miniforge3-MacOSX-arm64.sh
~~~

## 5. Download Tensorflow 2.4 (alpha 2)

[Click here](https://github.com/apple/tensorflow_macos/releases/download/v0.1alpha2/tensorflow_macos-0.1alpha2.tar.gz) to download Tensorflow 2.4 (alpha 2) <br>
Then, open the folder in Finder. You will get a folder named "tensorflow_macos"

Go to arm64 in the tensorflow_macos folder (***Change the username with yours***)
~~~
cd /Users/username/Downloads/tensorflow_macos/arm64
~~~

## 6. Create Conda environment

Open Terminal and type:
~~~
conda create --name tf24 
conda activate tf24
conda install -y python==3.8.6
conda install -y pandas matplotlib scikit-learn jupyterlab
~~~

## 7. Set variables

Open Terminal and type (***Change the username with yours***):
~~~
libs="/Users/username/Downloads/tensorflow_macos/arm64"
env="/Users/username/miniforge3/envs/tf24"
~~~

## Install TensorFlow 2.4 (alpha 2)

Open Terminal and type:
~~~
pip install --upgrade pip wheel setuptools cached-property six

pip install --upgrade -t "$env/lib/python3.8/site-packages/" --no-dependencies --force "$libs/grpcio-1.33.2-cp38-cp38-macosx_11_0_arm64.whl"

pip install --upgrade -t "$env/lib/python3.8/site-packages/" --no-dependencies --force "$libs/h5py-2.10.0-cp38-cp38-macosx_11_0_arm64.whl"

pip install --upgrade -t "$env/lib/python3.8/site-packages/" --no-dependencies --force "$libs/numpy-1.18.5-cp38-cp38-macosx_11_0_arm64.whl"

pip install --upgrade -t "$env/lib/python3.8/site-packages/" --no-dependencies --force "$libs/tensorflow_addons_macos-0.1a2-cp38-cp38-macosx_11_0_arm64.whl"

pip install absl-py astunparse flatbuffers gast google_pasta keras_preprocessing opt_einsum protobuf tensorflow_estimator termcolor typing_extensions wrapt wheel tensorboard typeguard

pip install --upgrade -t "$env/lib/python3.8/site-packages/" --no-dependencies --force "$libs/tensorflow_macos-0.1a2-cp38-cp38-macosx_11_0_arm64.whl"
~~~
