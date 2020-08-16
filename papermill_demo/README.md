# Steps to run the code in docker container

1. Pull the NGC RAPIDS docker container from [here](https://ngc.nvidia.com/catalog/containers/nvidia:rapidsai:rapidsai). You might need to choose the right tag depending on your system from [here](https://ngc.nvidia.com/catalog/containers/nvidia:rapidsai:rapidsai/tags).

    Example for Ubuntu 18.04:
    ```
    docker pull nvcr.io/nvidia/rapidsai/rapidsai:cuda10.2-runtime-ubuntu18.04
    ```

2. Run the docker container using the following command:
    ```
    docker run -v /path/to/papermill_demo:/rapids/notebooks/papermill_demo -it -p 8888:8888 -p 8787:8787 -p 8786:8786 \nvcr.io/nvidia/rapidsai/rapidsai:cuda10.2-runtime-ubuntu18.04
    ```

    This will run the container and mount the `papermill_demo` folder. Using mount argument `-v` any changes made to the directory on the host will show up in the container and vice versa.

3. You should see something like: `(rapids) root@e477c40c1229:/rapids/notebooks# `, where `e477c40c1229` is the container ID. You are now within the docker container. Change directory to `rapids/papermill_demo`.
    - Notice via `jupyter notebook list` that a Jupyter notebook instance is already running on port 8888. You may want to kill this instance for now using `pkill jupyter` since we need to install ipywidgets first.

4. Time to enable ipywidgets for progress bars:
    - If you are using Jupyter Noteboook: Run `jupyter nbextension enable --py widgetsnbextension`
    - If you are using Jupyter Lab: Run `jupyter labextension install @jupyter-widgets/jupyterlab-manager`

5. Run `jupyter lab . --ip=0.0.0.0 --port=8888 --no-browser --allow-root &` to launch Jupyter Lab instance in background.

6. You can see the Jupyter lab link on terminal. Click on the link to see the jupyter lab with the files.

7. Open and run `make_data.ipynb` to generate the data file `data.csv`.

8. Add parameters tag in `XGBoost_Demo.ipynb`.

9. Open and run `main.ipynb`. This file executes `XGBoost_Demo.ipynb`. 

    **Note** : For sequential processing of parameterized notebook, set `parallel = False`, for parallel processing of parameterized notebook, set `parallel = True`. Checkout the notebook for more details.

10. You can see the results in the output folder generated. If you are running in parallel, it might take some time depending on your system requirements. Use `htop` on your 'local host' to see the cpu usage.


Authors: Srishti Yadav [@copperwiring](https://github.com/copperwiring) and Akshit Arora [@aroraakshit](https://github.com/aroraakshit)

---

If you find any bug in the code, please raise an issue or send a PR are: https://github.com/copperwiring/scalable-hpo-pybay
