# Computing.Automaton.Tensorflow.1904

### Anaconda is meant to install in a users HOME directory, by default it will be /home/username/anaconda3

#### It is possible to setup a group install, with shared environments, but there should be enough space for each user to have their own install

 $ cd ~
 
 $ wget https://repo.anaconda.com/archive/Anaconda3-2019.03-Linux-x86_64.sh
 
 $ chmod +x Anaconda3-2019.03-Linux-x86_64.sh
 
 $ ./Anaconda3-2019.03-Linux-x86_64.sh
 
### you can just delete a tensorflow installation by $ rm -rf ~/anaconda3

#### Make sure you close the terminal and open a new one so paths are done properly.

### Now to configure an environment with tensorflow
 https://towardsdatascience.com/tensorflow-gpu-installation-made-easy-use-conda-instead-of-pip-52e5249374bc

 $ conda create --name tf_gpu tensorflow-gpu

### Now test and use tensorflow

 $ conda activate tf_gpu
### Can deactivate by conda deactivate
### Can see other environments by conda info --envs
 
 $ python

 import tensorflow as tf
 
 sess = tf.Session(config=tf.ConfigProto(log_device_placement=True))

### Install Theano (optional)
http://deeplearning.net/software/theano/install_ubuntu.html

Apart from the conda cuda and cudnn, you need to install cuda and cudnn from the nvidia site, latest version.
Then copy the include and lib&lib64 from cudnn into /usr/local/cuda/include and /usr/local/cuda/lib64
Only need to do this once per computer, as it's global, not local like conda envs.

Add the following path to your .bashrc file for cuda to have the includes in the system path.

export PATH="/usr/local/cuda/include:$PATH"

 $ conda create -n theano27 python=2.7
 
 $ conda activate theano27
 
 $ conda install numpy=1.12 scipy mkl
NOTE numpy=1.12, for some reason if you install the latest version of numpy here then the stuff doesn't work. install an old version, then install the latest version at the end.

 $ pip install parameterized
 
 $ conda install cudnn 
 
 $ conda install theano pygpu
 
 $ conda install numpy

Now when you run Theano python scripts you have to specify the env variables unless you add them to the .theanorc file.
THEANO_FLAGS='device=cuda0,dnn.include_path=/usr/local/cuda/include,dnn.library_path=/usr/local/cuda/lib64' python $HOME/gpu_tutorial.py
