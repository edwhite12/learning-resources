# Learning resources for Eric White in the CUAHSI Virtual University Digital Water course - Fall 2020
## Notebook 1: [Nooksack Watershed Lapse Rates 2016](https://www.hydroshare.org/resource/222e832d3df24dea9bae9bbeb6f4219d/)
- [Bandaragoda et al., 2020](https://doi.org/10.1016/j.dib.2020.105578)
- the file paths did not match the default folder structure that was generated when I opened this notebook in jupyterhub
- the numpy text encoder was not able to decode the datetime strings in the 2016 lapse dataset - there was a Unicode Decode Error thrown![image](https://github.com/edwhite12/learning-resources/blob/master/Nooksack_error.PNG)
- this error could be an issue with the python kernel I was using. I used the whw kernel - and the error message looks like it may not have the required codecs for installed

- I used this whw kernel, however, it still looks like the kernels do not have the necessary dependencies

 ## Notebook 2: [RAPID National Water Model Github repository](https://github.com/rapid-research/tutorial_rapid-nationalwatermodel)
- do not trust pre-defined kernels in jupyterhub
  - in juypterhub, it is unclear as to what exactly is included in each kernel
  - trying several different kernels resulted in many import errors
    - even for seemingly standard Python libraries such as matplotlib
- in the console, using pip, I installed both nwm and matplotlib
- in the notebook, I changed the kernel by selecting the kernel set up in the console. This was *not* the same kernel as whw - and allowed me to have some control over the Python library dependencies
- file path structure to the yaml config file seemed to change from time to time when I closed and reopened jupyterhub. It seems like the default working directory changes and was able to be controlled for by either os.chdir() or by changing the directory path for the config file
- when logging back into jupyterhub (or jupyterlab), I am able to see my notebook - but I am unclear on how to publish it as a 'resource' in Hydroshare so that it is active and can be run. I was able to download a copy, and then upload it to a Hydroshare resource. However, even when opened in Hydroshare's jupyterhub, the notebook does not appear to maintain connectivity to the datasets and modules previously linked in my personal juptyerhub that was used to build the notebook.


## Proposed workflow for my dissertation research:
- one of my test cases will be to use forecasted runoff hydrographs from the NWM and then route the hydrograph using kinematic, diffusive, and dynamic wave algorithms.
- I will compare the resulting floodwaves from each method and determine how different each forecasted wave is from one another
- these comparisons will be made across:
    - space (e.g., different basins)
    - events (e.g., different forecasted events)
    - time (e.g., different range forecasts)
- I will utilize the nwm python library to access NWM forecast archives.
- I will use the sample code provided in the NWM Harvey jupyter notebook as a go-by
- I will develop several lists that will contain iterators
    - forecast = ['short','medium','long']
    - basin = ['123456','654321','135790']
- Iterating over these lists with NwmHs.get_data, I can prepare the runoff hydrographs that I need as an upstream boundary condition in my model runs.
- I will need to sort out the dates, as well as sort out the archives that are available. I will need to dig through the Github documentation and other documents in Hydroshare to find the information that I need.

## Additional links from lecture:
https://www.hydroshare.org/resource/01fb1caf21fc45fb9ac1257bb276bc7a/
