## Steps to run the docker container

- Pull the docker container from [here](https://ngc.nvidia.com/catalog/containers/nvidia:rapidsai:rapidsai). You might need to change the tags depending on your system requirements from [here](https://ngc.nvidia.com/catalog/containers/nvidia:rapidsai:rapidsai/tags)

    Example:

    `docker pull nvcr.io/nvidia/rapidsai/rapidsai:cuda10.2-runtime-ubuntu18.04`

- Let the docker build. it will take some time.
- Run the docker container using the following command:

    `docker run -v /home/srishtiy/dev/talks/scalable-hpo-pybay/papermill_demo:/rapids/notebooks/papermill_demo -it -p 8890:8890 -p 8787:8787 -p 8786:8786 \nvcr.io/nvidia/rapidsai/rapidsai:cuda10.2-runtime-ubuntu18.04`

    This will run the container at same time mouting the `papermill_demo` folder. Using mount command `-v` any changes made to the directory on the host will show up in the container.