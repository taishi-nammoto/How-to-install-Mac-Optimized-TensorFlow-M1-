# How to install Mac Optimized TensorFlow (M1) under Anaconda Environment

Since installing Tensorflow for M1 Macbook was not easy, I made a complete instruction to install TensorFlow 2.4.0-rc0.
Follow [this instruction](https://github.com/taishi-nammoto/How-to-install-Mac-Optimized-TensorFlow-M1-/blob/main/instruction.ipynb)

In the future, I will test the speed of TensorFlow 2.4.0-rc0.

{
 "cells": [
  {
   "cell_type": "markdown",
   "id": "technological-school",
   "metadata": {},
   "source": [
    "# How to install Mac Optimized TensorFlow (M1) under Anaconda Environment\n",
    "<hr>"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "tamil-wednesday",
   "metadata": {},
   "source": [
    "## 1. Install Xcode Command Line Tools"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "competent-venture",
   "metadata": {},
   "outputs": [],
   "source": [
    "!xcode-select --install"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "timely-challenge",
   "metadata": {},
   "source": [
    "## 2. Download Miniforge3\n",
    "\n",
    "[Click here](https://github.com/conda-forge/miniforge/releases/latest/download/Miniforge3-MacOSX-arm64.sh) to download Miniforge3"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "hungry-wound",
   "metadata": {},
   "source": [
    "## 3. Make sure your current environment\n",
    "\n",
    "Open a new terminal and type the following command\n",
    "~~~\n",
    "conda env list\n",
    "~~~"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "textile-discrimination",
   "metadata": {},
   "source": [
    "Your current environment should be base under miniforge3. \n",
    "~~~\n",
    "base                    * /Users/username/miniforge3\n",
    "~~~"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "honey-glenn",
   "metadata": {},
   "source": [
    "## 4. Set variables\n",
    "\n",
    "Open Terminal and type (***Change the username with yours***):\n",
    "~~~\n",
    "sh /Users/username/Downloads/Miniforge3-MacOSX-arm64.sh\n",
    "~~~"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "enormous-appraisal",
   "metadata": {},
   "source": [
    "## 5. Download Tensorflow 2.4 (alpha 2)\n",
    "\n",
    "[Click here](https://github.com/apple/tensorflow_macos/releases/download/v0.1alpha2/tensorflow_macos-0.1alpha2.tar.gz) to download Tensorflow 2.4 (alpha 2) <br>\n",
    "Then, open the folder in Finder. You will get a folder named \"tensorflow_macos\"\n",
    "\n",
    "Go to arm64 in the tensorflow_macos folder (***Change the username with yours***)\n",
    "~~~\n",
    "cd /Users/username/Downloads/tensorflow_macos/arm64\n",
    "~~~"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "capital-winning",
   "metadata": {},
   "source": [
    "## 6. Create Conda environment\n",
    "\n",
    "Open Terminal and type:\n",
    "\n",
    "~~~\n",
    "conda create --name tf24 \n",
    "conda activate tf24\n",
    "conda install -y python==3.8.6\n",
    "conda install -y pandas matplotlib scikit-learn jupyterlab\n",
    "~~~"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "accredited-message",
   "metadata": {},
   "source": [
    "## 7. Set variables\n",
    "\n",
    "Open Terminal and type (***Change the username with yours***):\n",
    "~~~\n",
    "libs=\"/Users/username/Downloads/tensorflow_macos/arm64\"\n",
    "env=\"/Users/username/miniforge3/envs/tf24\"\n",
    "~~~"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "important-fairy",
   "metadata": {},
   "source": [
    "## Install TensorFlow 2.4 (alpha 2)\n",
    "\n",
    "Open Terminal and type:\n",
    "~~~\n",
    "pip install --upgrade pip wheel setuptools cached-property six\n",
    "\n",
    "pip install --upgrade -t \"$env/lib/python3.8/site-packages/\" --no-dependencies --force \"$libs/grpcio-1.33.2-cp38-cp38-macosx_11_0_arm64.whl\"\n",
    "\n",
    "pip install --upgrade -t \"$env/lib/python3.8/site-packages/\" --no-dependencies --force \"$libs/h5py-2.10.0-cp38-cp38-macosx_11_0_arm64.whl\"\n",
    "\n",
    "pip install --upgrade -t \"$env/lib/python3.8/site-packages/\" --no-dependencies --force \"$libs/numpy-1.18.5-cp38-cp38-macosx_11_0_arm64.whl\"\n",
    "\n",
    "pip install --upgrade -t \"$env/lib/python3.8/site-packages/\" --no-dependencies --force \"$libs/tensorflow_addons_macos-0.1a2-cp38-cp38-macosx_11_0_arm64.whl\"\n",
    "\n",
    "pip install absl-py astunparse flatbuffers gast google_pasta keras_preprocessing opt_einsum protobuf tensorflow_estimator termcolor typing_extensions wrapt wheel tensorboard typeguard\n",
    "\n",
    "pip install --upgrade -t \"$env/lib/python3.8/site-packages/\" --no-dependencies --force \"$libs/tensorflow_macos-0.1a2-cp38-cp38-macosx_11_0_arm64.whl\"\n",
    "~~~"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "random-citizen",
   "metadata": {},
   "outputs": [],
   "source": []
  }
 ],
 "metadata": {
  "kernelspec": {
   "display_name": "Python 3",
   "language": "python",
   "name": "python3"
  },
  "language_info": {
   "codemirror_mode": {
    "name": "ipython",
    "version": 3
   },
   "file_extension": ".py",
   "mimetype": "text/x-python",
   "name": "python",
   "nbconvert_exporter": "python",
   "pygments_lexer": "ipython3",
   "version": "3.8.6"
  }
 },
 "nbformat": 4,
 "nbformat_minor": 5
}
