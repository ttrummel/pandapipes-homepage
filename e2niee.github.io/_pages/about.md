---
layout: single
permalink: /about/
title: About pandapipes
author_profile: false
toc: true
toc_sticky: true
toc_label: <a href="#site-nav">About pandapipes</a>
classes:
  - wide   
gallery:
  - url:        /images/about/validation/cross.png
    image_path: /images/about/validation/cross.png
    title:      "cross"
  - url:        /images/about/validation/delta.png
    image_path: /images/about/validation/delta.png
    title:      "delta"
  - url:        /images/about/validation/district.png
    image_path: /images/about/validation/district.png
    title:      "district"
  - url:        /images/about/validation/H-net.png
    image_path: /images/about/validation/H-net.png
    title:      "H-net"
  - url:        /images/about/validation/one_pipe.png
    image_path: /images/about/validation/one_pipe.png
    title:      "one_pipe"
  - url:        /images/about/validation/parallel.png
    image_path: /images/about/validation/parallel.png
    title:      "parallel"
  - url:        /images/about/validation/pumps.png
    image_path: /images/about/validation/pumps.png
    title:      "pumps"
  - url:        /images/about/validation/square.png
    image_path: /images/about/validation/square.png
    title:      "square"
  - url:        /images/about/validation/strand_net.png
    image_path: /images/about/validation/strand_net.png
    title:      "strand_net"
  - url:        /images/about/validation/strand_net_stanet.png
    image_path: /images/about/validation/strand_net_stanet.png
    title:      "strand_net_stanet"
  - url:        /images/about/validation/t-cross_1.png
    image_path: /images/about/validation/t-cross_1.png
    title:      "t-cross_1"
  - url:        /images/about/validation/t-cross_2.png
    image_path: /images/about/validation/t-cross_2.png
    title:      "t-cross_2"
  - url:        /images/about/validation/two_pipes.png
    image_path: /images/about/validation/two_pipes.png
    title:      "two_pipes"
  - url:        /images/about/validation/two_pipes_two_ext_grid.png
    image_path: /images/about/validation/two_pipes_two_ext_grid.png
    title:      "two_pipes_two_ext_grid"
  - url:        /images/about/validation/two_valves.png
    image_path: /images/about/validation/two_valves.png
    title:      "two_valves"
  - url:        /images/about/validation/versatility_1.png
    image_path: /images/about/validation/versatility_1.png
    title:      "versatility_1"
  - url:        /images/about/validation/versatility_2.png
    image_path: /images/about/validation/versatility_2.png
    title:      "versatility_2"
---

pandapipes is an easy to use network calculation program aimed at automation of analysis of district heating
and gas systems. It utilizes the data analysis library pandas and is also closely related to
the power systems calculation program pandapower.

pandapipes and pandapower can be used in combination to analyze multi energy networks. An environment able to couple both
tools is pandapowerpro.

## Why another tool?

**Motivation**<br>

pandapower was developed to close the gap between commercial and open source power systems analysis tools.
While open source power systems tools are flexible and can easily be customized, they often lack the detailed model libraries and
comfortable usage of commercial power system analysis tools.

|                                                      | Electric Models                                                                                                                                | Automation                                                                                                               | Customization                                                                                           |
|------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| Commercial Tools (e.g. Sincal, PowerFactory, NEPLAN) | <span style="color:green">Thoroughly validated and easy to parametrize electric models of lines, transformers, switches etc.</span>            | <span style="color:red">Graphical User Interface applications that are difficult to automate.</span>                     | <span style="color:red">Restricted possibilities for customization due to proprietary code base.</span> |
| Open Source Tools (e.g. MATPOWER, PYPOWER)           | <span style="color:red">Basic models that require parametrization by the user with expert knowledge.</span>                                    | <span style="color:green">Console application that are designed for automated evaluations.</span>                        | <span style="color:green">Open Source code base that can be freely modified and customized.</span>      |
| **pandapower**                                       | <span style="color:green">**Thoroughly validated and easy to parametrize electric models of lines, transformers, switches etc.**</span>        | <span style="color:green">**Console application that is designed for automated evaluations.**</span>                     | <span style="color:green">**Open source code base that can be freely modified and customized.**</span>  |

