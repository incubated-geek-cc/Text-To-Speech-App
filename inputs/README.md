# Host Your Own Offline Mapping Server
## What this is - A step-by-step tutorial on how to host an offline basemap for other GeoSpatial applications to use.
### Specific steps are documented in the following [notebook](https://github.com/incubated-geek-cc/offline-mapping-server/blob/master/Host%20Your%20Own%20Offline%20Mapping%20Server.ipynb)
### Publication of project on [Towards Data Science (TDS)](https://towardsdatascience.com/host-your-own-offline-mapping-server-with-jupyter-notebook-ff21b878b4d7)

#### Pre-requisites to run jupyter notebook locally
* **Running:** Python 3.7.9
* **Using:** pip 20.2.4
* **OS:** Windows 10

#### Functionality of each `.bat` file

Filename | Functionality
------------ | -------------
activate_env.bat | activate virtual environment .env and upgrade pip on Windows OS
pip_freeze.bat | output all python packages into requirements.txt file and overwrites it
pip_install_requirements.bat | pip install all python packages based on requirements.txt file
run_jupyter_notebook.bat | run jupyter notebook on port 8889
python/scripts/01_stream_tiles.bat | run python script stream_tileimages.py i.e. start streaming map tile images and save into local folders
transform_to_mbtiles.bat & python/scripts/02_transform_to_mbtiles.bat | use mbutil lib to package tile image into mbtiles file
python/scripts/03_run_flask_app.bat | run python script serve_web_app.py and navigate to http://localhost:9000 to view basemap

* The folder `python_scripts` runs independently of the jupyter notebook. The jupyter notebook is for first-time users and used for illustrations sake.
* Note: The jupyter notebook had been developed in a python virtual environment created via the command `virtualenv .env`

#### Update on 02-Nov-2020
A few things to note in this Git Repo:
* `.mbutil` has been included so users may skip the step of downloading the library from https://github.com/mapbox/mbutil
	- The .bat file named: transform_to_mbtiles.bat can be run to package a folder of tile images and output a mbtiles file. Do change the parameters inside the .bat file.
* The folder [python_scripts](https://github.com/incubated-geek-cc/offline-mapping-server/tree/master/python_scripts) contains numbered .bat files which can be run directly in the order. For users who wish to execute a script instead of the jupyter notebook.