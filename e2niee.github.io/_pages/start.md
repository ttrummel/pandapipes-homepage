---
layout: single
title: Getting Started
permalink: /start/
author_profile: false
toc: true
toc_sticky: true
toc_label: <a href="#site-nav">Getting Started</a>
classes:
   - wide
---

***NOTE: Tab-Icon ist noch von pandapower.***

## Installing pandapower

For the installation of pandapipes it is necessary to install pandapower first. For the installation please follow the detailed instructions which can be found on the [pandapower website](http://www.pandapower.org/start/). 



<h2 id="install">Installing pandapipes</h2>
***NOTE: Nur pandapower zu pandapipes geändert.***
        
<h3 id="pip">Through pip</h3>

The easiest way to install pandapipes is through pip:

1. Open a command prompt (e.g. start-->cmd on windows systems)

2. Install pandapipes by running:

        pip install pandapipes

<h3 id="nopip">Without pip</h3>

If you don't have internet access on your system or don't want to use pip for some other reason, pandapipes can also be installed without using pip:

1.  Download and unzip the current pandapipes distribution from [PyPi](https://pypi.org/project/pandapower/) under "Download files".
2.  Open a command prompt (e.g. Start\--\>cmd on Windows) and navigate to the folder that contains the setup.py file with the command cd
    \<folder\> :

        cd %path_to_pandapower%\pandapower-x.x.x\

3.  Install pandapipes by running :

        python setup.py install

<h3 id="develop">Development Version</h3>

To install the latest development version of pandapipes from [github](https://github.com/e2nIEE/pandapower), simply follow these steps:

1. Download and install [git](https://git-scm.com). 

2. Open a git shell and navigate to the directory where you want to keep your pandapipes files.

3. Run the following git command:

        git clone https://github.com/e2nIEE/pandapower.git

4. Navigate inside the repository and check out the develop branch:

        cd pandapipes
        git checkout develop
       
5. Open a command prompt (cmd or anaconda command prompt) and navigate to the folder where the pandapipes files are located. Run:

        pip install -e .
        
   This registers your local pandapipes installation with pip.
        
## Test your installation <a name="test"></a>

A first basic way to test your installation is to import all pandapower submodules to see if all dependencies are available:

    import pandapower
    import pandapower.networks
    import pandapower.topology
    import pandapower.plotting
    import pandapower.converter
    import pandapower.estimation

If you want to be really sure that everything works fine, run the pandapower test suite:

1.  Install pytest if it is not yet installed on your system:

        pip install pytest

2. Run the pandapower test suite:

        import pandapower.test
        pandapower.test.run_all_tests()

If everything is installed correctly, all tests should pass or xfail (expected to fail).


## A short introduction <a name="intro"></a>

A network in pandapipes is represented in a pandapipesNet object, which
is a collection of pandas Dataframes. Each dataframe in a pandapipesNet
contains the information about one pandapipes element, such as pipe,
junction, sink, etc.

We consider the following simple example network as a minimal
example:

![](/images/getting_started/simple_network.png)


### Creating a network

The above network can be created in pandapipes as follows:

    import pandapipes as pp
    #create empty net
    net = pp.create_empty_network() 

    #create junctions
    j1 = pp.create_junction(net, pn_bar=5, name="Junction 1")
    j2 = pp.create_junction(net, pn_bar=5, name="Junction 2")
    j3 = pp.create_junction(net, pn_bar=5, name="Junction 3")

    #create junction elements
    pp.create_ext_grid(net, junction=j1, p_bar=5, name="Grid Connection")
    pp.create_sink(net, junction=j3, mdot_kgps=50, name="Sink")

    #create branch elements
    pp.create_pipe(net, from_junction=j1, to_junction=j2, length_km=0.1, diameter_m=0.05, name="Pipe")
    pp.create_valve_pipe(net, from_junction=j2, to_junction=j3, length_km=2, diameter_m=0.05)   



The pandapipes representation now looks like this:

![image](/images/getting_started/pandapipes_results1.png)






![image](/images/getting_started/pandapipes_results2.png)


### Running a Power Flow

A powerflow can be carried out with the [runpp function][]: 

    pp.runpp(net)

When a power flow is run, pandapower combines the information of all
element tables into one pypower case file and uses pypower to run the
power flow. The results are then processed and written back into
pandapower:

![image](http://pandapower.readthedocs.io/en/latest/_images/pandapower_powerflow.png)

For the 3-bus example network, the result tables look like this:

![image](/images/getting_started/pandapower_results.png)

All other pandapower elements and network analysis functionality (e.g.
optimal power flow, state estimation or short-circuit calculation) is
also fully integrated into the tabular pandapower datastructure.

This minimal example is also available as a [jupyter notebook].

  [transformer model]: http://pandapower.readthedocs.io/en/latest/elements/trafo.html#electric-model
  [standard type library]: http://pandapower.readthedocs.io/en/latest/std_types.html
  [runpp function]: http://pandapower.readthedocs.io/en/latest/powerflow/ac.html
  [jupyter notebook]: https://github.com/e2nIEE/pandapower/blob/develop/tutorials/minimal_example.ipynb


  
## Interactive Tutorials <a name="tutorials"></a>

There are jupyter notebook tutorials on different functionalities of pandapower:

Basic introduction:

   -   [Minimal example](https://github.com/panda-power/pandapower/blob/master/tutorials/minimal_example.ipynb)
   -   [Creating a simple network](https://github.com/panda-power/pandapower/blob/master/tutorials/create_simple.ipynb)
   -   [Running a power flow](https://github.com/panda-power/pandapower/blob/master/tutorials/powerflow.ipynb)
   -   [Creating an advanced network](https://github.com/panda-power/pandapower/blob/master/tutorials/create_advanced.ipynb)
   -   [Working with the pandapower standard type library](https://github.com/panda-power/pandapower/blob/master/tutorials/std_types.ipynb)
   -   [Application example: calculate hosting capacity with pandapower](https://github.com/e2nIEE/pandapower/blob/develop/tutorials/hosting_capacity.ipynb)

Data analysis and modelling error diagnostic:

   -   [Analysing data in pandapower tables](https://github.com/panda-power/pandapower/blob/master/tutorials/data_analysis.ipynb)
   -   [Diagnosing inconsistent or incorrect data](https://github.com/panda-power/pandapower/blob/master/tutorials/diagnostic.ipynb)
   -   [About the internal data structure of pandapower](https://github.com/panda-power/pandapower/blob/master/tutorials/internal_datastructure.ipynb)

Optimal power flow:

   -   [Configuring and running an optimal power flow](https://github.com/panda-power/pandapower/blob/master/tutorials/opf_basic.ipynb)
   -   [Calculate power curtailment with an OPF](https://github.com/panda-power/pandapower/blob/master/tutorials/opf_curtail.ipynb)
   -   [Calculate DC line dispatch with an OPF](https://github.com/panda-power/pandapower/blob/master/tutorials/opf_dcline.ipynb)
   -   [Using PowerModels.jl to carry out an OPF](https://github.com/panda-power/pandapower/blob/master/tutorials/opf_powermodels.ipynb)
   -   [Using PowerModels.jl TNEP (transmission network expansion planning) interface](https://github.com/e2nIEE/pandapower/blob/develop/tutorials/tnep_powermodels.ipynb)
   -   [Using PowerModels.jl OTS (optimal transmission switching) interface](https://github.com/e2nIEE/pandapower/blob/develop/tutorials/ost_powermodels.ipynb)
   -   [Using PowerModels.jl storage interface](https://github.com/e2nIEE/pandapower/blob/develop/tutorials/storage_powermodels.ipynb)
    
State estimation:

   -   [Configure and run a state estimation](https://github.com/panda-power/pandapower/blob/master/tutorials/state_estimation.ipynb)

Short-circuits:

   -   [Run a short-circuit calculation according to IEC 60909](https://github.com/e2nIEE/pandapower/blob/develop/tutorials/shortcircuit.ipynb)
   -   [Short-circuit calculations considering renewable energy (2016 revision)](https://github.com/e2nIEE/pandapower/blob/develop/tutorials/shortcircuit_renewables.ipynb)

Topology package:

   -   [Running topological graph searches](https://github.com/panda-power/pandapower/blob/master/tutorials/topology.ipynb)

Plotting pandapower networks (static with matplotlib):

   -   [Plotting grographic network plans](https://github.com/panda-power/pandapower/blob/master/tutorials/plotting_basic.ipynb)
   -   [Plotting network plans with colormaps](https://github.com/panda-power/pandapower/blob/master/tutorials/plotting_colormaps.ipynb)
   -   [Plotting structural plans without geographical data](https://github.com/panda-power/pandapower/blob/master/tutorials/plotting_structural.ipynb)
   -   [Embedding matplotlib colormaps in PyQt](https://github.com/panda-power/pandapower/blob/master/tutorials/plotting_pyqt.ipynb)


Plotting pandapower networks (interactive with plotly)

   -   [Creating interactive plots with plotly](http://nbviewer.jupyter.org/github/e2nIEE/pandapower/blob/develop/tutorials/plotly_built-in.ipynb)
   -   [Customize plotly plots](http://nbviewer.jupyter.org/github/e2nIEE/pandapower/blob/develop/tutorials/plotly_traces.ipynb)
   -   [Include interactive maps as background](http://nbviewer.jupyter.org/github/e2nIEE/pandapower/blob/develop/tutorials/plotly_maps.ipynb)

Time series calculation with the pandapower control module

   -   [Basic time series calculation](https://github.com/e2nIEE/pandapower/blob/develop/tutorials/time_series.ipynb)
   -   [Advanced time series calculation](https://github.com/e2nIEE/pandapower/blob/develop/tutorials/time_series_advanced_output.ipynb)
   
## YouTube Tutorials <a name="youtube_tutorials"></a>

You can also find some tutorials about the basics of pandapower on YouTube:

[pandapower on YouTube](https://www.youtube.com/channel/UC0iZbJpDu5--fa8A2GWCa0Q?view_as=subscriber)