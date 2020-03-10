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

Multi-Energy networks and the utilization of synergies between energy sectors are an important research topic today. To
simulate these networks, it is crucial to not only include coupling points between the sectors in the analysis, but also to
know the network state of sectors of interest. pandapipes was developed to provide a tool capable of calculating
state variables of multi-energy networks. To do so, it can be used in combination with the open source software
pandapower. If only gas or district heating networks are of interest, pandapipes can also be used as a stand-alone 
application. 

In this sense, pandapipes closes two gaps: There are not many tools available which focus on multi-energy grid modeling.
In addition, most software for calculating fluid networks is only commercially available. The following table
summarizes some properties of commercial and open source tools, respectively.


|                                                      | Fluid Models                                                                                                                                | Automation                                                                                                               | Customization                                                                                           |
|------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| Commercial Tools (e.g. Stanet, Sincal, NEPLAN)       | <span style="color:green">Thoroughly validated and easy to parametrize models of pipes, pumps, valves etc. Typically, multi-energy networks are not considered.</span>            | <span style="color:red">Graphical User Interface (GUI) applications that are difficult to automate.</span>                     | <span style="color:red">Restricted possibilities for customization due to proprietary code base.</span> |
| Open Source Tools (e.g. Modelica, TransientEE)       | <span style="color:red">Models that require parametrization by the user with expert knowledge.</span>                                    | <span style="color:green">Console or GUI applications that might be automized.</span>                        | <span style="color:green">Open Source code base that can be freely modified and customized.</span>      |
| **pandapipes**                                       | <span style="color:green">**Thoroughly validated and easy to parametrize fluid models of pipes, pumps, valves etc. with the focus on multi-energy grids.**</span>        | <span style="color:green">**Console application that is designed for automated evaluations.**</span>                     | <span style="color:green">**Open source code base that can be freely modified and customized.**</span>  |

This is of course a very broad classification of tools that is only supposed to illustrate the focus of pandapipes without
considering the diverse landscape of existing tools. 


**Scope**<br>

pandapipes is aimed at **static** analysis of **balanced** fluid systems. This allows analysis of:
- **Static** or **quasi-static** analyses of pressure and velocity distributions in fluid networks using incompressible or compressible media. Gas composition is assumed fix.
-  **Static** or **quasi-static** analyses of temperature distributions in fluid networks. At present, this kind of analysis is only possible for incompressible media.


<h2 id="modeling">Fluid System Modeling</h2>

<h3 id="datastructure">Tabular Data Structure</h3>

pandapipes is based on a tabular data structure, where every element type is represented by a table that holds all parameters for a specific
element and a result table which contains the element specific results of the different analysis methods. The tabular data structure is
based on the Python library pandas. It allows storing variables of any data type, so that parameters can be stored
together with status variables and meta-data, such as names or descriptions. The tables can be easily expanded and customized by adding new
columns without influencing the pandapipes functionality. All inherent pandas methods can be used to efficiently read, write and
analyze the network and results data.

<h3 id="std_types">Standard Type Libraries</h3>

pandapipes includes a standard type library that allows the creation of pipes and pumps using predefined basic standard type parameters. The user can either define individual standard types or use the predefined pandapipes basic standard types for convenient definition of networks.

<h3 id="std_types">Fluid Property Library</h3>

pandapipes includes a fluid property library that allows the creation of fluid properties using predefined data. The user can either define individual properties or use the predefined data.
   
<h2 id="analysis">Fluid System Analysis</h2>

pandapipes supports the following fluid systems analysis functions:

- [Pipe Flow](#pf)


<h3 id="pf">Pipe Flow</h3>

The pandapipes pipe flow solver is based on the Newton-Raphson method.
<br><small>[Learn more](https://pandapipes.readthedocs.io/en/latest/pipeflow.html)</small>

<font size="4"><b>Initialization</b></font>

pandapipes offers two different methods to initialize the solution
vector for the pipe flow calculation:
   - flat start
   - Solution vector of a previous calculation
   

<h2 id="tests">Tests and Validation</h2>

<font size="5"><b>STANET Tests</b></font>
<br>
So far pandapipes has been successfully tested with [pytest](https://docs.pytest.org/en/latest/).
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

> Copyright (c) 2020 by Fraunhofer Institute for Energy Economics
and Energy System Technology (IEE) Kassel and individual contributors (see AUTHORS file for details).
All rights reserved.
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
    
    