# Computing.Automaton.Tensorflow.1904

### Anaconda is meant to install in a users HOME directory, by default it will be /home/username/anaconda3

#### It is possible to setup a group install, with shared environments, but there should be enough space for each user to have their own install

 $ cd ~
 
 $ wget https://repo.anaconda.com/archive/Anaconda3-2019.03-Linux-x86_64.sh
 
 $ chmod +x Anaconda3-2019.03-Linux-x86_64.sh
 
 $ ./Anaconda3-2019.03-Linux-x86_64.sh
 
### you can just delete a tensorflow installation by $ rm -rf ~/anaconda3

### Now to configure an environment with tensorflow
 https://towardsdatascience.com/tensorflow-gpu-installation-made-easy-use-conda-instead-of-pip-52e5249374bc

 $ conda create --name tf_gpu tensorflow-gpu

### Now test and use tensorflow

 $ conda activate tf_gpu
### Can deactivate by conda deactivate
### Can see other environments by conda info --envs
 
 $ python

 import import tensorflow as tf
 
 sess = tf.Session(config=tf.ConfigProto(log_device_placement=True))