This is of course a very broad classification of tools that is only supposed to illustrate the focus of pandapower without
considering the diverse landscape of existing tools. A more detailed analysis of existing open source tools and 
the gap that pandapower closes can be found in <a href="https://doi.org/10.1109/TPWRS.2018.2829021" title="L. Thurner, A. Scheidler, F. Schäfer et al, pandapower - an Open Source Python Tool for Convenient Modeling, Analysis and Optimization of Electric Power Systems, IEEE Transactions on Power Systems, 2018.">[1]</a>.
Overviews over existing open source tools can also be found in <a href="https://doi.org/10.1016/j.esr.2017.12.002" title="S. Pfenninger, L. Hirth, I. Schlecht et. al - Opening the black box of energy modelling: Strategies and lessons learned, Energy Strategy Reviews, Volume 19, Pages 63-71, 2018">[2]</a>
 or <a href="https://doi.org/10.1109/PES.2009.5275920" title="F. Milano, L. Vanfretti - State of the Art and Future of OSS for Power Systems, 2009 IEEE Power & Energy Society General Meeting, Calgary, AB, 2009">[3]</a>
.

**Scope**<br>

pandapower is aimed at **static** analysis of **balanced** power systems. This allows analysis of:
- **transmission** and **subtransmission systems**, which are typically operated symmetrically.
- **symmetric distribution systems**, which are commonly found in Europe.

Distribution grids with unbalanced power flows, such as the feeder design common in North America, can currently not be
analysed with pandapower.


<h2 id="modeling">Power System Modeling</h2>

<h3 id="circuits">Equivalent Circuit Models</h3>
pandapower is an element based network calculation tool that supports a wide variety of electric components. 
The following table shows that the pandapower model library goes beyond of that of most existing open source tools:

<img src="{{"/images/about/open_source_models.png" | relative_url }}" alt=""/>
<figcaption>Comparison of open source electric model libraries <a href="https://doi.org/10.1109/TPWRS.2018.2829021" title="L. Thurner, A. Scheidler, F. Schäfer et al, pandapower - an Open Source Python Tool for Convenient Modeling, Analysis and Optimization of Electric Power Systems, IEEE Transactions on Power Systems, 2018.">[1]</a></figcaption>

