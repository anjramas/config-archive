## Getting started

These instructions will get you a copy of the Python code for a Python script to find the difference between running config and startup config of a device a DNAC controller knows about.

## Requirements

- Python 3.6 or higher
- "git" command line tools
- Homebrew (Mac OS X)

## For Mac OS X Installation

```
git installation - https://git-scm.com/download/mac
```
```
homebrew installation - ruby -e "$(curl -fsSL https://raw.github.com/mxcl/homebrew/go)"
```
```
Python 3.6 installation - https://www.python.org/downloads/release/python-364/
Python pip installation
curl -o get-pip.py https://bootstrap.pypa.io/get-pip.py
sudo python get-pip.py
```
Command Line Developer Tools Installation. After running command, complete installation using the GUI.
```          
xcode-select --install
```

## For Windows Installation
```
git installation - https://git-scm.com/download/win
Python 3.6 installation - https://www.python.org/downloads/release/python-364/
Be sure to check box for "Add Python to PATH" during the installer
```

## 'GIT' this code

All of the code and examples for this lesson is located in the 'add me here' directory. Clone and access it with the following commands:

```
git clone https://github.com/anjramas/config-archive
cd config-archive
```
Use pip to install the necessary requirements
```
pip install -r requirements.txt
```

### Code features

The Python script uses the DNAC APIs to get the difference between the running configuration and startup configuration of a device a DNAC Controller knows about. The APIs provides the details of the timestamp when the last startup and running configuration change was done and by whom. It also provides the difference between the running config and startup config for the given device.

## Running the code

In dnac_config.py, set your DNAC environment details

DNAC=os.environ.get('DNAC','<DNAC_Cluster_IP>')
DNAC_PORT=os.environ.get('DNAC_PORT',443)
DNAC_USER=os.environ.get('DNAC_USER','<DNAC_Username>')
DNAC_PASSWORD=os.environ.get('DNAC_PASSWORD','<DNAC_Password>')

Once configured use the following command to run the code
```
python get_running_startup_config_diff.py <device_ip>
```

## Sample Output

```>python get_running_startup_config_diff.py 10.10.20.80
Device IP Address 10.10.20.80

 Running Configuration Change time and user details
------------------------------------------------------
 Last configuration change at 21:51:21 UTC Wed Dec 18 2019 by admin

 Startup Configuration Change time and user details
------------------------------------------------------
 Last configuration change at 02:59:05 UTC Mon Dec 16 2019 by admin

  Difference between Running and startup config for the device 10.10.20.80

---------------------------------------------------------------------------------------------------
certificate xxxxxxxxx

certificate xxxxxxxxx

certificate xxxxxxxxx

certificate xxxxxxxxx

certificate xxxxxxxxx

certificate xxxxxxxxx

certificate xxxxxxxxx

certificate xxxxxxxxx

certificate xxxxxxxxx

certificate xxxxxxxxx

  -D697DF7F 28

certificate xxxxxxxxx

certificate xxxxxxxxx

certificate xxxxxxxxx

certificate xxxxxxxxx

  -F33BED83 E64DF76A 5C5C33AF 88DE590E 250F
```
