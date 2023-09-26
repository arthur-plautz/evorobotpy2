# evorobotpy2

## Setup

Firstly, if you are using Linux, install the following libraries:
```bash
sudo apt-get install python-dev python3-dev
sudo apt-get install libgsl-dev
sudo apt install libopenmpi-dev
sudo apt-get install g++
sudo apt-get install swig
```
After that, make shure to create a virtual environment in the root directory:
```bash
virtualenv -p python3 venv
source venv/bin/activate
```
Then install the requirements:
```bash
pip install -r requirements.txt
```

## Compiling

Before running the models, you need to compile the resource that you'll use.
The main resources available are: ErDiscrim, ErDpole, ErPredprey, ErStaybehind and Evonet.
You can look for the compile command in your terminal by writing `make compile_` and then pressing `tab` to see all commands.
You can find all of them in the `Makefile`, but here's a list:
```
make compile_erdiscrim
make compile_erdpole
make compile_evonet
make compile_erpredprey
make compile_erstaybehind
```
And if you just want to install all of them at once:
```
make compile_all
```

## Running

To run a model, first go to the target environment, and then run the following command:
```bash
cd $env
python ../bin/es.py -f ./$file.ini -s $seed
```
Example:
```bash
cd xdpole
python ../bin/es.py -f ./ErDpole.ini -s 1
```
To see all execution options run:
```bash
python ../bin/es.py --help
```

## Contributing

If at some point you've installed a new package, and therefore it will be needed to run the new code, you can update the requirements by running:
```bash
make update_requirements
```

## Concepts

A tool for training robots through evolutionary and reinforcement learning methods

The tool is documented in [How to Train Robots through Evolutionary and Reinforcement Learning Methods](https://bacrobotics.com/Chapter13.html) which includes also a detailed tutorial with exercises.

For an introduction to the theory and to state-of-the-art research in this areas, see the associated open-access book [Behavioral and Cognitive Robotics: An Adaptive Perspective](https://bacrobotics.com)

## Credits

This repository is a fork of the evorobotpy2 by Stefano Nolfi:
```
@misc{evorobotpy2,
  author = {Stefano Nolfi},
  title = {A tool for training robots through evolutionary and reinforcement learning methods},
  year = {2020},
  publisher = {GitHub},
  journal = {GitHub repository},
  howpublished = {\url{https://github.com/snolfi/evorobotpy2}},
}
```
