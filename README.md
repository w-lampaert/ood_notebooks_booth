# Notebooks for the Ondemand booth at All Areas

You can find all notebooks for the Open Ondemand booth at the All Areas day here. A section is provided for each of them here, which includes the installation 
instructions for the conda environment and where to find the data. Feel free to add anything that you consider interesting in the context of showcasing JupyterLab.

## Python notebook
This is a notebook that uses the standard MNIST example, a network that can recognize handwritten digits. 

Create your conda environment as follows:

```
conda create -n tensorflow
source activate tensorflow
conda install tensorflow=2.9 python matplotlib datetime ipykernel
python -m ipykernel install  --prefix=${VSC_HOME}/.local/ --name 'tensorflow'
```
It is important to not use Tensorflow <= 2.9, as some functionality has changed after this version.

Once you've installed the kernel in this way, you should be able to see the kernel in your JupyterLab launcher. Open the notebook and select the correct kernel in
the right upper corner.

## R notebook

This notebook uses a dataset containing data from the Eurovision song festival. For now it only contains some very basic data manipulation and two graphs that show
the (pretty sad) scores of Belgium over the years. If you have any inspiration for nicer graphs, feel free to add them!

Create your conda env as follows:

```
conda create -n r_env
source activate r_env
conda install -c conda-forge r-base r-data.table r-ggplot2 jupyter_client r-irkernel
Rscript -e 'IRkernel::installspec(prefix="${VSC_HOME}/.local/", name="r_env", 	displayname="r_env")’
```
The dataset is downloaded from Kaggle, but you need a login for that. Also, I changed some minor things before reading it into R, so it would be better to just 
copy it from my $VSC_DATA (it is located in '/data/leuven/342/vsc34271/ondemand_booth/datasets') to your own data folder.

## MaNGO notebook
This is a notebook created by the RDM team. It contains general iRODS and MaNGO functions. Create your conda env and kernel as follows:

```
conda create -n irods
conda install python pip ipykernel
<your_miniconda_location>/envs/irods/bin/pip install python-irodsclient
<your_miniconda_location>/envs/irods/bin/pip install ipython
python -m ipykernel install  --prefix=${VSC_HOME}/.local/ --name 'irods'
```



