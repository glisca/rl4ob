# Reinforcement Learning for Optimizations in Biomechanics (RL4OB)

- todo(lisca): update the description of the repository.

## 1. System dependencies

### 1.1 Ubuntu 22.04

```
sudo apt install update && sudo apt update && sudo apt autoremove
```

### 1.2 Nvidia driver 535

Install the Nvidia driver:

```
sudo apt install nvidia-driver-535
```

<span style="color:red">
&rarr; Reboot your computer! Otherwise the tensorflow and pytorch will fail.
</span>

## 2. Worspace layout

2.1 Export the `WS_BIOMEC` environment variable:

```
export WS_BIOMEC=$HOME/biomec
```

2.2 Create the following directory tree into your home directory:

```
cd $HOME && \
mkdir -p $WS_BIOMEC/build/btk/ && \
mkdir -p $WS_BIOMEC/build/opensim/core/ && \
mkdir -p $WS_BIOMEC/build/opensim/dependencies/ && \
mkdir -p $WS_BIOMEC/build/opensim/gui && \
mkdir -p $WS_BIOMEC/build/mujoco/ && \
mkdir -p $WS_BIOMEC/install/btk/ && \
mkdir -p $WS_BIOMEC/install/matlab/ && \
mkdir -p $WS_BIOMEC/install/mujoco/mujoco210/ && \
mkdir -p $WS_BIOMEC/install/opensim/core/ && \
mkdir -p $WS_BIOMEC/install/opensim/dependencies/ && \
mkdir -p $WS_BIOMEC/install/opensim/gui/ && \
mkdir -p $WS_BIOMEC/src/anaconda/ && \
mkdir -p $WS_BIOMEC/src/matlab/ && \
mkdir -p $WS_BIOMEC/src/netbeans/ && \
mkdir -p $WS_BIOMEC/data/
```

## 3. Anaconda

The entire software stack will be contained into conda environment, isolated from your system packages. Only a few debian packages will be installed into your system.

3.1 Download Anaconda.

```
cd $WS_BIOMEC/src/anaconda/ && \
wget https://repo.anaconda.com/archive/Anaconda3-2024.06-1-Linux-x86_64.sh
```

3.2 Install Anaconda.

```
bash $WS_BIOMEC/src/anaconda/Anaconda3-2024.06-1-Linux-x86_64.sh -p $WS_BIOMEC/install/a202406/
```

Confirm the installation process:

```
Welcome to Anaconda3 2024.06-1

In order to continue the installation process, please review the license
agreement.
Please, press ENTER to continue
>>> < just press the ENTER key >
```

Accept the license agreement:

```
...
...
Do you accept the license terms? [yes|no]
```

Type in `yes` and press enter.

```
[no] >>> yes
```

Confirm the location:
```
...

...

Anaconda3 will now be installed into this location:
/home/<your use name>/biomec/install/a202406/

  - Press ENTER to confirm the location
  - Press CTRL-C to abort the installation
  - Or specify a different location below

[/home/<your user name>/biomec/install/a202406/] 
```

Press enter.

```
>>> < enter key >
```

&rarr; Feel free to grab yourself a coffee. Probably it will take Anaconda more tha 2 minutes (depending on your internet speed) to to download and install all default packages which it needs.

When the installer asks:

```
...

...

Do you wish the installer to initialize Anaconda3
by running conda init? [yes|no]
```

Type in `no` and press enter, because in the future you will initialize anaconda manually, otherwise anaconda will be activated automatically each time you start a new temrinal. We definitely do not want that!

You are done with installing Anaconda3.

## 4. `ob-rl-ai` conda environment

4.1 Clone the `athlete` (this repository) repository inside the `src` directory.

```
cd $WS_BIOMEC/src/ && \
git clone git@gitlab.lrz.de:glisca/ob-rl-ai.git
```

4.2 Create the `ob-rl-ai` conda environment (and automatically install the required dependencies).

&rarr; Run the following command and feel free to grab yourself a coffee. Probably it will take anaconda more tha 5 minutes (depending on your internet speed) to to download and install all packages which the about to be installed `ob-rl-ai` conda evironment needs.

```
$WS_BIOMEC/install/a202406/bin/conda env create -f $WS_BIOMEC/src/ob-rl-ai/conda/ob-rl-ai.yml
```

A message similar to the following:
```
...
done
#
# To activate this environment, use
#
#     $ conda activate ob-rl-ai
#
#     $ conda deactivate

Retrieving notices: ...working... done
```
confirms that your new `ob-rl-ai` conda environment was successfully installed.

4.3 Activate manually the `ob-rl-ai` conda environment.

```
source ~/biomec/install/a202406/bin/activate ob-rl-ai
```

## 4. Install the MuJoCo's system dependencies

```
cd $WS_BIOMEC/src/ob-rl-ai && \
sudo bash setup.sh
```

## 5. Run the tutorials

Start the JupyterLab:

```
jupyter lab
```

### 5.1 Run the MuJoCo tutorial



### 5.2 Run the stable-baselines3 tutorial
