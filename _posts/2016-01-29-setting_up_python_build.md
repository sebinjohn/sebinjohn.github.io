## Python Build Setup

* Write setup.py, give as much details as you can

* By default README, README.rst and README.txt are automatically included, if you have a README.md it will not be included. So to add that, create a MANIFEST.in file and specify to include README.md.

  `include README.md`

* when running `python setup.py sdist` command you gotta be in that directory
  eg:

  ```
  ├── cm_config
  ├── setup.py
  └── tests
  ```
This helps to find out the packages automatically(provided you are using `find_packages` function from setuptools)

* create a __init__.py in all the packages. So that `find_packages` function can find it

* When you are deploying to pypi, all the underscores(-) in the name (given in the setup.py) should be changed to hiphens(-)

* The sample project in the github is a good starting place.


### Data files

* `python -c 'import sys; print sys.prefix` prints out the prefix path used by python.
* Prefix path is different for different OSes
* in setup.py we can specify the data files to be copied along with the installation using `data_files`  parameter
* the data files specified will be copied to the path specified in the `sys.prefix`
* eg: the default ansible library path is `/usr/share/ansible` in ubuntu and centos. where `/usr` is the `prefix`.
* the data file parameter can be specified like this `data_files=[(share/ansible/<libname>, '<files to be gone into the libname>')]`
