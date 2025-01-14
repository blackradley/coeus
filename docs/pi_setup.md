
* Flash with the .img file from Ubuntu using BalenaEtcher.
* Stick the SD in the Raspberry Pi and connect with ethernet cable to the router.
* Plug in a monitor and keyboard
* sudo raspi-config
	- Setup the Wifi
	- Enable ssh
	- Change the hostname
	- Expand the file system (under Advanced options)
	- Reboot
* Find the Raspberry Pi on the router and ssh to it, (user=pi, password=raspberry).
* Install the prerequisites

```bash
$ sudo apt-get purge wolfram-engine
$ sudo apt-get purge libreoffice*
$ sudo apt-get clean
$ sudo apt-get autoremove
$ sudo apt-get update
$ sudo apt-get upgrade
$ sudo apt-get install build-essential cmake pkg-config
$ sudo apt-get install libjpeg-dev libtiff5-dev libjasper-dev libpng-dev
$ sudo apt-get install libavcodec-dev libavformat-dev libswscale-dev libv4l-dev
$ sudo apt-get install libxvidcore-dev libx264-dev
$ sudo apt-get install libfontconfig1-dev libcairo2-dev
$ sudo apt-get install libgdk-pixbuf2.0-dev libpango1.0-dev
$ sudo apt-get install libgtk2.0-dev libgtk-3-dev
$ sudo apt-get install libatlas-base-dev gfortran
$ sudo apt-get install libhdf5-dev libhdf5-serial-dev libhdf5-103
$ sudo apt-get install libqtgui4 libqtwebkit4 libqt4-test python3-pyqt5
$ sudo apt-get install python3-dev
```

* Setup the development environment

```bash
wget https://bootstrap.pypa.io/get-pip.py
sudo python get-pip.py
sudo python3 get-pip.py
sudo rm -rf ~/.cache/pip
sudo pip install virtualenv virtualenvwrapper
nano ~/.bashrc
```

Add this to the `.bashrc`

```.bashrc
# virtualenv and virtualenvwrapper
export WORKON_HOME=$HOME/.virtualenvs
export VIRTUALENVWRAPPER_PYTHON=/usr/bin/python3
source /usr/local/bin/virtualenvwrapper.sh
```

Reload the `.bashrc` with `source ~/.bashrc`.  Then create a virtual environment to work in `mkvirtualenv coeus -p python3`.  To leave use `deactivate` and to start use `workon coeus`. 