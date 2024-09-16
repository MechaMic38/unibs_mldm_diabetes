# Development - Contributing

If you already cloned the repository, here are some guidelines to setup your environment.

## Python Setup

You must install at least Python 3.12 on your local machine, you can do so by doing:

```shell
# Add Launchpad PPA to the repositories list
sudo add-apt-repository ppa:deadsnakes/ppa

# Update package list information
sudo apt update

# Install Python 3.12 (append -full to install all extras)
sudo apt install python3.12
```

## Virtual Environment Setup

Now that you have installed Python 3.12 on your local machine, it's time to setup the virtual environment.

To create the virtual environment, execute the following:

```shell
python -m venv .venv
```

Once it finishes, you should see the newly created `.venv` directory. You can activate the environment with:

```shell
source ./.venv/bin/activate
```

Finally, to install all the necessary Python libraries, execute the following:

```shell
pip install -r requirements.txt
```