<div style='display: inline-block'>
    <img src="assets/imgs/rapids_logo.png" height=100px>
    <img src="assets/imgs/sagemaker_logo.jpeg" height=100px>
</div>

# Scalable Hyper-parameter Optimization using RAPIDS and AWS

Presented at [PyBay](http://pybay.com/) 2020. Slides [here](https://docs.google.com/presentation/d/1N0vsV6vaA16jlpyZaV3yLSE1FZ02eGu3vPH5WBlE4I4/edit?usp=sharing). Recording (yet to be uploaded).

## Scaling HPO on CPUs
You can find the instructions [here](https://github.com/copperwiring/scalable-hpo-pybay/blob/master/papermill_demo/README.md). The demo covers:

* Single-node multi-CPU workflow.
* Setting up the docker container.
* Mounting the code from host system to docker container.
* Installing [Papermill](https://papermill.readthedocs.io/en/latest/) and related dependencies.
* Running the parameterized XGBoost demo notebook both sequentially and in parallel using MultiProcessing and Papermill.

## Scaling HPO on GPUs
You can find the instructions here: [rapidsai/cloud-ml-examples](https://github.com/rapidsai/cloud-ml-examples/). The notebook shown in the talk is [here](https://github.com/rapidsai/cloud-ml-examples/blob/master/aws/rapids_sagemaker_hpo.ipynb). The demo covers:

* Single CPU, Multi CPU, Single GPU, Multi GPU workflows
* Building the ML workflow using RAPIDS and Dask
* Building Estimator
* Running HPO on AWS SageMaker

## Suggested Reading
* [30x Faster Hyperparameter Search with Ray Tune and RAPIDS](https://medium.com/rapids-ai/30x-faster-hyperparameter-search-with-raytune-and-rapids-403013fbefc5) by Nanthini Balasubramanian.
* [Parallel Jupyter Notebooks](https://andrewm4894.com/2019/04/27/parallel-jupyter-notebooks/) by Andrew Maguire.
* [RAPIDS HPO](https://rapids.ai/hpo.html) getting started guide.
* [Accelerated Machine Learning with RAPIDS](https://github.com/aroraakshit/AcceleratedMLwRAPIDS) talk by Akshit Arora.

## Talk Abstract
> “Not sure if my novel ML model is giving the best accuracy it can!”

> “Can I find the best hyperparameters for my talk demo 4 days before the deadline?”

If this sounds like you, then you might want to attend this talk.

Distributed computing in machine learning is becoming the norm, and this trend is driven largely by the computational requirements of machine learning applications. However, building distributed applications today requires tons of expertise and finding optimal sets of hyper-parameters. It is often a time and resource-consuming process.

We want something that can search for hyper-parameters (hyper-parameter search optimization, aka HPO) in a distributed manner on-prem and on the cloud. We would expect the approach to intelligently optimize which of the possible combinations from the search space will give us the best results (example: best accuracy ). In this talk, we will be covering a technique that you can use with Jupyter Notebooks: an interactive python environment, parametrize using Papermill: a python library and distribute hyper-parameter search. Further in the talk we will explore how to scale up this search to cloud, specifically using AWS SageMaker orchestrator for HPO.

## About Speakers

### **Srishti Yadav**

Srishti is currently a graduate research assistant at Networked Robotics and Sensing Laboratory at Simon Fraser University, Canada. Her work revolves around the intersection of computer vision and machine learning where she actively use PyTorch, TensorFlow, Python, MATLAB, Numpy, Scipy, OpenCV, Matplotlib, GDAL, etc. scientific stack as well as cloud services like AWS. She is a founder of several developer community groups of Vancouver. In the past, she has given talks at Microsoft Open Source events, PyLadies and other machine learning groups. As a strong proponent of tech and diversity, her involvement goes beyond local community work. Recently she was one of the the chairs of Women in Computer Vision workshop co-hosted with CVPR, 2020 and was on the committee of the Women in Machine Learning workshop, 2019. 

<i>Website: [srishti.dev](https://srishti.dev/) / Email me: [srishtiyadav0807@gmail.com](mailto:srishtiyadav0807+pybay@gmail.com) / Follow me on Twitter: [@_srishtiyadav](https://twitter.com/_srishtiyadav) / GitHub: [@copperwiring](https://github.com/copperwiring)</i>

### **Akshit Arora**

Akshit is a deep learning solutions architect at NVIDIA focused on deploying machine learning and deep learning platforms at scale. As an architect, he helps accelerate deep learning pipelines using NVIDIA GPUs at various tech companies. Previously at CU Boulder, he developed deep learning models to understand how students learn on an online learning platform. His work also includes predicting weather using LSTMs and automatically completing a painting in virtual reality using sketch-RNN. He is interested in creative applications of machine learning/deep learning and the wide set of possibilities it presents. 

<i>Website: [aroraakshit.github.io](http://aroraakshit.github.io/) / Email me: [akshita@nvidia.com](mailto:akshita@nvidia.com) / Follow me on Twitter: [@_AkshitArora](https://twitter.com/_AkshitArora) / GitHub: [@aroraakshit](https://github.com/aroraakshit) </i>

---

If you find any bug in the code, please raise an issue [here](https://github.com/copperwiring/scalable-hpo-pybay/issues) or send a Pull Request [here](https://github.com/copperwiring/scalable-hpo-pybay/pulls).