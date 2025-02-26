# WAVE - Multiple load generator for computer network experimentation

[WAVE User Manual](Manual_do_Usuario_do_WAVE.pdf)

[Explanatory Video](https://www.youtube.com/watch?v=AOsvDJgxGQ8&ab_channel=JeffersonLucasFerreiradaSilva)

[Artigo Salão de Ferramentas SBRC 2023](https://doi.org/10.5753/sbrc_estendido.2023.712)

## Checking the Required Requirements

### Checking if Python3 is installed and it's version:

![wave-version-python3](https://user-images.githubusercontent.com/79940823/227387336-5cf0f04e-d74d-4107-b1c2-121accc85cf9.png)

### Additionally, the VirtualEnv virtual environment is required:

![wave-version-venv](https://user-images.githubusercontent.com/79940823/227387419-f8e7fa75-5c76-43f3-be66-4af4b83c5b2e.png)


### Checking the Docker and docker compose components:

![wave-version-docker](https://user-images.githubusercontent.com/79940823/227387459-b2ac5df2-aa2a-4a2e-9487-dac1e23f2dad.png)

![wave-version-docker-compose](https://user-images.githubusercontent.com/79940823/227387519-fb43dd4b-1826-4065-931e-4088bc64f132.png)

### Checking what version of Virtualbox is installed:

![wave-version-virtualbox](https://user-images.githubusercontent.com/79940823/227387550-05df777e-e121-4f49-b1ff-753dd32b4489.png)

### Checking what version of Vagrant is installed:

![wave-version-vagrant](https://user-images.githubusercontent.com/79940823/227387581-f5448336-2242-438f-b70c-8aa410fefca3.png)

The versions shown in the figures were those tested at the time of this manual's creation.

## Downloading the Code and Starting the Environment

### Cloning the official repository and starting the system:

```
$ git clone https://github.com/ifpb/new_wave.git
$ cd new_wave/wave
$ ./app-compose.sh --start
```

### Checking the execution in a Docker enviroment:

![wave-cli-docker](https://user-images.githubusercontent.com/79940823/227387624-3d84cb78-2fe4-4b6d-8c37-09f71cf9eb9d.png)

As can be seen in the figure above, the WAVE Initialization module uses two containers for its execution: wave-app and grafana-oss. On the left side of the figure, we have the output of the WAVE startup command.

### The WAVE Web module can be accessed via a browser

![wave-web-home](https://user-images.githubusercontent.com/79940823/227392316-1a45422c-8d38-4562-9094-6a39302bae98.png)

The form contains fields for entering network data for both the traffic load source and destination. In addition to the IP address, it is possible to select environment provisioning through a container or a virtual machine with configurable memory size and number of virtual CPUs. Finally, the user can choose which workload model to apply, either sinusoid, flashcrowd or step and if they want to use micro-burst as well.

## Ending the WAVE Execution

### Finalizing and removing the container environment:

```
$ ./app-compose.sh --destroy
```

By running the command above, the user terminates the WAVE WEB module and removes the containers responsible for the other initiated modules. To restart the entire system, simply execute the same command, replacing the --destroy argument with --start.