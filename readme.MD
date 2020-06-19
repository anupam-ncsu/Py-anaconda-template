# Python Anaconda Data Science Project Template



#### Before you start
- System must have python3 , pip3
```
brew install python
// Homebrew installs both python3 and pip
```
- Install anaconda and activate
```zsh
https://docs.anaconda.com/anaconda/install/mac-os/
https://docs.anaconda.com/anaconda/user-guide/troubleshooting/#conda-command-not-found-on-macos-or-linux
```
- verify that the shell can reach conda
```bash
source ~/.bash_profile
conda list
```
If the command responds, then you have anaconda running as expected. Else debug


#### Package Installation
Anaconda comes with a preferred list of dependencies installed, but we will need to install more depending on the project we are working on.
These modules are installed through our file **requirement.txt** execute through the script **install_packages.sh**.  
```bash
./install_packages.sh
```

#### Conda Virtual Environment
Python uses virtual environment to isolate and manage dependcies that are required in a project.
This project creates such virtual environment using a *.yml file.
The file specifies a name for the virtual environment and the dependencies .  
Note: To use a dependcy we need have it installed first on anaconda using the step above.

```bash
conda env export > list.yml
```
This gets you all the things that you can copy over to your virtual environment dependcies.
If anything is missing from here, please install them on anaconda navigator first before using them

- To create the virtual environment
```bash
conda env create -f environment.yml
``` 
- to update an environment if you add new dependencies before activaing:
```bash
conda env update –f environment.yml –n your_env_name
```
- if you are already inside the virtual env and want to update dependecies:
```bash
conda env update --file environment.yml
```
- to remove the virtual environment after use:
```bash
conda env remove -n <NAME-OF-THE-VIRTUAL-ENV-FROM-YML-FILE>
```

#### Execute code
- Create the virtual environment
- Activate environment
```bash
conda activate <NAME-OF-THE-VIRTUAL-ENV-FROM-YML-FILE>
```
- At this point, we have a virtual environment with all the dependencies.
To run the sample code
```bash
python /src/test/py
```