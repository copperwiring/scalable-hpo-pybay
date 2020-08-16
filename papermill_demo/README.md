### Steps to run the code in docker container

1. Pull the docker container from [here](https://ngc.nvidia.com/catalog/containers/nvidia:rapidsai:rapidsai). You might need to change the tags depending on your system requirements from [here](https://ngc.nvidia.com/catalog/containers/nvidia:rapidsai:rapidsai/tags)

    Example:

    `docker pull nvcr.io/nvidia/rapidsai/rapidsai:cuda10.2-runtime-ubuntu18.04`

2. Run the docker container using the following command (change the location of the folder where uour notebook lies. Mine was in `/home/srishtiy/dev/talks/scalable-hpo-pybay/papermill_demo` :

    `docker run -v /home/srishtiy/dev/talks/scalable-hpo-pybay/papermill_demo>:/rapids/notebooks/papermill_demo -it -p 8890:8890 -p 8787:8787 -p 8786:8786 \nvcr.io/nvidia/rapidsai/rapidsai:cuda10.2-runtime-ubuntu18.04`

    This will run the container at same time mouting the `papermill_demo` folder. Using mount command `-v` any changes made to the directory on the host will show up in the container.

3. You should see something like: `(rapids) root@e477c40c1229:/rapids/notebooks# `. You are now within the docker container.

4. In this docker container, run `jupyter nbextension enable --py widgetsnbextension`

5. In this docker container, run `jupyter labextension install @jupyter-widgets/jupyterlab-manager`

    Run `jupyter lab . --ip=0.0.0.0 --port=8890 --no-browser --allow-root &`
6. You can see the jupyler lab link on terminal. Click on the link to see the jupyter lab with the files.
7. `cd` to `papermill_demo` directory.
8. Open and run `make_data.ipynb` to get the data file.
9. Open and run `main.ipynb`. This file parameterizes and executes `XGBoost_Demo.ipynb`. 

    **Note** : For sequential processing of parameterized notebook, set `parallel = False`, for parallel processing of parameterized notebook, set `parallel = True`. Checkout the notebook for more details.

10. You can seethe results in the output folder generated. If you are running in parallely, it might take some time deending on your system requirements. Use `htop` on your 'local host' to see the cpu usage.


---
### Authors: 
* Srishti Yadav [@copperwiring](https://github.com/copperwiring)
* Akshit Arora [@aroraakshit](https://github.com/aroraakshit)

---

If you find any bug in the code, please raise an issue or send a PR are: https://github.com/copperwiring/scalable-hpo-pybay
