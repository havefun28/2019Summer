# 2019 Summer
## 5.23 Install Carla
0. [CARLA paper](http://vladlen.info/papers/carla.pdf)
1. [Getting Started with CARLA] (https://carla.readthedocs.io/en/stable/getting_started/) -> [build with Linux](https://carla.readthedocs.io/en/latest/how_to_build_on_linux/) <br/>
Remember to [build Unreal Engine](https://wiki.unrealengine.com/Building_On_Linux) <br/>
[install clang 3.9 on ubuntu 16](https://askubuntu.com/questions/787383/how-to-install-llvm-3-9) (the clang default on Ubuntu is 16.04 is 3.8)
```
Add the archive signature:

wget -O - https://apt.llvm.org/llvm-snapshot.gpg.key | sudo apt-key add -
Add the PPA:

sudo apt-add-repository "deb https://apt.llvm.org/xenial/ llvm-toolchain-xenial-3.9 main"
sudo apt-get update
Note: There may be some authentication warnings for the llvm key which I have safely overridden on my own system. To bypass authentication, replace sudo apt-get update with

sudo apt -o Acquire::AllowInsecureRepositories=true update
Allow the Repository to reload and then run the following command:

sudo apt-get install clang-3.9 lldb-3.9
Test your installation as follows, as shown on my own Xenial system:

$ clang-3.9 --version
clang version 3.9.0-svn275716-1~exp1 (trunk)
Target: x86_64-pc-linux-gnu
Thread model: posix
InstalledDir: /usr/bin
```

[install clang 6.0 on ubuntu16](https://blog.kowalczyk.info/article/k/how-to-install-latest-clang-6.0-on-ubuntu-16.04-xenial-wsl.html) <br/>
After installation make "alternative link" following [this](https://github.com/carla-simulator/carla/issues/53)
To debugh `update-alternatives warning: broken link group, need to force reinstallation`, try [this](https://dev1galaxy.org/viewtopic.php?id=649), type `yes '' | sudo update-alternatives --force --all` in terminal, press `Enter` and redo the alternative link <br/>
After installing [Clang](https://clang.llvm.org/), `./Setup.sh` can run properly].

*Misc*
* Learn C++, [notes for `reference`](https://en.wikipedia.org/wiki/Reference_(C%2B%2B))

## 5.30
1. Change to Clang v3.8 in order to run ` ./GenerateProjectFiles.sh ` as normal. Follow [Build UE on Lunux](https://wiki.unrealengine.com/Building_On_Linux), do `make` and test with `./Engine/Binaries/Linux/UE4Editor` successfully.

## 6.10
1. First meeting with Prof. Li <br/>
Papers to read: <br/>
  * https://arxiv.org/pdf/1812.03079.pdf
  * http://www.cds.caltech.edu/~murray/preprints/comb19-aiaa.pdf
  * https://arxiv.org/pdf/1710.02410.pdf
  * https://arxiv.org/pdf/1611.01779.pdf
  * https://arxiv.org/pdf/1905.10691.pdf
2. To set up CARLA, although "build on linux" still get error of "No rules to make 'launch'", can download from `releases` from [CARLA github](https://github.com/carla-simulator/carla/releases) \[Linux] CARLA_0.9.5.tar.gz <br/>
Then directly run the program, see more at `README`

*Notes*
* [One-hot encoded data](https://machinelearningmastery.com/why-one-hot-encode-data-in-machine-learning/)
  
## 6.11
1. J-1 orientation
2. seminars @ MIT
3. Read paper`Learning to Act by Predicting the Future`

## 6.12
1. Read paper `MPSC`

*Notes*
* dynamical system: In mathematics, a dynamical system is a system in which a function describes the time dependence of a point in a geometrical space.
* [tube-based MPC](https://web.stanford.edu/~pavone/papers/Singh.Pavone.Slotine.CDC16EV.pdf): In tube MPC, an ancillary feedback controller is designed to keep the actual state within an invariant “tube” around a nominal trajectory computed neglecting disturbances.
* [constrained RL](https://arxiv.org/pdf/1801.08099.pdf) **To Do**
* [Lyapunov equation](https://stanford.edu/class/ee363/lectures/lq-lyap.pdf) AXA^{{H}}-X+Q=0 **To Do** [coursera videos](https://www.coursera.org/lecture/nonlinear-spacecraft-attitude-control/2-lyapunov-function-definition-no5pF)
* [automatic differentiation](https://en.wikipedia.org/wiki/Automatic_differentiation)

## 6.13
1. Install Carla 0.8.4 release and copy the `carla` folder inside to the git-cloned `conditional imitation learning` repo <br/>
install [tensorflow](https://www.tensorflow.org/install/pip?lang=python2) for python2.7 in virtualenv callled (venv) <br/>
encounter `RuntimeWarning: numpy.dtype size changed, may indicate binary incompatibility.` and solved by upgrading to numy 1.15.2 `pip install numpy==1.15.2` <br/>
correct way to add path: `export PATH=$PATH:/usr/local/cuda`. If use  `export PATH=/usr/local/cuda`, it will replace the path and cannnot execute normal command like `ls` `sudo`. Soln: restore to some commonly added path like `/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin` <br/>
use python3 for carla
2. Try to install CUDA 8.0, 10.0, nvidia driver. libpng library can be manuallly installed. <br/>
Final resolution: cuda 8.0 + nvidia 384 + manully install libpng library. <br/>
[CUDA 10 install](https://devtalk.nvidia.com/default/topic/1045400/cuda-setup-and-installation/cuda-10-installation-problems-on-ubuntu-18-04/)
* [How to Fix an Ubuntu System When It Won’t Boot](https://www.howtogeek.com/196740/how-to-fix-an-ubuntu-system-when-it-wont-boot/)
* [boot to a black screen](https://askubuntu.com/questions/162075/my-computer-boots-to-a-black-screen-what-options-do-i-have-to-fix-it/162078#162078)
* [Graphics issues after/while installing Ubuntu 16.04/16.10 with NVIDIA graphics](https://askubuntu.com/questions/760934/graphics-issues-after-while-installing-ubuntu-16-04-16-10-with-nvidia-graphics)
* [tensorflow and compatible version](https://www.tensorflow.org/install/source#tested_source_configurations)

## 6.14
1. group meeting: try data augmentationm <br/>
[Behavioral cloning w D.A. (from Udacity)](https://medium.com/@ksakmann/behavioral-cloning-make-a-car-drive-like-yourself-dc6021152713)
2. set up `MPSC_Guided_Imitation_Learning` so that both lab comp and my mac `can run pendulum.ipynb` <br/>
mac run `car2.ipynb` till before MPSC guided learning

*Notes*
* add path to jupyter notebook 
```
import os
import sys
nb_dir = os.path.split(os.getcwd())[0]
if nb_dir not in sys.path:
    sys.path.append(nb_dir)
```
* Since version 0.8, Pip supports pip-{version}. You can use it the same as easy_install-{version}:
```
$ pip-2.5 install myfoopackage
$ pip-2.6 install otherpackage
$ pip-2.7 install mybarpackage
```
same for python3
if pip3 doesn't help, use sth like `pip3.6`

*Others*
* ubuntu change font size `gsettings set org.gnome.desktop.interface text-scaling-factor 1.5`, change `1.5` to any factor you want.
* check numpy version: in python, `import numpy     numpy.version.version`

## 6.17
* Weichao's github link for [MPSC_Guided_Imitation_Learning](https://github.com/zwc662/MPSC_Guided_Imitation_Learning)
* [cvxopt cone programming](https://cvxopt.org/userguide/coneprog.html)

*Note* 
* Github In order to synchronize a fork: [config an upstream (source repo)](https://help.github.com/en/articles/configuring-a-remote-for-a-fork) and then [synchronize with it](https://help.github.com/en/articles/syncing-a-fork)
* [Theano documentation/tutorial](http://deeplearning.net/software/theano/) Read till [Seeding Streams](http://deeplearning.net/software/theano/tutorial/examples.html#seeding-streams)
* [Python memory](https://www.evanjones.ca/memoryallocator/)

## 6.18
1. lecture about conve optimiaion (Introl only
2. Figure out the naming and way of storage of the checkpoints files.
3. Save your own mpc_safe datapoints, try to save mpc safe traj and re-train

*Note*
* Pickle streams are entirely self-contained, and so unpickling will unpickle one object at a time. <br/>
Therefore, to unpickle multiple streams, you should repeatedly unpickle the file until you get an EOFError:
```
>>> f=open('a.p', 'wb')
>>> pickle.dump({1:2}, f)
>>> pickle.dump({3:4}, f)
>>> f.close()
>>> 
>>> f=open('a.p', 'rb')
>>> pickle.load(f)
{1: 2}
>>> pickle.load(f)
{3: 4}
>>> pickle.load(f)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module> EOFError
```
so your unpickle code might look like
```
import pickle
objs = []
while 1:
    try:
        objs.append(pickle.load(f))
    except EOFError:
        break
```

## 6.19
Meeting with Wenchao
1. Read paper [Berkeley: counter-example guided data augmentation](https://arxiv.org/pdf/1805.06962.pdf)
2. Continue to implement fine-tuning model. <br/>

*Note*
* add 
```
%load_ext autoreload
%autoreload 2
```
in jupyter notebook (iPython for python3.5) to autoreload

## 6.20 
1. Solve problem `can't convert np.ndarray of type numpy.object_.` <br/>
* change `x0_` to `x0`, less one layer of `[]` <br/>
* change `for j in range(0, n+1)` to `for j in range(0, n)`
After changing some format, finally able to train a new model with MPC output. However, the output runs in a circle at the starting point. **TODO** check the x0_ilqr_path, may be modified unintentionally
2. Read about online learning [basic idea](https://medium.com/value-stream-design/online-machine-learning-515556ff72c5) [Thesis: Online Learning: Theory, Algorithms, and Applications](https://ttic.uchicago.edu/~shai/papers/ShalevThesis07.pdf)  [MIT notes](http://www.mit.edu/~rakhlin/6.883/lectures/lecture01.pdf)
3. Modify the code and put `create_expert_traj_boundary/ref` into funcitons. Collect new expert points `[x0, upper_boundary, lower_boundary]`. **TODO** use the new points to train a new model and compare with that with MPC safe control.

*Python*
* [parameter passing for mutable & immutable objects](https://medium.com/@tyastropheus/tricky-python-ii-parameter-passing-for-mutable-immutable-objects-10e968cbda35)

## 6.21
1. Group meeting [EWRL18 tutorial on safe RL](https://las.inf.ethz.ch/files/ewrl18_SafeRL_tutorial.pdf)
2. Set up new desktop following [lambda stack](https://deeptalk.lambdalabs.com/t/install-ubuntu-18-04-with-lambda-stack-from-scratch/490).  Boot program [Legacy VS UEFI](https://phoenixts.com/blog/uefi-vs-legacy-bios/) <br/>
* Ubuntu setup [Top 10 things to do](https://www.linuxtechi.com/top10-things-after-installing-ubuntu-18-04/) 
* [install terminator](https://blog.arturofm.com/install-terminator-terminal-emulator-in-ubuntu/) 
* "switching between screens" is called `workspace`; in 16.04, `menu bar -> Appearances -> Behavior -> Enable workspace` allows you to switch between four workspaces; in 18.04 just move the applicaiton by `ctrl + alt + arrow` and it will automatically create new workspace
* the `super` key is the key with windows logo
3. Big group meeting at Robotics Lab
4. Finish collecting 50000 data points of \[current position, upper&lower boundary], train a model and compare with MPC safe controller. have 5 (fewer) points violating safety constraint, and the "switching" controller seems to work much smoothier than CNN learnt from ref traj. However, when I use the five MPC controller o\p to retrain the model, it flies to sky.

## 6.22
Running, hotpot, chatting, go to PHO and study Cvx Opt Lec2

## 6.23
Chatting, meet Wanzheng, study Cvx Opt Lec3, read part of paper reduction to IL, 选课

## 6.24
0. Get the account ready
1. Collect points for non-symmetric boundaries, train the model and draw the plots 
2. Finish the paper `A Reduction of Imitation Learning and Structured Prediction to No-Regret Online Learning` <br/>
**TODO** find code & try to implement on Carla <br/>
Found [one implemented on car racing game with Gym](https://github.com/havefun28/imitation-dagger) <br/>
able to run dagger.py, **TODO** Look into the dagger code
3. Install Carla (download Carl 0.9.5 release package, as building on Linux encounter the same problem of "No rule to make target 'launch'") <br/>
Run `sudo apt-get install python-pygame` and `sudo apt-get install python3-pygame` in terminal to install pygame <br/>
Try carla/CIL again and notice that `run_CIL.py` only works with python 2.7 & 3.5 <br/>
[intall python3.5](https://askubuntu.com/questions/682869/how-do-i-install-a-different-python-version-using-apt-get ), since originally only have 3.6, 3.7. <br/>
However, since packages like numpy were only installed on PYthon 3.6 & 3.7, choose to run CIL with python 2.7 and Carla 0.8.4 (Carla 0.9 encounter error `no 'carla' found` or `no 'carla.benchmark' found`) <br/>
Encounter error `ERROR: (localhost:2000) failed to connect: [Errno 111] Connection refused`, solved by adding `carla-server` tag to `./CarlaUE4.sh` server command <br/>
Encounter error `module 'scipy.misc' has no attribute 'imresize`, only solved in PYthon 2.7 by `sudo pip install Pillow` and reopen the terminal
4. Current solution to run carla/CIL: <br/>
* in one terminal of `~/CARLA_0.8.4` run ` ./CarlaUE4.sh -carla-server` (which will [by default connect to port 200, 2001, 2002](https://carla.readthedocs.io/en/stable/connecting_the_client/) can be check by running `./client_example.py --autopilot` under `~/CARLA_0.8.4/PythonClient`)<br/>
* in another terminal of `~/imitation-learning` run `python run_CIL.py` (works fine with 2.7, but not with `python3` because of error `module 'scipy.misc' has no attribute 'imresize` >> check Pillow has been installed, scipy is updated, so the problem is maybe due to the fact that [`imread` and `imresize` have been removed](https://github.com/lengstrom/fast-style-transfer/issues/106#issuecomment-501967909))
5. Go through run_CIL code and it only loads a pre-trained model (an agent) and benchmark it. To train the model or modify and retrain it with dagger, you need to look at their training code. see below
6. On old desktop, install [sublime merge](https://www.sublimemerge.com/docs/linux_repositories#apt)

*TODO*
[argparse tutorial](https://docs.python.org/2/howto/argparse.html)
* posts to look at for Carla CIL training <br/>
[Questions on model & training](https://github.com/carla-simulator/imitation-learning/issues/1)
[merantix](https://github.com/merantix/imitation-learning)
[felip](https://github.com/felipecode/coiltraine/)
*Note*
* use [lsof command](https://www.cyberciti.biz/faq/unix-linux-check-if-port-is-in-use-command/) to check the ports been used by programs
* CARLA tip: <br/>
 * You can launch the simulator in windowed mode by using the argument -windowed, and control the window size with -ResX=N and -ResY=N.
 * [Github version control](https://ourcodingclub.github.io/2017/02/27/git.html)
 
## 6.25
1. Install [Miniconda 2](https://www.osetc.com/en/how-to-install-miniconda-on-ubuntu-18-04-16-04-linux.html) on new desktop.
2. Try training carla using [felip repo coiltraine](https://github.com/havefun28/coiltraine) <br/>
To run coiltraine, need to [run Carla in docker](https://carla.readthedocs.io/en/latest/carla_docker/)
3. Create a Docker account. Username: ruihan pw: ILstudy28! email: gaor0007@entu.edu.sg
4. Install docker  
 * for Docker only can follow  [How to Install Docker On Ubuntu 18.04 Bionic Beaver](https://linuxconfig.org/how-to-install-docker-on-ubuntu-18-04-bionic-beaver), change `bionic` to [`artful`](https://askubuntu.com/questions/1030179/package-docker-ce-has-no-installation-candidate-in-18-04) and finally get `(coiltraine) ruihan@depend-XPS-8930:~$ docker --version Docker version 18.06.3-ce, build d7080c1`
 * in coiltraine case where nvidia-docker2 is required, follow [Get Docker CE for Ubuntu](https://docs.docker.com/install/linux/docker-ce/ubuntu/#extra-steps-for-aufs). Try with repo, but encounter the problem cuz "docker-ce package is missing for Ubuntu "Bionic" 18.04 LTS x86_64" Soln: follow [QuickStart](https://github.com/NVIDIA/nvidia-docker#quickstart) and after adding the repos, do the following to pin all three specific versions
```
sudo apt-get install docker-ce=18.06.0~ce~3-0~ubuntu
sudo apt-get install nvidia-container-runtime=2.0.0+docker18.06.0-1
sudo apt-get install nvidia-docker2=2.0.3+docker18.06.0-1
```
* Note:when create a new file in `/etc/`, permission denied; soln: create in home directory and copy it to `/etc`
* [os.environ](https://kite.com/python/docs/os.environ)

* After a day's debugging (should use `suppress_output=0` at the first beginning), find the error and many others [encounter the same thing](https://github.com/felipecode/coiltraine/issues/12). <br/>
the error is   
```
File "/home/ruihan/miniconda2/envs/coiltraine/lib/python3.5/site-packages/numpy/core/fromnumeric.py", line 41, in _wrapit
    result = getattr(asarray(obj), method)(*args, **kwds)
numpy.core._internal.AxisError: axis1: axis 0 is out of bounds for array of dimension 0
```
when running `for data in data_loader` in `train.execute`

## 6.26
1. Continue to debug CoIL training.  <br/>
`python3 coiltraine.py --folder sample --gpus 0 -de TestT1_Town01 -vd CoILVal1 --docker carlasim/carla:0.8.4`

*Debug*
* `STATUS: Error - cuda runtime error (38) : no CUDA-capable device is detected at /pytorch/aten/src/THC/THCGeneral.cpp:74` <br/>
Soln: set `gpus` = 0 (Restart the program with os.environ\["CUDA_VISIBLE_DEVICES"] = '0'can solve the problem)
* `AttributeError: 'NoneType' object has no attribute 'swapaxes'`<br/>
Find that the error is due to inconsistency of img paths when reading the files. <br/>
check `def _pre_load_image_folders(self, path):` in `coil_dataset.py` <br/>
"THCudaCheck FAIL file=/pytorch/aten/src/THC/THCGeneral.cpp line=663 error=11 : invalid argument" Soln: add `torch.backends.cudnn.benchmark = False` in `train.py` before using torch <br/>
the program stops/hangs at `loss.backward()` and cannot proceed to `optimizer.step()` after one iteration. Soln: upgrade pytorch from 0.4 to 1.0 by `pip install --upgrade torch torchvision` <br/>
after upgrading, encounter "Error - cuDNN error: CUDNN_STATUS_EXECUTION_FAILED", need to upgrade corresponding packages by `conda install pytorch torchvision cudatoolkit=10.0 -c pytorch` (my cuda is actually 10.1 but this works) <br/>
Till now it can load data properly and proceed from `Loading` status to `Iterating` status. Hopefully it goes well tomorrow.

*Python*
* check meaning and [differences between `def __init__` and  ` def __call__`](https://stackoverflow.com/questions/9663562/what-is-the-difference-between-init-and-call), [`def __repr__`](https://stackoverflow.com/questions/1984162/purpose-of-pythons-repr) , and [`def __getitem__`](https://stackoverflow.com/questions/43627405/understanding-getitem-method)

* [git ignore](https://git-scm.com/docs/gitignore)

## 6.27
1. **TODO** [exploration](http://www.cs.cmu.edu/~rsalakhu/10703/Lecture_Exploration.pdf)
2. To avoid "CUDA out of memory" error: change GPU value from 3.5 to 2 so that only one process is going on.
3. Debug: `driving` is in `iterating` for too long, then check the o`outputl_log` find the error `ERROR:root:(127.0.0.1:49971) failed to connect: [Errno 111] Connection refused`
4. After training and validation, can run the following to execute one single process `python3 coiltraine.py --folder sample --single-process drive --exp coil_icra --gpus 0 -de TestT1_Town01 -vd CoILVal1 --docker carlasim/carla:0.8.4` (`coil_icra` is found by searching the subfolder of `_logs/sample/`)
5. When run the single process of `drive`, <br/>
encounter "ERROR:root:(127.0.0.1:49971) failed to connect: \[Errno 111] Connection refused" <br/>
Soln: set `suppress_output` to False and find the internal error is `permission denied` (docker: Got permission denied while trying to connect to the Docker daemon socket at unix:///var/run/docker.sock: Post http://%2Fvar%2Frun%2Fdocker.sock/v1.38/containers/create: dial unix /var/run/docker.sock: connect: permission denied. See 'docker run --help') from `docker`. Should [add user to docker group](https://techoverflow.net/2018/12/15/how-to-fix-docker-got-permission-denied-while-trying-to-connect-to-the-docker-daemon-socket/) by running command [`sudo usermod -a -G docker $USER`](https://techoverflow.net/2019/04/30/what-does-sudo-usermod-a-g-docker-user-do-on-linux/), where `$USER` should be either `$USER` or explicitly `ruihan`
To run `docker` without `sudo`, log out and login again to the desktop (not only docker account) <br/>
encouter error "ERROR:root:(127.0.0.1:54729) connection closed" <br/>
Encounter "connection closed when running carla", waiting for a few seconds helps since [the client may be waiting](https://github.com/carla-simulator/carla/issues/263#issuecomment-383113144)
6. Try Penny's [Get started](https://carlachallenge.org/get-started/) <br/>
When running `bash srunner/challenge/run_evaluator.sh`, encounter `ImportError: No module named carla`. Soln: in `~/.bashrc`, add `export PYTHONPATH="${PYTHONPATH}:/home/ruihan/CARLA_0.9.5/PythonAPI/"` <br/>
if follow [tutorial](https://github.com/carla-simulator/scenario_runner/blob/development/Docs/getting_started.md/#install_prerequisites), encounter `https://github.com/carla-simulator/scenario_runner/blob/development/Docs/getting_started.md/#install_prerequisites` when running `ython scenario_runner.py --scenario FollowLeadingVehicle` [possible soln](https://github.com/carla-simulator/scenario_runner/issues/172)
7. Note: when running srunner, remember to do `conda deactivte`, otherwise need to install packages separtely, e.g. `cv2`


Commands
python $/home/ruihan/scenario_runner/srunner/challenge/challenge_evaluator_routes.py \
--scenarios=$/home/ruihan/scenario_runner/srunner/challenge/all_towns_traffic_scenarios1_3_4.json \
--routes=$/home/ruihan/scenario_runner/srunner/challenge/routes_training.xml \
--repetitions=3 \
--debug=0 \
--agent=autonomous_agent \
--config=FollowLeadingVehicle.xml

*Notes*
* Docker 
 * check process and port `docker ps -a`
 * [remove a container](https://linuxize.com/post/how-to-remove-docker-images-containers-volumes-and-networks/)
 * Error response from daemon::Cannot kill container  signaling init process caused "permission denied" 
 ```
 For anyone that does not wish to completely purge AppArmor.

 Check status: sudo aa-status

 Shutdown and prevent it from restarting: sudo systemctl disable apparmor.service --now

 Unload AppArmor profiles: sudo service apparmor teardown

 Check status: sudo aa-status

 You should now be able to stop/kill containers.
 ```
 * [dlib](http://dlib.net/)
 
## 6.28
1. Group meeting "App-Aware Scheduling" shard by Kacper, "enumerating the other labelling is already #P complete, i.e. too complex, so only evaluate optimal solution for one labelling.
2. Meeting with Wenchao, use the Carla Challenge one and make your own agent. Can refer to `coiltraine` if necessary but no need to spend too much time debugging it. <br/>
He stresses 
 1. for different scenarios, like the routes, turns, and notice that we can create some json files like `srunner/challenge/all_towns_traffic_scenarios1_3_4.json` and add more interesting scenarios.
 2.Add more controllable agents at the same time: cooperative imitation learning
3. Reading group meeting at Robotics Lab. Reinforcement learning. <br/>
Parameters tuning, [neural architecture search](https://www.automl.org/automl/literature-on-neural-architecture-search/), [knowledge distillation](https://arxiv.org/pdf/1503.02531.pdf)
4. Experiment with other agents built in scenario_runner and try to create your own imitation learning agent. <br/>
**Total installation:**
 0. `conda deactivate` to deactivate any running virtual environment and in `~/.bashrc`, comment out miniconda. Check by `which python` >> `usr/bin/python` <br/>
Clone [scenario_runner repo](https://github.com/carla-simulator/scenario_runner) to my account, then follow [tutorial](https://carlachallenge.org/get-started/) and [installation](https://github.com/carla-simulator/scenario_runner/blob/development/Docs/getting_started.md/#installing-prerequisites)
 1. Follow Step 1 to clone `carla_challenge` branch
 2. Follow Step 2 and set `bash setup_environment.sh --carla-root /home/ruihan/CARLA_0.9.5` followed by `source ~/.bashrc`
Routine procedure: <br/>
 3. Follow Step 3 exactly. When firstly start the server `./CarlaUE4.sh`, the town appears. But after running `bash srunner/challenge/run_evaluator.sh`, it will automatically change to racing challenge setting, so don't worry.
**After first time setting, just run Step 3 to start experiment**
5. First glance into the agents: 
 * Dummy agent does nothing but stays there. 
 * HumanAgent receives keyboard-mouse control.
 * NPCAgent follows pre-defined path. (Normal players as others)
 * ros_agent needs package `rospy` and not in interest now
 * Track4SampleAgent "THis is a human controlled agent with track 4 access for testing", did not get it yet
6. [Fov: field of view](https://en.wikipedia.org/wiki/Field_of_view_in_video_games)
7. Try the `coiiltrane` imitation learning agent with scenario_runner.py
when running [visualization](https://github.com/felipecode/coiltraine/blob/master/docs/carla_challenge_coil_baseline.md#visualize-the-agent-results)
```
$ python3 view_model.py -f baselines -e resnet34imnet -cp 180000 -cv 0.9
pygame 1.9.4
Hello from the pygame community. https://www.pygame.org/contribute.html
Traceback (most recent call last):
  File "view_model.py", line 89, in <module>
    import model_view.carla09interface as carla09interface
  File "/home/ruihan/coiltraine/model_view/carla09interface.py", line 72, in <module>
    import carla
  File "/home/ruihan/CARLA_0.9.5/PythonAPI/carla/__init__.py", line 8, in <module>
    from .libcarla import *
ImportError: /home/ruihan/CARLA_0.9.5/PythonAPI/carla/libcarla.so: undefined symbol: PyString_Type
```

when running [this](https://github.com/felipecode/coiltraine/blob/master/docs/carla_challenge_coil_baseline.md#get-the-agent-performance-on-the-carla-challenge)
```
CHALLENGE_PHASE_CODENAME=dev_track_2 python3 ${ROOT_SCENARIO_RUNNER}/srunner/challenge/challenge_evaluator_routes.py --scenarios=${ROOT_SCENARIO_RUNNER}/srunner/challenge/all_towns_traffic_scenarios1_3_4.json --routes=${ROOT_SCENARIO_RUNNER}/srunner/challenge/routes_training.xml --debug=0 --agent=../coiltraine/drive/CoILBaseline.py --config=../coiltraine/drive/sample_agent.json
Traceback (most recent call last):
  File "/home/ruihan/scenario_runner/srunner/challenge/challenge_evaluator_routes.py", line 31, in <module>
    import py_trees
ImportError: No module named 'py_trees'
```
## 6.29
* successful install `sudo python -m easy_install ${CARLA_ROOT}/PythonAPI/carla/dist/*-py2.7-linux-x86_64.egg`
* `sudo ln -sfn /usr/bin/python3.6 /usr/bin/python3`
```
CHALLENGE_PHASE_CODENAME=dev_track_2 python ${ROOT_SCENARIO_RUNNER}/srunner/challenge/challenge_evaluator_routes.py\
--scenarios=${ROOT_SCENARIO_RUNNER}/srunner/challenge/all_towns_traffic_scenarios1_3_4.json \
--routes=${ROOT_SCENARIO_RUNNER}/srunner/challenge/routes_training.xml \
--debug=0 \
--agent=../coiltraine/drive/CoILBaseline.py \
--config=../coiltraine/drive/sample_agent.json
```
"error: command 'x86_64-linux-gnu-gcc' failed with exit status 1 ---------------------------------------- Failed building wheel for psutil" Soln: `$ sudo apt install python3.5-dev`

* use python3.5 for coiltraine and scenario_run. Install some packages for 3.5 (system default only has 3.6 and 3.7)
* switch default python3 version `sudo ln -sfn /usr/bin/python3.5 /usr/bin/python3`
 * Debug: "Unable to find `imresize`". If got this error even with pillow installed on scipy==1.3.0, then fixed it by installing an earlier version:  `pip3 install scipy==1.1.0 --user`
 * Debug "ModuleNotFoundError: No module named `torch._C` ", `sudo pip3 install --upgrade torch` 
 * [easy_install](https://setuptools.readthedocs.io/en/latest/easy_install.html)

* when run `python3 view_model.py  -f baselines -e resnet34imnet -cp 180000 -cv 0.9`, pygame blank black screen, but does not report any error
* successfully run  
```
CHALLENGE_PHASE_CODENAME=dev_track_2 python3 ${ROOT_SCENARIO_RUNNER}/srunner/challenge/challenge_evaluator_routes.py \
--scenarios=${ROOT_SCENARIO_RUNNER}/srunner/challenge/all_towns_traffic_scenarios1_3_4.json \
--routes=${ROOT_SCENARIO_RUNNER}/srunner/challenge/routes_training.xml \
--debug=0 \
--agent=../coiltraine/drive/CoILBaseline.py \
--config=../coiltraine/drive/sample_agent.json
```
under `~/scenario_run` without any conda environment

## 7.1
1. Fix the bug of "cannot open terminator/terminal". It is the problem of python version. <br/>
When running CARLA, I changed the default `python3` from 3.6 to 3.5 globally, while in `/usr/bin` the `_gi` file required for lauching `gnome-terminal` is for 3.6 only. (Launch `xTerm` and type `gnome-terminal` returns the error "Import Error cannot import name '\_gi'") <br/>
Soln: 
```
cd /usr/lib/python3/dist-packages/gi/
ls
sudo cp _gi.cpython-36m-x86_64-linux-gnu.so _gi.cpython-35m-x86_64-linux-gnu.so
sudo cp _gi_cairo.cpython-36m-x86_64-linux-gnu.so _gi_cairo.cpython-35m-x86_64-linux-gnu.so
```
so that `gnome-terminal` works fine with python3.5. <br/>
For terminator, which needs to work with python2 (check by running`terminator` in terminal and get error "except(KeyError, ValueError), ex") <br/>
Soln: edit `/usr/bin/terminator` and changing the python version to python2 (the default python was changed to python3). In my case, the file `/usr/bin/terminator` is read-only, so copy it to `~/` directory (`sudo cp /usr/bin/terminator /home/ruihan/terminator`), change the first line from `#!/usr/bin/python` to `#!/usr/bin/python2`. Finally copy it back `sudo cp /home/ruihan/terminator /usr/bin/terminator` and you're ready to go!
2. **SMOOTH flow**
Start the CARLA server on one terminal without conda env:
```
cd ~/CARLA_0.9.5
./CarlaUE4.sh -benchmark -fps=20 -quality-level=Epic
```
Execute the challenge with the conditional imitation learning baseline in another terminal
```
cd ~/scenario_runner
conda activate coiltraine
CHALLENGE_PHASE_CODENAME=dev_track_2 python3 ${ROOT_SCENARIO_RUNNER}/srunner/challenge/challenge_evaluator_routes.py \
--scenarios=${ROOT_SCENARIO_RUNNER}/srunner/challenge/all_towns_traffic_scenarios1_3_4.json \
--routes=${ROOT_SCENARIO_RUNNER}/srunner/challenge/routes_training.xml \
--debug=0 \
--agent=../coiltraine/drive/CoILBaseline.py \
--config=../coiltraine/drive/sample_agent.json
```
Watch the results.

*Note*
* `sudo apt-get install` option: `sudo apt-get install --reinstall terminator`
* change the `~/.bashrc` to default setting 
```
cp ~/.bashrc ~/Documents/.bashrc.bak (save a copy of current file)
cp /etc/skel/.bashrc ~/ (recreate a fresh bashrc file)
```
* set the locale
```
sudo locale-gen
sudo localectl set-locale LANG="en_US.UTF-8"
```
* correct way to add a PYTHONPATH `export PYTHONPATH=/home/ruihan/coiltraine:$PYTHONPATH`; `:` stands for "adding" and no space in between!
* kill process in terminal, e.g. for pygame that does not close window `kill -9 xxx`(xxx is the process ID) or `pkill -9 python`

*Python*
* [getattr](https://effbot.org/zone/python-getattr.html)

## 7.2
*QuickLinks*
* [Policy aggregation in SMPyBandit](https://smpybandits.github.io/Aggregation.html)
* [CARLA API ref](https://github.com/carla-simulator/carla/blob/master/Docs/python_api.md) <br/>
* [PYTHON API methods ref](https://carla.readthedocs.io/en/latest/python_api/) <br/>
* [Git commands](https://github.com/joshnh/Git-Commands)

1. Individual meeting with Wenchao. Suggest to implement safe IL & BC on Scenario 1, ControlLoss of Carla AD Challenge.
2. Try to run scenario_runner with ControlLoss.
```
export ROOT_SCENARIO_RUNNER=/home/ruihan/scenario_runner
python ${ROOT_SCENARIO_RUNNER}/srunner/challenge/challenge_evaluator_routes.py \
--scenarios=${ROOT_SCENARIO_RUNNER}/srunner/challenge/all_towns_traffic_scenarios1_3_4.json \
--routes=${ROOT_SCENARIO_RUNNER}/srunner/challenge/routes_training.xml \
--repetitions=3 \
--debug=0 \
--agent=${TEAM_AGENT} \
--config=${TEAM_CONFIG}
```
```
 CHALLENGE_PHASE_CODENAME=dev_track_2 python3 ${ROOT_SCENARIO_RUNNER}/srunner/challenge/challenge_evaluator_routes.py \
--scenarios=${ROOT_SCENARIO_RUNNER}/srunner/challenge/all_towns_traffic_scenarios1_3_4.json \
--routes=${ROOT_SCENARIO_RUNNER}/srunner/challenge/routes_training.xml \
--debug=0 \
--agent=../coiltraine/drive/CoILBaseline.py \
--config=../coiltraine/drive/sample_agent.json
```
3. Look into scenario files and want to train the ciltriane agent.

* [Environment variables](https://medium.com/chingu/an-introduction-to-environment-variables-and-how-to-use-them-f602f66d15fa) e.g. `CHALLENGE_PHASE_CODENAME` to run `challenge_evaluater_routes.py`
* [behaviour tree](https://py-trees.readthedocs.io/en/devel/behaviours.html)
* [xml py-tree](https://www.datacamp.com/community/tutorials/python-xml-elementtree)

*Debug*
When running [training](https://github.com/havefun28/coiltraine/blob/master/docs/carla_challenge_coil_baseline.md#training)
* "Object arrays cannot be loaded when allow_pickle=False' for `np.load` function" <br/>
Soln: change `with np.load(path) as f` to `with np.load(path, allow_pickle=True) as f`
* "cannot import name '\_validate_lengths' " <br/>
`conda install -c conda-forge scikit-image` and/or `pip install -U scikit-image`
* "THCudaCheck FAIL file=/pytorch/aten/src/THC/THCGeneral.cpp line=383 error=11 : invalid argument" <br/>
Soln: [Incompatible torch version and RTX](https://github.com/pytorch/pytorch/issues/15797)
```
$ wget https://download.pytorch.org/whl/cu100/torch-1.0.0-cp35-cp35m-linux_x86_64.whl
$ python3.5 -m pip install torch-1.0.0-cp35-cp35m-linux_x86_64.whl
```
Leave with: successfully run --scenario FollowLeadingVehicle with scenario_runner of carla_challenge branch
## 7.3
1. Switch to master branch of scenario_runner, which allows multiple ego_vehicle and fix the 'group' option for running one scenario <br/>
Experiment: 1. run CARLA_0.95 as usual; 2. `python scenario_runner.py --scenario group:FollowLeadingVehicle` in `~/scenario_runner_master`; 3. Before it times out, run ` python manual_control.py` also in  `~/scenario_runner_master` <br/>
Results: 
Currently the smoothiest one. Can see around three (fixed) scenarios, but still need debugging.
```
(coiltraine) ruihan@depend-XPS-8930:~/scenario_runner_master$ python scenario_runner.py --scenario group:FollowLeadingVehicle
Preparing scenario: FollowLeadingVehicle_1
ScenarioManager: Running scenario FollowVehicle
Resetting ego-vehicle!
Resetting ego-vehicle!
Failure!
Resetting ego-vehicle!
Preparing scenario: FollowLeadingVehicleWithObstacle_1
ScenarioManager: Running scenario FollowLeadingVehicleWithObstacle
Resetting ego-vehicle!
Resetting ego-vehicle!
Resetting ego-vehicle!
Failure!
Resetting ego-vehicle!
Resetting ego-vehicle!
Preparing scenario: FollowLeadingVehicle_2
ScenarioManager: Running scenario FollowVehicle
Resetting ego-vehicle!
Failure!
Resetting ego-vehicle!
Preparing scenario: FollowLeadingVehicleWithObstacle_2
ScenarioManager: Running scenario FollowLeadingVehicleWithObstacle
eeResetting ego-vehicle!
Resetting ego-vehicle!
Resetting ego-vehicle!
Failure!
Resetting ego-vehicle!
Resetting ego-vehicle!
Preparing scenario: FollowLeadingVehicle_3
The CARLA server uses the wrong map!
This scenario requires to use map Town02
The scenario cannot be loaded
The CARLA server uses the wrong map!
Preparing scenario: FollowLeadingVehicleWithObstacle_3
The CARLA server uses the wrong map!
This scenario requires to use map Town02
The scenario cannot be loaded
The CARLA server uses the wrong map!
Preparing scenario: FollowLeadingVehicle_4
The CARLA server uses the wrong map!
This scenario requires to use map Town03
The scenario cannot be loaded
The CARLA server uses the wrong map!
Preparing scenario: FollowLeadingVehicleWithObstacle_4
The CARLA server uses the wrong map!
This scenario requires to use map Town03
The scenario cannot be loaded
The CARLA server uses the wrong map!
Preparing scenario: FollowLeadingVehicle_5
The CARLA server uses the wrong map!
This scenario requires to use map Town04
The scenario cannot be loaded
The CARLA server uses the wrong map!
Preparing scenario: FollowLeadingVehicleWithObstacle_5
The CARLA server uses the wrong map!
This scenario requires to use map Town04
The scenario cannot be loaded
The CARLA server uses the wrong map!
Preparing scenario: FollowLeadingVehicle_6
The CARLA server uses the wrong map!
This scenario requires to use map Town04
The scenario cannot be loaded
The CARLA server uses the wrong map!
Preparing scenario: FollowLeadingVehicleWithObstacle_6
The CARLA server uses the wrong map!
This scenario requires to use map Town04
The scenario cannot be loaded
The CARLA server uses the wrong map!
Preparing scenario: FollowLeadingVehicle_7
The CARLA server uses the wrong map!
This scenario requires to use map Town04
The scenario cannot be loaded
The CARLA server uses the wrong map!
Preparing scenario: FollowLeadingVehicleWithObstacle_7
The CARLA server uses the wrong map!
This scenario requires to use map Town04
The scenario cannot be loaded
The CARLA server uses the wrong map!
Preparing scenario: FollowLeadingVehicle_8
The CARLA server uses the wrong map!
This scenario requires to use map Town05
The scenario cannot be loaded
The CARLA server uses the wrong map!
Preparing scenario: FollowLeadingVehicleWithObstacle_8
The CARLA server uses the wrong map!
This scenario requires to use map Town05
The scenario cannot be loaded
The CARLA server uses the wrong map!
Preparing scenario: FollowLeadingVehicle_9
The CARLA server uses the wrong map!
This scenario requires to use map Town05
The scenario cannot be loaded
The CARLA server uses the wrong map!
Preparing scenario: FollowLeadingVehicleWithObstacle_9
The CARLA server uses the wrong map!
This scenario requires to use map Town05
The scenario cannot be loaded
The CARLA server uses the wrong map!
Preparing scenario: FollowLeadingVehicle_10
The CARLA server uses the wrong map!
This scenario requires to use map Town05
The scenario cannot be loaded
The CARLA server uses the wrong map!
Preparing scenario: FollowLeadingVehicleWithObstacle_10
The CARLA server uses the wrong map!
This scenario requires to use map Town05
The scenario cannot be loaded
The CARLA server uses the wrong map!
Preparing scenario: FollowLeadingVehicle_11
The CARLA server uses the wrong map!
This scenario requires to use map Town02
The scenario cannot be loaded
The CARLA server uses the wrong map!
Preparing scenario: FollowLeadingVehicleWithObstacle_11
The CARLA server uses the wrong map!
This scenario requires to use map Town02
The scenario cannot be loaded
The CARLA server uses the wrong map!
No more scenarios .... Exiting
```
If for Step 2, use ` python scenario_runner.py --reloadWorld --scenario group:FollowLeadingVehicle` instead, will encounter error
```
ERROR: trying to access an expired episode; a new episode was started in the simulation but an object tried accessing the old one.
Traceback (most recent call last):
  File "manual_control.py", line 622, in game_loop
    if not world.tick(clock):
  File "manual_control.py", line 158, in tick
    if len(self.world.get_actors().filter(self.vehicle_name)) < 1:
RuntimeError: trying to access an expired episode; a new episode was started in the simulation but an object tried accessing the old one.

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File "manual_control.py", line 681, in main
    game_loop(args)
  File "manual_control.py", line 630, in game_loop
    world.destroy()
  File "manual_control.py", line 177, in destroy
    actor.destroy()
RuntimeError: trying to access an expired episode; a new episode was started in the simulation but an object tried accessing the old one.
```
*Debug*
* [git resolve merge conflicts](https://help.github.com/en/articles/resolving-a-merge-conflict-using-the-command-line)
* [Comprehensive GIT cheatsheet](http://www.ccs.neu.edu/home/types/resources/notes/cs4500-git.md)
* Fix [error in loading scenarios](https://github.com/carla-simulator/scenario_runner/issues/172)
* Fix Git error "remote: error: File is 268.01 MB; this exceeds GitHub's file size limit of 100.00 MB" <br/>
1. [Remove a big file wrongly committed](https://thomas-cokelaer.info/blog/2018/02/git-how-to-remove-a-big-file-wrongly-committed/)
```
git filter-branch --tree-filter 'rm -rf path/to/your/file' HEAD
git push
```
2. if get error "\[rejected] master -> master (non-fast-forward) error: failed to push some refs to 'https://github.com/havefun28/coiltraine.git' hint: Updates were rejected because the tip of your current branch is behind hint: its remote counterpart. Integrate the remote changes" <br/>
Soln: [deal with fast-forward error](https://help.github.com/en/articles/dealing-with-non-fast-forward-errors)
3. error "fatal: refusing to merge unrelated histories"
```
git pull origin master --allow-unrelated-histories
git merge origin origin/master
```
4. error "Auto-merging input/coil_dataset.py CONFLICT (add/add): Merge conflict in input/coil_dataset.py" <br/>
use [`git diff`](https://git-scm.com/docs/git-diff) to check
```
git diff branch1 branch2 -- path/to/file
git checkout name_of_branch path/to/file
```
Sometimes the right content is a mix of the two files. In that case you have to resolve manually, possibly by studying the differences using the git diff command and manully modify in text editor or use Git desktop GUI.

* Running CARLA
 * "The CARLA server uses the wrong map!" <BR/>
 Soln: when running [`scenario_runner`](https://github.com/carla-simulator/scenario_runner/blob/master/Docs/getting_started.md), use `./CarlaUE4.sh /Game/Carla/Maps/Town01 -benchmark -fps=20 -windowed` for server; <br/>
 when running [challenge](https://carlachallenge.org/get-started/), use ` ./CarlaUE4.sh -benchmark -fps=20 -quality-level=Epic` for server
 *  two different systems, `scenario_runner` and `challenge_routes.py`
 
* try to convert xml to json file. `ControlLoss.xml` contains all scenarios (Town 01-05) of control loss and I try to convert it to `.json` file so that can run in `challenge`, which currently use `Scenario1_3_4` to contain different types of scenarios in different towns. <br/>
Can use library [xmltodict](https://pypi.org/project/xmltodict/) but need to pay close attention to the hierachy

## 7.4
* Starting point (what works) <br/>
```
./CarlaUE4.sh /Game/Carla/Maps/Town01 -benchmark -fps=20 -windowed 
python scenario_runner.py --scenario group:FollowLeadingVehicle
python manual_control.py
```
Changing the second line to `python scenario_runner.py --scenario FollowLeadingVehicle_1` will encounter error "Configuration for scenario FollowLeadingVehicle_1 cannot be found!"
* Debug: "ImportError: No module named 'tools.download_tools'" <br/>
Soln: need to add to [PYTHONPATH](https://stackoverflow.com/questions/51288512/difference-between-path-sys-path-and-os-environ/51290910), not only `sys.path` 
```
cd ~/coitraine
export PYTHONPATH=`pwd`:$PYTHONPATH
```
* Error: "json.decoder.JSONDecodeError: Expecting value: line 68 column 21 (char 2463)" <br/>
Soln: use json formatter to check; there shouldn't be `,` after the last element in an array
* To create a json file only for ControlLoss, previously convert `ControlLoss.xml` into json format. However, when put in `run_evaluator.sh`, nothing shows on the road, probably due to wrong coordinates. <br/>
what works now, modify `all_towns_traffic_scenarios1_3_4.json` and only keep `Scenario1` and get the file `all_towns_traffic_scenarios1.json`, which successfully show on the road. <br/>
Performance: not good. On the highway, the car just crashes into it and disappear, on the road sometimes run above it.
* Git. add a local copy of a cloned repo to my own repos and set the `origin` as `upstream` <br/>
```
 git push
remote: Permission to carla-simulator/scenario_runner.git denied to havefun28.
fatal: unable to access 'https://github.com/carla-simulator/scenario_runner.git/': The requested URL returned error: 403

 git remote -v
origin	https://github.com/carla-simulator/scenario_runner.git (fetch)
origin	https://github.com/carla-simulator/scenario_runner.git (push)

 git remote add upstream https://github.com/carla-simulator/scenario_runner.git
 git remote set-url origin https://github.com/havefun28/scenario_runner_master.git

 git remote -v
origin	https://github.com/havefun28/scenario_runner_master.git (fetch)
origin	https://github.com/havefun28/scenario_runner_master.git (push)
upstream	https://github.com/carla-simulator/scenario_runner.git (fetch)
upstream	https://github.com/carla-simulator/scenario_runner.git (push)

 git push
```

## 7.8
**Terminal commmands**
` conda deactivate` `cd CARLA_0.9.5` `./CarlaUE4.sh -benchmark -fps=20 -quality-level=Epic` <br/>
`conda activate coiltraine` `cd scenario_runner_master` `bash srunner/challenge/run_evaluator_co.sh`
*ToDo*
Design an agent for MPSC <br/>
 * "inner-loop" to simulate the vehicle model with `apply_control`
 * get bondary info that is consistent with GPS/localizaiton obtained from `transform_to_location`

*Carla*
* blueprint library for UE Carla => folder: /home/ruihan/CARLA_0.9.5/CarlaUE4/Content/Carla/Static
* [map & waypoints](http://carla.org/2018/11/16/release-0.9.1/)
* [camera & sensors](https://github.com/carla-simulator/carla/blob/master/Docs/cameras_and_sensors.md)
* questions about API
  * Error: "AttributeError: 'World' object has no attribute 'get_snapshot'". snapshots are only available to nightly built version, but running nightly built verion (CARLA_Latest) will get "rpc" error
  * Try recording and replay. Don't put anything in `client.stop_recorder()` otherwise get error 
 ```
  Traceback (most recent call last):
  File "try_CARLA.py", line 71, in <module>
    client.stop_recorder("recording01.log")
    Boost.Python.ArgumentError: Python argument types in
    Client.stop_recorder(Client, str) did not match C++ signature:
    stop_recorder(carla::client::Client {lvalue})
```
Besides, cannot find where the recording log is stored. **Need to check**
*Python*
* [`import logging`](https://docs.python.org/2/howto/logging.html)

*Others*
* git clone weichao's [MPSC repo](https://github.com/zwc662/MPSC_Guided_Imitation_Learning) but encounter the error of "ImportError: cannot import name 'constants'" when lauching `jupyter notebook`. 
Soln:
```
Anaconda
pip uninstall jupyter
pip install jupyter
pip install --force-reinstall --upgrade pyzmq
```
* Git: to ignore an untracked file, a simple way to add it to .gitignore is: Change to the root of the git tree and do `git ls-files --others --exclude-standard >> .gitignore`
* [RPC(remote procedure call) model](https://www.ibm.com/support/knowledgecenter/ssw_aix_72/com.ibm.aix.progcomc/rpc_mod.htm)

## 7.9 
1. Meeting with Wenchao
Parameter fitting
online/offline approximate model
pomdp strategy improvement
Slack penalty
Monotonic
Solve mdp
Termination
Maximize  fur
Overleaf sharing document
**Work on CARLA model extraction and help with traj generator**
2.Successfully spawn a vehicle with specific model and location. (Adding a new blueprint (see [add assets](https://carla.readthedocs.io/en/latest/how_to_add_assets/))is harder, need to work with UE, but spawn a vehicle agent is fine.) <br/>
Similar way to spawn multiple agents, which is enabled from [0.9.0](http://carla.org/2018/07/30/release-0.9.0/)
```
(base) ruihan@depend-XPS-8930:~/CARLA_0.9.5$ ./CarlaUE4.sh -fps=20
(coiltraine) ruihan@depend-XPS-8930:~/scenario_runner_master$ python3 try_CARLA.py 
```
*Python*
* random.choice(sequence)
* use [dir()](https://docs.python.org/3.5/library/functions.html#dir) to retrieve all attributes of an object

* Try to open CARLA from UnrealEngine. `(base) ruihan@depend-XPS8930:~/UnrealEngine_4.22/Engine/Binaries/Linux$ ./UE4Editor`. It takes some time at 10%, 45% but will get it. However, when I try to open the project, it fails. <br/>
Try to build CARLA from source but get error "clang 7 is required, but it's not installed. Util/BuildTools/Linux.mk:110: recipe for target 'setup' failed. make: *** [setup] Error 1" at `make launch`
So try to install clang7 ([How to install clang6 on Ubuntu16](https://blog.kowalczyk.info/article/k/how-to-install-latest-clang-6.0-on-ubuntu-16.04-xenial-wsl.html))
```
* [cannot install](https://blog.csdn.net/TYOUKAI_/article/details/78116912)
wget -O - https://apt.llvm.org/llvm-snapshot.gpg.key | sudo apt-key add -
sudo apt-add-repository "deb http://apt.llvm.org/bionic/ llvm-toolchain-bionic-7 main"
sudo apt-get update
sudo apt-get install -y clang-7.0
```
get error "ImportError: No module named 'apt_pkg'" <br/>

Possible helpful soln:
```
$ cd Unreal/CarlaUE4/
$ make CarlaUE4Editor ARGS=-clean
$ make CarlaUE4Editor
```
[get model information](https://github.com/carla-simulator/carla/issues/1329)

## 7.10
* "No module named "apt_pkg"". <br/>
Soln: `$ sudo cp apt_pkg.cpython-35m-x86_64-linux-gnu.so apt_pkg.cpython-36m-x86_64-linux-gnu.so `
* Try `libpng-dev` if get error "E: Package 'libpng16-dev' has no installation candidate"
* `sudo cp -a /path/from /path/to`
* check `ls /etc/apt/sources.list` and [remove packages](https://itsfoss.com/how-to-remove-or-delete-ppas-quick-tip/)
* [Target config multiple times](https://askubuntu.com/questions/760746/how-to-fix-error-w-target-packages-main-binary-amd64-packages-is-configured-m/760789)
* [Remove PPA](https://linuxconfig.org/how-to-list-and-remove-ppa-repository-on-ubuntu-18-04-bionic-beaver-linux)
* carla car model extraction: "You can find the information in UE4 Editor. When you open the Carla Project in the editor, you can find all the vehicle physical model in Content/Carla/Blueprints/Vehicles."
* Rename the original `UnrealEngine_4.22` into `UE` and try to rebuild everything from scratch following [build on Linux](https://carla.readthedocs.io/en/latest/how_to_build_on_linux/). For `Build Carla`, git clone the master branch of repo into `UnrealEngine` folder. The `stable` and `master` branches have totally different `Makefile`, which causes the error "No rule to make target 'launch'"
* For building from the scratch, the UnrealEngine `./Engine/Binaries/Linux/UE4Editor` works fine after `make launch` but get error of "Plugin 'ExampleDeviceProfileSelector' failed to load because module 'ExampleDeviceProfileSelector'could not be found. Please ensure the plugin is properly installed. Otherwise consider disabling the plugin for this project"
* restore the `~/.bashrc` and its `CARLA_ROOT`, the original code works fine
* To extract the vehicle model:
 1. dig the blueprints for vehicles of UnrealEngine and find the [user guide](https://docs.unrealengine.com/en-US/Engine/Physics/Vehicles/VehicleUserGuide/index.html). Yet there are many configurations including spension and tyre types and no "real" dynamics formulas are provided.
 2. Turn to use [Gaussian Process to approximate the model](https://rcheng805.github.io/files/aaai2019.pdf).
* git clone the [RL-CBF](https://github.com/havefun28/RL-CBF) repo and install necessary packages including gym, tensorflow-gpu for Python3.5, scikit-learn, tflearn, and cvxopt. <br/>
Can run the ddpg process successfully. <br/>
Look in to the code of GP model approximation.

## 7.11
1. re-git fork `scenario-runner` repo. Steps to clone and update with upstream:
```
Update your Local Repo & Push Changes
git pull upstream master - pull down any changes and sync the local repo with the central repo
make changes, git add and git commit
git push origin master - push your changes up to your fork
Repeat
```
* **New workflow with the latest CARLA**
```
cd $CARLA_SERVER_DIR  
(base) ruihan@depend-XPS-8930:~/UnrealEngine_4.22/carla/Unreal/CarlaUE4/Saved/StagedBuilds/LinuxNoEditor$ ./CarlaUE4.sh
(coiltraine) ruihan@depend-XPS-8930:~/scenario_runner$ python scenario_runner.py --scenario FollowLeadingVehicle_1 
(coiltraine) ruihan@depend-XPS-8930:~/scenario_runner$ python manual_control.py
-reloadWorld
(coiltraine) ruihan@depend-XPS-8930:CHALLENGE_PHASE_CODENAME=dev_track_2 python3 ${ROOT_SCENARIO_RUNNER}/srunner/challenge/challenge_evaluator_routes.py \
--scenarios=${ROOT_SCENARIO_RUNNER}/srunner/challenge/all_towns_traffic_scenarios1_3_4.json \
--routes=${ROOT_SCENARIO_RUNNER}/srunner/challenge/routes_training.xml \
--debug=0 \
--agent=../coiltraine/drive/CoILBaseline.py \
--config=../coiltraine/drive/sample_agent.json
```
[scenario-runner](https://github.com/carla-simulator/scenario_runner)
[coiltraine](https://github.com/felipecode/coiltraine/blob/master/docs/carla_challenge_coil_baseline.md)

* Debug: "The CARLA server uses the wrong map!
ValueError: class member 'world'' not initialized yet" <br/>
Solb: add `--reloadWorld` at the end of command <br/>
e.g. `python scenario_runner.py --scenario group:ControlLoss --reloadWorld`

2. Read paper [differentiable MPC for Control-Limits](https://arxiv.org/abs/1810.13400) and look at its implementation. But encounter bugs of unmatched dimension for `bmv` method, `C[t]` turns out to be a vector (6) instead of a 3D matrix (128, 6, 3). Unsolved yet.

3. Implement MLP to build a NN learning-based controller, with states as input and control command as output. (copy [Kggle digit recoginition implementation](https://www.kaggle.com/pinocookie/pytorch-simple-mlp) modified upon it. <br/>
* Run the BackgroundActivity scenario to collect training data. <br/>
`(coiltraine) ruihan@depend-XPS-8930:~/scenario_runner$ python scenario_runner.py --scenario BackgroundActivity_1 --reloadWorld`
* Pytorch MLP debug: 
 *  "RuntimeError: Expected object of scalar type Long but got scalar type Double for argument #2 'target'" <br/>
Soln: add `torch.set_default_dtype(torch.float64)` at the top of the script and modify the data format of the inputtraining set. `train_test_split(train_df.iloc[:, :-2].astype(np.float64), train_df.iloc[:, -2:].astype(np.long)`. Change the target (label) to long (which is integer), instead of the original control output (which is float number) <br/>
 * "RuntimeError: multi-target not supported at /pytorch/aten/src/THNN/generic/ClassNLLCriterion.c:20" <br/>
Soln: change 
```
loss_fn = nn.CrossEntropyLoss()
...
loss = loss_fn(outputs, controls)
```
to 
```
loss_fn = nn.MultiLabelMarginLoss() 
...
loss = loss_fn(outputs, controls)
```

*Others*
* install package for a specific python version. e.g. `python3.6 -m pip install --upgrade pip setuptools wheel`
* [git discussion: How to get co-ordinates of lane using sensor.other.lane_detector](https://github.com/carla-simulator/carla/issues/1254)
* [pytorch neural network](https://pytorch.org/tutorials/beginner/blitz/neural_networks_tutorial.html)

## 7.12
*Others*
* [epoch in ML](https://machinelearningmastery.com/difference-between-a-batch-and-an-epoch/)

*Python*
* [numpy expand vector to matrix => expand_dims](https://docs.scipy.org/doc/numpy/reference/generated/numpy.expand_dims.html)
* [x.view pytorch](https://stackoverflow.com/questions/42479902/how-does-the-view-method-work-in-pytorch)
* [PyTorch load/save model](https://pytorch.org/tutorials/beginner/saving_loading_models.html)

* From Shidong, ROS [cartography](https://google-cartographer-ros.readthedocs.io/en/latest/)


## 7.15
1. Reda and modify MPSC paper
2. Read `end-to-control` paper and clone its code
3. Study the code of `manual_control` and `challenge_evaluator_routes` <br/>
Modify the NNAgent and finally it can run in the challenge setting.
```
ruihan@depend-XPS-8930:~/UnrealEngine_4.22/carla/Unreal/CarlaUE4/Saved/StagedBuilds/LinuxNoEditor$ ./CarlaUE4.sh -benchmark -fps=20 -quality-level=Epic
(coiltraine) ruihan@depend-XPS-8930:~/scenario_runner$ bash srunner/challenge/run_evaluator_NN.sh
```
 * Debug: "(coiltraine) ruihan@depend-XPS-8930:~/scenario_runner$ bash srunner/challenge/run_evaluator_NN.sh
Can't get attribute 'MLP' on <module '__main__' from '/home/ruihan/scenario_runner/srunner/challenge/challenge_evaluator_routes.py'>" <br/>
Soln: copy the import path
```
# for use nn_controller
from NN_controller import *
from NN_controller import MLP
```
to `challenge_evaluator_routes.py`, not only `NNAgent.py`
 * Debug: "WARNING: attempting to destroy an actor that is already dead:" <BR/>
 Soln: to initiate an object, use `carla.Location`, e.g. `location = carla.Location(x=input_data['GPS'][1][0], y=input_data['GPS'][1][1], z=input_data['GPS'][1][2])` <br/>
 Soln: `wp = map.get_waypoint(location)` only output one waypoint, and not as array. Using `wp[0]` or `len(wp)` will cause above error.

*Others*
* [Latex revision control tips](https://tex.stackexchange.com/questions/232/how-can-you-use-latex-to-write-a-document-with-other-people)
* [ToDoNotes](http://empiricalev.blogspot.com/2013/05/using-latex-todonotes-on-document-with.html)

## 7.16
*ToDo*
1. Try `e2c` and adapt it to Carla agent

*Python*
* [Python absolute & relative import path](https://realpython.com/absolute-vs-relative-python-imports/)
* [`__all__`](https://stackoverflow.com/questions/44834/can-someone-explain-all-in-python): It's a list of public objects of that module, as interpreted by `import *`. It overrides the default of hiding everything that begins with an underscore.

*Others*
* [Autoencoder](https://www.jeremyjordan.me/autoencoders/)
* [nn.ModuleList vs nn.Sequential](https://discuss.pytorch.org/t/when-should-i-use-nn-modulelist-and-when-should-i-use-nn-sequential/5463/4)

## 7.17
1. Try to use carla/data_collector, give up. Use CameraManager in  manual_control.py instead.
*Debug*
* 'AttributeError: 'list' object has no attribute 'dim'" when running `e2c_controller.py`-> `train` <br/>
Soln: `return list(zip(*self._processed))[0]` for class `CarlaData` and `return self.x_val[index]` for class `CarlaDataPro`
* "RuntimeError: Expected object of scalar type Float but got scalar type Double for argument #2 'mat2'" <br/>
Soln: `return torch.from_numpy(control).float()` in `process_control` and reload the `processed.pkl`

*Python*
* `np.save` save one array, `np.savez` save arrays
* `glob`
```
Order is arbitrary, but you can sort them yourself

If you want sorted by name:

sorted(glob.glob('*.png'))
sorted by modification time:

import os
sorted(glob.glob('*.png'), key=os.path.getmtime)
sorted by size:

import os
sorted(glob.glob('*.png'), key=os.path.getsize)
```

*Others*
* [PyTorch model basics](https://cs230-stanford.github.io/pytorch-getting-started.html)
* [pyTorch save & load model](https://pytorch.org/tutorials/beginner/saving_loading_models.html#what-is-a-state-dict)

## 7.18
1. Debug e2c controller. <br/>
* `RuntimeError: size mismatch, m1: [11264 x 200], m2: [52800 x 150] at /pytorch/aten/src/TH/generic/THTensorMath.cpp:961` <br/>
Soln: <br/>
 * use `x = x.view(x.shape[0], -1)` before `optimizer.zero_grad()` in `tain_loader` `for` loop to [flatten the vector](https://stackoverflow.com/questions/54218604/size-mismatch-m1-3584-x-28-m2-784-x-128-at-pytorch-aten-src-th-generic)
=>  `size mismatch, m1: [128 x 17600], m2: [52800 x 150]`
* use `RGB` instead of `L` (grayscale) for `ToTensor` in `_process_img` *Can u be a bit more sensitive to numbers,i.e. 528 = 3\*176*
* `RuntimeError: The size of tensor a (100) must match the size of tensor b (128) at non-singleton dimension 1` <br/>
Soln: change `add(o)` to `add(o.unsqueeze(2))` in `Transition.forward`
2. Another workflow for removing large file that is mistakenly committed and push failed.
```
git filter-branch -f --index-filter 'git rm --cached --ignore-unmatch <dir/file>'
git push (failed)
git push -f origin master
```
Note: If you do not wish to merge the remote branch into your local branch (see differences with git diff), and want to do a force push, use the push command with `-f`, e.g. `git push -f origin <branch>`, where origin is the name of your remote repo.
3. Try RGB and gray scale images, respectively. Finally use gray, smaller dimension, not bad performance with enough data. <br/>
Also try opencv and PIL, finally choose PIL. Opencv will result in negative training loss and weird images.
4. Pickle streams are entirely self-contained, and so unpickling will unpickle one object at a time.

Therefore, to unpickle multiple streams, you should [repeatedly unpickle the file until you get an EOFError](https://stackoverflow.com/questions/12761991/how-to-use-append-with-pickle-in-python)
5. Debug: encounter `OSError: [Errno 12] Cannot allocate memory` during testing when use large dataset <br/>
Soln: restart the desktop

*Others*
* [bmm](https://kite.com/python/docs/torch._C.bmm): two 3D tensors. batch1:  b * n * m, batch2: b * m * p, out: b * n * p)
* [PIL image convert](https://pillow.readthedocs.io/en/stable/reference/Image.html#PIL.Image.Image.convert) <br/>
  ToTensor: https://pytorch.org/docs/stable/torchvision/transforms.html#torchvision.transforms.ToTensor

## 7.19
*ToDo*
1. Check e2c model \[tick\]
2. Build dynamics model

1. Meetig with Wenchao <br/>
 * For NN agent / localizaiton info concatenated to z, use relative position of waypoints
 * Look into Local planner API, try to use it sub-trajectory planning MPSC mainly helps trajectory following, e.g. 10 steps ahead of local traj.
 * For end-to-end vision module, can do perception don't want...(lane detection etc.) 
 * Use depth camera instead of RGB, smaller dimension & more depth info. can further reduce dimension by crop fov or down-sampling (by lines/grids). Urban/countryside setting, "walls" on the road boundary
 * E2C worth trying, autoencoder.
 * account: need BU account to access VPN ssh/VNC, then set up dns server connection on the desktop

2. modify the network. Instead of training a separate dynamics model, we can concatenate `m_t` to each `x_t` and `z_t` using a constant layer and the the network as a whole.

*Others*
* [PyTorch basic operations](https://jhui.github.io/2018/02/09/PyTorch-Basic-operations/) e.g. mean, var
* [reparameterization trick](http://blog.shakirm.com/2015/10/machine-learning-trick-of-the-day-4-reparameterisation-tricks/)
* [simple layers of PyTorch](https://nn.readthedocs.io/en/rtd/simple/index.html)

## 7.20
* ToDo*
* Modify the network to concatenate measurement to image 
1. In `Encoder_cat` and `Decoder_cat`, use [`torch.cat`](https://pytorch.org/docs/stable/torch.html#torch.cat), [`torch.split`](https://pytorch.org/docs/stable/torch.html#torch.split) for concatenating and splitting the `img` and `m`, respectively.
2. clean the program, deleting the `mode` and modify some var names e.g. `x` -> `img`
**Debug: `inf` in KLD_element**

## 7.21
1. Debug: 
 * `inf` in KLD => `nan` loss <br/>
 Reason: the way we construct layer for measurement `m` <br/>
 Soln: tried `nn.Identity`; `nn.Linear(dim_m, dim_m*)`; `m_mean = m, m_var = torch.ones/randn(m.size())`; finally use 
 ```
 m_mean = m
	m_var = torch.Tensor(m.size()).uniform_(0.1, 0.9)
 ```
 to keep var positive so that in `binary_crossentropy`, log function will not become nan

## 7.22
*ToDo*
* It's fine to use Background Activity for data collection, sunny weather. The simpler, the better.
* Our scenario: learn a basic NN policy. Add a NPC in front, try to avoid it.
* Continue to use depth camera.
* Prioritize:
	* loss function. (normalize m, based on relative waypoint location and speed)
	* look into local & global planner (UnrealEngine4.22 PythonAPI) to get local waypoint
	* learn good latent vector, e.g. adjust optimizer
	* learn  a rather good policy
	* add NPC
	* compare performance
	
	* fix scenario_runner `--reloadWorld` bug
*Log*
* For background activity, speed limit varies from 30 t0 90 (as far as I observe), so take 90 as maximum
* tried to use `map.get_waypoint`, but it returns current location instead of nearest path waypoint, just adding more attributes. so we need to look into local and/or global planner, which is found in `UnrealEngine4.22/carla/PythonAPI/carla/agents/navigation`
* `LocalPlanner`: connected with longitudinal and lateral PID controller and manage a queue of waypoints
* `GlobalRoutePlanner`: given origin and destination, use A* algo to find a path, add points to edges, and return a route trace.
* `waypoint.next()` `_compute_next_waypoints(k=1)` method may help generate waypoints.
* modify the `.xml` file and refer to `class ActorConfiguration(ActorConfigurationData):` in `config_parser.py` for `other actor config`.
* waypoints are added into `RouteConfiguration.data`
* rolename: 'hero' for ego vehicle, and 'scenario' for others

*Note*
[A* search](https://www.hackerearth.com/zh/practice/notes/a-search-algorithm/): consider `f = g+h` and the only condition for h(x) to be consistent is that - for all the nodes, the difference of h values between them should be lower then the distance between their g values. 

## 7.23
*Debug*

	* "different worlds": world in `_parse_image_and_measurement`is World(id=3898079997334768281), while enable_e2c has `<__main__.World object at 0x7ff2927e01d0>`. my_world World(id=16923728823182281709) <br/>
Soln: save `m_tensor` and `img_tensor` as attributes of `CameraManager` and load `e2c_model` and `nn_model` from `__main__.World object`
	* "Boost.Python.ArgumentError: Python argument types in None.None(VehicleControl, numpy.float32 did not match C++ signature: None(carla::rpc::VehicleControl {lvalue}, float)" <br/>
	Soln: [convert np datatype to native datatype](https://stackoverflow.com/questions/9452775/converting-numpy-dtypes-to-native-python-types) e.g. `self._control.throttle = u[0].item()`, where `u` is np array.

1. Finish building the pipeline.(take camera sensor image, location, velocity, pass to e2c model to get latent vector, pass to nn model to get control) <br/>
	* e2c_controller_cat.py to train e2c model
	* e2c_NN.py to train NN model
	* manual_control_test_NN.py to test the model
2. Prioritize:
	* Look into coiltraine, see if can copy the network to NN model
	* try different optimizer, adjust parameter, till find a rather good policy (may double check control)
	* add NPC, refer to Nashita's pedestrian
3. The vehicle keeps full throttle and steer, hence modification needed. <br/>
Try: copy MLP neural network from CoIL, clip the action to \[0,1\], and use binary cross-entropy for the loss function. <br/>
Debug: "RuntimeError: grad can be implicitly created only for scalar outputs" add `.mean(()` as in `loss = -binary_crossentropy(u, outputs).sum(dim=1).mean()`


## 7.24
1. Use coil model. The performance is still bad. e.g. `u  [0.000000e+00 2.008999e-07 1.000000e+00]`, which gives `VehicleControl(throttle=0.000000, steer=-1.000000, brake=0.000000, hand_brake=False, reverse=False, manual_gear_shift=False, gear=0)` (I force the brake to be 0)
2. While waiting for the model to train, git clone `minetorch` repo and learn to draw training loss. <br/>
see `drawers.py` for its implementation of drawing the plots.
3. Debug: the vehicle is not moving. Soln: `brake` matters (but don't know why), currently force it to be zero.
4. Tried different optimizer and loss func. <br/>
	* SGD + binary CE => turn crazely
	* adam + weighted SE => throttle = 0 e.g. `VehicleControl(throttle=0.000000, steer=-0.989607, brake=0.000000, hand_brake=False, reverse=False, manual_gear_shift=False, gear=0)` <br/>
	It's learning but not learning well.

*ToDo*
* Try to partially copy the state_dict of coil baseline_18000 model, modify the layers, and adapt to our agent model. [warmstart](https://pytorch.org/tutorials/beginner/saving_loading_models.html#warmstarting-model-using-parameters-from-a-different-model)
* move the training process to CUDA
* Plot the training loss 

*Notes*
* [Python format and f-string](https://realpython.com/python-f-strings/)
* [PyTorch optimizer](https://pytorch.org/docs/stable/optim.html)
* [guide for hyperparams tuning](https://blog.floydhub.com/guide-to-hyperparameters-search-for-deep-learning-models/)
* PyTorch set [`model.train()` and `model.eval()` mode](https://jamesmccaffrey.wordpress.com/2019/01/23/pytorch-train-vs-eval-mode/)

## 7.25
*Debug*
* "python: can't open file '/home/ruihan/scenario_runner/srunner/challenge/challenge_evaluator_routes.py--scenarios=/home/ruihan/scenario_runner/srunner/challenge/Town1_traffic_scenarios1.json': [Errno 2] No such file or directory" <br/>
Soln: should leave a space at each line before `\`

[CARLA MPC post](https://medium.com/asap-report/introduction-to-the-carla-simulator-training-a-neural-network-to-control-a-car-part-2-6a71115f2940)

* diable the traffic lights, remove other actors.
* train the NN controller with different number of wps look-ahead, optimizer and loss func combination.

## 7.26
1. try to initiate different starting condition and collect data

* Log
	*       # Q: whether set_transform works at current tick
                # A: No, because get_transform/velocity method returns the setting in the last tick
                # cur_loc = world.vehicle.get_transform()
                # cur_vel = world.vehicle.get_velocity()

	*
```
204912 Transform(Location(x=221.589508, y=-388.642517, z=-0.010099), Rotation(pitch=0.010983, yaw=-179.859695, roll=0.084959))
204913 Transform(Location(x=220.479218, y=-388.646698, z=-0.010133), Rotation(pitch=0.014617, yaw=-179.720428, roll=0.100143))
frame 204915 set to  Transform(Location(x=402.567078, y=-15.598181, z=0.000000), Rotation(pitch=0.000000, yaw=293.138885, roll=0.000000))
204915 Transform(Location(x=218.262909, y=-388.659882, z=-0.010157), Rotation(pitch=0.017260, yaw=-179.440491, roll=0.126653))
204915 Transform(Location(x=218.262909, y=-388.659882, z=-0.010157), Rotation(pitch=0.017260, yaw=-179.440491, roll=0.126653))
204918 Transform(Location(x=214.937088, y=-388.690826, z=-0.009876), Rotation(pitch=-0.013920, yaw=-179.187561, roll=0.126473))
204918 Transform(Location(x=214.937088, y=-388.690826, z=-0.009876), Rotation(pitch=-0.013920, yaw=-179.187561, roll=0.126473))
204921 Transform(Location(x=400.473267, y=-15.640567, z=-0.007076), Rotation(pitch=-0.222541, yaw=-66.817017, roll=1.751169))
204921 Transform(Location(x=400.473267, y=-15.640567, z=-0.007076), Rotation(pitch=-0.222541, yaw=-66.817017, roll=1.751169))
204921 Transform(Location(x=400.473267, y=-15.640567, z=-0.007076), Rotation(pitch=-0.222541, yaw=-66.817017, roll=1.751169))
204924 Transform(Location(x=397.843323, y=-15.565899, z=-0.008533), Rotation(pitch=-0.294128, yaw=-65.827812, roll=4.280376))
204925 Transform(Location(x=397.096436, y=-15.487780, z=-0.008827), Rotation(pitch=-0.257204, yaw=-65.411888, roll=4.753189))
204925 Transform(Location(x=397.096436, y=-15.487780, z=-0.008827), Rotation(pitch=-0.257204, yaw=-65.411888, roll=4.753189))
```
Possible soln: `client = carla.Client(args.host, args.port, worker_threads=1)`, `apply_batch`

## 7.27
1. [Carla thread](https://github.com/carla-simulator/carla/issues/1563#issuecomment-486704035)
2. Try `worker_threads = 1`, but the simulator does not work, probably because at least 2 threads are required, see above. <br/>
Try `apply_batch` and `settings.synchronous_mode = True` (see [configuring](https://carla.readthedocs.io/en/latest/configuring_the_simulation/)), but the frame number is still different.


## 7.28
1. Solve the problem of time difference between `set_transform` and `get_control`. <br/>
Soln: add `world.world.wait_for_tick()` at appropriate pos for a "tick". Hence, can save a transition, but there is stll a small error between `set_transform` and `get_transform` 
2. save the data in csv format

*ToDo*
1. why negative loss
2. still bad performance
3. `record_e2c_init_diff`: background activity is not long enough to collect data for all init waypoints; actually, just one

*Python*
* change numpy datatype to naive type: `type(np.float64(0).item())`

## 7.29
1. Carla vehicle dynamics model: [NVIDIA's PhysX vehicle model](https://github.com/carla-simulator/carla/issues/115#issuecomment-355941800) see [source](https://docs.nvidia.com/gameworks/content/gameworkslibrary/physx/guide/Manual/Vehicles.html)
2. matplot: use `savefig` before `plt.show()`
3. [RNN with PyTorch](https://github.com/gabrielloye/RNN-walkthrough/blob/master/main.ipynb) LSTM 
4. Tutorial for training NN controller [blog](https://medium.com/asap-report/introduction-to-the-carla-simulator-training-a-neural-network-to-control-a-car-part-1-e1c2c9a056a5) [code](https://github.com/asap-report/carla/tree/racetrack/PythonClient/racetrack)
## 7.30
1. Meeting with Wenchao <br/>
	* Continue with experiments 
	* Visualize the training results, e.g. plot the trajectory ("how shall I interpret the loss/y-axis?")
	* try system identification for dynamics model. Matlab existiing code (in case you are not aware of methods other than NN)
2. Plot the traj for pred_state and next_state, respectively. use [matplot.plt scatterplot](https://matplotlib.org/3.1.1/api/_as_gen/matplotlib.pyplot.scatter.html)
3. Try use [System ID python package](https://github.com/CPCLAB-UNIPI/SIPPY), fail at installation, `Cmake dir error`
4. Try grid search. [ray tune](https://github.com/ray-project/ray/tree/master/python/ray/tune/examples)

*Debug*
* "Using CUDA Pytorch RuntimeError: Expected object of backend CUDA but got backend CPU running" <br/>
Soln:
```
device = torch.device("cuda:0" if torch.cuda.is_available() else "cpu")
model = model.to(device)
for i, (data, target) in enumerate(data_loader):
	data, target = data.to(device), target.to(device)
	output = model(data)
```
* Naive implementation of Grid Search
```
num_wps_range = [10, 20, 30, 40, 50]
lr_range = [0.00001, 0.0001, 0.001, 0.01, 0.1]
batch_range = [32, 64, 128, 256]
params_product = [(num_wps,lr, batch_size) for num_wps in num_wps_range for lr in lr_range for batch_size in batch_range]
for params_list in params_product:
	num_wps = params_list[0]
	lr = params_list[1]
	batch_size = params_list[2]
	# model.train()
```


## 7.31
*Debug*
* In `test_NN`, "  File "manual_control_test_NN.py", line 587, in tick
    'Server:  % 16d FPS' % self.server_fps,
OverflowError: cannot convert float infinity to integer", if set traffic lights to Green
* Infinity `get_fps()`. Soln: restart the computer
* PyTorch tensor to numpy `loss.data.cpu().numpy()`

## 8.1
1. Learn to use examples of `synchronous_mode` and `BasicAgent`. Change `CARLA_SERVER_DIR` and add to pythonpath.
2. 
*Python*
* Dictionary to attribute
```
class AttrDict(dict):
    def __init__(self, *args, **kwargs):
        super(AttrDict, self).__init__(*args, **kwargs)
        self.__dict__ = self
```

*Carla*
* useful code of [spawning two actors in syn mode](https://github.com/carla-simulator/carla/issues/1462)


## 8.2 
0. Qingqing's final defense
1. Implement the NN_controller with one target_waypoint look ahead in synchronous mode

*Debug*
* "typeerror: 'VehicleControl' object is not iterable" <br/>
Soln: `run_step` functions have two ways to return. Make sure both return the same number of outputs (not one output for one case, and two outputs for another)
* Git undo last commit before push
```
git reset --soft HEAD^ 
or
git reset --soft HEAD~1

Then reset the unwanted files in order to leave them out from the commit:
git reset HEAD path/to/unwanted_file 
or
git reset
(DO NOT RUN git reset --hard.

It will not only unstage your added files, but will revert any changes you made in your working directory. If you created any new files in working directory, it will not delete them though.)

Now commit again, you can even re-use the same commit message:
git commit -c ORIG_HEAD  
```
or
```
git diff --name-only HEAD^ - (optional) use to list the files that changed in the last commit.
git reset HEAD^ path/to/file/to/revert - to reset the index to that last version, leaving the working copy untouched.
git commit --amend - to amend that last commit to include the index changes
```
[Undo commit](https://bytefreaks.net/programming-2/how-to-undo-a-git-commit-that-was-not-pushed) <br/>
[git reset docs](https://git-scm.com/docs/git-reset) <br/>

*Python*
* get files in dir and sub_dir
```
You can also use the glob module along with os.walk.

import os
from glob import glob

files = []
start_dir = os.getcwd()
pattern   = "*.log"

for dir,_,_ in os.walk(start_dir):
    files.extend(glob(os.path.join(dir,pattern))) 
```
* [read and write csv](https://www.guru99.com/python-csv.html)
* count row numbers `row_count = sum(1 for row in fileObject) ` Note: which may close the file, need to reopen the file for further action
* Pytorch retrain the model. put `model = model.to(device)` before `optimizer.load_state_dict(checkpoint['optimizer_state_dict'])`

## 8.3
1. Debug for NN_controller.py
2. Write `NN_controller_img.py` and build the network including perception and measurement modules, based on CoILICRA model. Learn to load the pre-trained model based on key, value of state_dict.

* Sublime fold lines. `Edit -> Code folding -> Fold/Unfold` Shortcut: `Ctrl + shift + [` (`]` for unfolding)

## 8.4 
1.Unfortunately, last night nothing went on.
2. Fortunately, build vnc server/viewer connection. Just download from [official website](https://www.realvnc.com/en/connect/download/viewer/), sign in and use `ifconfig` to check ip address of the server for configuration.
3. The NN model goes fine and add recorder to `test_NN.py`. `replay_record.py` replay the log file in server (map), not pygame. `examples/start_replaying` also works.

## 8.5
1. Check the model with num_wps = 10. It only works well for `i=0, j=2`. <br/>
ToDo: collect more data and train with larger num_wps to compare the performance
2. Prepare slides for presentation.
3. To visualize Pytorch model:
	* `print(model)` or `summary(model, input_shape)`
	* possible alternatives: [daft](http://daft-pgm.org/), [make_dot](https://github.com/szagoruyko/functional-zoo/blob/master/resnet-18-export.ipynb)
	* [neural network zoo](http://www.asimovinstitute.org/neural-network-zoo/)
4. Debug `NN_controller_img.py`
`RuntimeError: Given groups=1, weight of size 64 3 7 7, expected input[64, 1, 88, 200] to have 3 channels, but got 1 channels instead` <br/>
Soln: refer to `coil_dataset.py` L104-118, use cv2 instead of PIL to process image.
* `os.walk()` returns current dir as the first element and subdirectoies as the rest of the list


*Carla notes for BasicAgent*
1. Low level control: it uses PID control. Longitudinal--speed control PID--throttle; Lateral--position control PID--steering. <br/>
For lateral controller, the error term is computed by calculating the angle difference of two vectors, v_vec (future pos with current yaw - current pos) and w_vec(waypoint pos - current pos)
2. Navigation: 
	* The global planner (global_route_planner_dao.py) queries the topology information from the whole map, get the road segments, and add waypoints to `seg_dict` wherever the dist > sampling radius. <br/>
	* The local planner manages the waypoint queue (obtained from global planner) and waypoint buffer (based on global planner and Road option), passes the target waypoint (horizon=1) to VehicleController


## 8.6
1. Meet with Wenchao
	 * check out [neural simplex architecture](https://arxiv.org/abs/1908.00528)
	 * pure pursuit
2. Implement buffer for `test_NN` so that the future points don't change instantaneously after the veh deviates a bit

*Python*
* [np.frombuffer](https://docs.scipy.org/doc/numpy/reference/generated/numpy.frombuffer.html)
* [np.deque](https://docs.python.org/2/library/collections.html)
* [enumerate](https://www.geeksforgeeks.org/enumerate-in-python/)
* Draw NN graph [mlp with customized number of neurons](https://gist.github.com/craffel/2d727968c3aaebd10359), [torch nn graph](https://github.com/torch/nngraph)

3. [Ubuntu screen recorder](http://tipsonubuntu.com/2018/06/09/record-gnome-desktop-ubuntu-18-04/)

## 8.10
* `ssh ruihan@155.41.13.248`

## 8.16 
* Write report
**Useful links for Latex**
* [cite in Latex](https://libguides.usask.ca/c.php?g=218034&p=1446425)
* [sections and subsections](https://www.overleaf.com/learn/latex/Sections_and_chapters)
```
\section{Test Section}
test
\subsection{Test Subsection}
test
\subsubsection{Test Subsubsection}
test
\paragraph{Test Modified Paragraph}
test
```
* to insert algorithm 
```
\usepackage{algorithm}
\usepackage{algorithmic}
```
