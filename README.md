# Hopium-pylibcamera
This package is for the libcamera python bindings only. It requires you to already have installed a version of libcamera onto your system.

## Caveats
***For most users this package is not the best approach to use libcamera in python - there are simpler ways***

**If you are able to use the system python**, then running `sudo apt install -y python3-libcamera` will install the libcamera python bindings in the simplest way.

**If you do require a virtual environment** (for example, in order to use a python package not available through apt) then the simplest way is to install the apt package and then create a virtual environment using system-site-packages.
```
sudo apt install -y python3-libcamera
python3 -m venv --system-site-packages my-env
```
This will allow you to use pip to install other packages in the virtual environment, while using the system versions of packages such as libcamera and PyQt5, which is a much simpler approach than pip installing these packages. Usually. This is the part where I intervene and say that tools like poetry and pipx, wherein isolating literally everything from the system python, is the whole point, and they definitely do need something more interesting. 

This package has been modified such that it will always build targeting the main branch of https://github.com/raspberrypi/libcamera, thereby ensuring that a static version of this software (hopium-libcamera @ git+https://github.com/yeetmanthecoolman/pylibcamera.git) can bind to a static version of the libcamera (namely, the main branch). These can never really be static, obviously, but it's close enough to fool poetry and kick the can down the road.