All equivalent circuit models are [thoroughly validated](#tests) against commercial software tools and therefore allow industry level modeling of electric power systems.

<h3 id="datastructure">Tabular Data Structure</h3>

pandapower is based on a tabular data structure, where every element type is represented by a table that holds all parameters for a specific
element and a result table which contains the element specific results of the different analysis methods. The tabular data structure is
based on the Python library pandas. It allows storing variables of any data type, so that electrical parameters can be stored
together with status variables and meta-data, such as names or descriptions. The tables can be easily expanded and customized by adding new
columns without influencing the pandapower functionality. All inherent pandas methods can be used to efficiently read, write and
analyze the network and results data.

<h3 id="std_types">Standard Type Libraries</h3>

pandapower includes a standard type library that allows the creation of lines and transformers using predefined basic standard type parameters. The user can either define individual standard types or use the predefined pandapower basic standard types for convenient definition of networks.

   
<h2 id="analysis">Power System Analysis</h2>

pandapower supports the following power systems analysis functions:

- [Power Flow](#pf)
- [Optimal Power Flow](#opf)
- [State Estimation](#se)
- [Short-Circuit Calculation](#sc)
- [Topological Graph Searches](#topology)

<h3 id="pf">Power Flow</h3>

The pandapower power flow solver is based on the Newton-Raphson method.
The implementation was originally based on PYPOWER, but has been improved with respect to
robustness, runtime and usability.
<br><small>[Learn more](http://pandapower.readthedocs.io/en/stable/powerflow/ac.html)</small>

<font size="4"><b>Initialization</b></font>

pandapower offers three different methods to initialize the complex voltage
vector for the AC power flow calculation:
   - flat start
   - voltage vector of a previous calculation
   - initialization with a DC power flow
   
<font size="4"><b>Performance</b></font>

Some parts of the pandapower solver have been accelerated using the
JIT compiler [numba](https://numba.pydata.org/). This makes the pandapower Newton-Raphson significantly faster
than the PYPOWER solver from which it was originally derived.
To outline the difference in computational time, the convergence times for different standard MATPOWER
case files are shown here for MATPOWER, PYPOWER and pandapower:

<img src="{{"/images/about/speed_comparison.png" | relative_url }}" alt=""/>
<figcaption>Power flow speed convergence time comparison of different open source tools <a href="https://doi.org/10.1109/TPWRS.2018.2829021" title="L. Thurner, A. Scheidler, F. Schäfer et al, pandapower - an Open Source Python Tool for Convenient Modeling, Analysis and Optimization of Electric Power Systems, IEEE Transactions on Power Systems, 2018.">[1]</a></figcaption>

While PYPOWER and MATPOWER operate directly on the bus-branch model of the grid, the element based power system model in pandapower
requires mappings and conversions of grid data and results into the tabular data structure. The graph shows that this
conversion can take a significant amount of time in smaller networks, but its share decreases in larger networks. Even with 
the conversion overhead, pandapower is the fastest of the three tools in large grids with >1000 nodes.

<font size="4"><b>Other solvers</b></font>

In addition to the default Newton-Raphson solver, pandapower also
provides an implementation of a backward/forward sweep. pandapower also includes an Iwamoto variant of the Newton-Raphson,
which includes a damping factor that can help convergence in ill-conditioned problems. It is also possible to use the fast
decoupled as well as the Gauss-Seidel power flow algorithms through an interface to PYPOWER, although some features, such as ZIP loads
or unsymmetrical impedances will only work with the pandapower solvers.

<font size="4"><b>Unbalanced Power Flow</b></font>

An unbalanced power flow is currently being implemented and a first version will hopefully be released soon. Follow the progress
or join the implementation efforts on [github](https://github.com/e2nIEE/pandapower/issues/96), or subscribe to the [pandapower
mailing list](contact.md) for updates.

<h3 id="opf">Optimal Power Flow<br> </h3>
pandapower allows solving AC and DC optimal power flow (OPF) problems through interfacing
PYPOWER or [PowerModels.jl](https://github.com/lanl-ansi/PowerModels.jl). Costs, flexibilities and constraints are configured through
the element-based pandapower data structure and internally converted to a PYPOWER or PowerModels data structure where the optimization
is carried out. Static loads can be used as flexibilities in the OPF, which allows optimization dispatch of static generators as well 
as load shedding. The cost function for each power injection or load can either be defined by a piecewise linear or a n-polynomial
cost function of the active and reactive power output of the respective elements.
<br><small>[Learn more](http://pandapower.readthedocs.io/en/stable/powerflow/opf.html)</small>

<h3 id="se">State Estimation<br></h3>
pandapower includes a state estimation module that allows to estimate the electrical state of a network by dealing with inaccuracies
and errors from measurement data. pandapower supports measurement of voltages, active and reactive power or currents at bus, lines and
transformers. The state estimation is solved with a weighted-least-square method. It also includes a bad-data detection method based
on a Chi-squared and a normalized residuals test.
<br><small>[Learn more](http://pandapower.readthedocs.io/en/stable/estimation.html)</small>

<h3 id="sc">Short-Circuit Calculation<br></h3>
pandapower includes a short-circuit calculation that allows to calculate fault currents for three-phase, two-phase and single phase 
short-circuits according to the IEC 60909 standard. The implementation also allows modeling power converter elements, such as 
PV plants or wind parks, according to the 2016 revision of the standard.
<br><small>[Learn more](http://pandapower.readthedocs.io/en/stable/shortcircuit.html)</small>

<h3 id="topology">Graph Searches<br></h3>
pandapower provides the possibility of graph searches using the Python library [NetworkX](https://networkx.github.io/) by providing a
possibility to translate pandapower networks into NetworkX graphs.
Once a network is translated into an abstract graph, all graph searches implemented in the NetworkX library can be used to analyze
the network structure. Additionally, pandapower also provides some predefined search algorithms to tackle common graph search problems
in electric networks, such as finding unsupplied buses or identifying buses on main or 
secondary network feeders.
<br><small>[Learn more](http://pandapower.readthedocs.io/en/stable/topology.html)</small>

<h2 id="tests">Tests and Validation</h2>

<font size="5"><b>STANET Tests</b></font>
<br>
So far pandapipes has been successfully tested 66 times with [pytest](https://docs.pytest.org/en/latest/).
Several factors within the test networks were varied:

 <ul>
 <small>
  <li>medium: gas and water</li>
  <li>topology</li>
  <li>pressure at external grids</li>
  <li>number of external grids</li>
  <li>friction model</li>
  <li>length, diameter and roughness of a pipe</li>
  <li>volume flow</li>
  <li>number and height values of nodes</li>
  <li>direction of pipe link between nodes, for checking the correct flow velocity calculation</li>
  <li>combinations of sources, sinks, pumps, valves and external grids</li>
  </small>
 </ul>
<br>
The test nets were created with STANET and saved in CSV format so that a conversion
into a json file can take place to perform the tests in [PyCharm](https://www.jetbrains.com/pycharm/).
The structures of all test networks are listed below:

{% include gallery caption="The pandapipes test networks." %}

<img src="{{"/images/about/validation/legend.png" | relative_url }}" alt=""/>
<figcaption>Legend of the network components.</figcaption>
<br>
The relative error <math><mi>p<sub>diff</sub></mi></math> during the calculation of the pressures always has a value less than 0.01.

<math>
    <mrow>
        <mi>p<sub>diff</sub></mi>
        <mo>=</mo>
        <mo>|</mo>
            <mo>(</mo>
                <mi>p<sub>stanet</sub></mi>
                <mo>-</mo>
                <mi>p<sub>pandapipes</sub></mi>
            <mo>)</mo>
            <mo>/</mo>
            <mi>p<sub>stanet</sub></mi>
        <mo>|</mo>
    </mrow>
</math>

<br>
Furthermore, the absolute error in the calculation of the flow velocities <math><mi>v<sub>diff,abs</sub></mi></math> is always less than 0.05.

<math>
    <mrow>
        <mi>v<sub>diff,abs</sub></mi>
        <mo>=</mo>
        <mo>|</mo>
        <mi>v<sub>stanet</sub></mi>
        <mo>-</mo>
        <mi>v<sub>pandapipes</sub></mi>
        <mo>|</mo>
    </mrow>
</math>

<!--
| **Parameter**     | **Max. Deviation**  | 
|-------------------|---------------------| 
| Voltage Magnitude | 0.000001 pu         | 
| Voltage Angle     | 0.01°               | 
| Current           | 0.000001 kA         | 
| Power             | 0.005 kW            | 
| Element Loading   | 0.001%              | 
-->



<h2 id="citing">Citing pandpipes</h2>

If you use pandapipes in your work, we kindly ask you to cite the [pandapipes reference paper](/references/#citing)


<h2 id="license">License</h2>

pandapipes is published under the following 3-clause BSD license: 

> Copyright (c) 2018 by University of Kassel and Fraunhofer Institute for Fraunhofer Institute for 
    Energy Economics and Energy System Technology (IEE) Kassel and individual contributors
   (see AUTHORS file for details). All rights reserved.
>   Redistribution and use in source and binary forms, with or without modification, are permitted 
    provided that the following conditions are met:   


 > 1. Redistributions of source code must retain the above copyright notice, this list of conditions
    and the following disclaimer.

> 2. Redistributions in binary form must reproduce the above copyright notice, this list of
    conditions and the following disclaimer in the documentation and/or other materials provided
    with the distribution.

> 3. Neither the name of the copyright holder nor the names of its contributors may be used to 
    endorse or promote products derived from this software without specific prior written permission.

    THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS" AND ANY EXPRESS OR 
    IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND 
    FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT HOLDER OR 
    CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL
    DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, 
    DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY,
    WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY
    WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.

