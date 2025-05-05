# meam620-project1-phase-2--3d-path-planning-solved
**TO GET THIS SOLUTION VISIT:** [MEAM620-Project1 phase 2- 3D Path Planning Solved](https://www.ankitcodinghub.com/product/meam620-project-2-3d-path-planning-solved/)


---

📩 **If you need this solution or have special requests:** **Email:** ankitcoding@gmail.com  
📱 **WhatsApp:** +1 419 877 7882  
📄 **Get a quote instantly using this form:** [Ask Homework Questions](https://www.ankitcodinghub.com/services/ask-homework-questions/)

*We deliver fast, professional, and affordable academic help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;50555&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;1&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;5&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;5\/5 - (1 vote)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;MEAM620-Project1 phase  2- 3D Path Planning Solved&quot;,&quot;width&quot;:&quot;138&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

<div class="kksr-stars">

<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>

<div class="kksr-stars-active" style="width: 138px;">
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>


<div class="kksr-legend" style="font-size: 19.2px;">
            5/5 - (1 vote)    </div>
    </div>
Introduction

In this assignment you will begin building a trajectory generator for a quadrotor by implementing two graph search algorithms: Dijkstra’s algorithm and A*. The goal of this phase is to compute resolution optimal paths in a 3D environment from a start position to a goal position that avoids colliding with obstacles. This project is independent of Phase 1, but we will combine our planning and control algorithms in a subsequent phase.

Code Packet

Provided Files

<ul>
<li>flightsim/world.py</li>
</ul>
The environments used for this assignment are defined by <strong><sub>World </sub></strong>objects. As documented in the file header, the world is defined by a dictionary containing the bounds of the world (’extents’), and a list of dictionaries of axis-aligned cuboid obstacles (’blocks’), which have ’extents’ and ’colors’. These worlds can be loaded from .json files like those provided in <sub>util/</sub>. We recommend you create more examples for yourself. Please do not submit or modify the World object code or any other files from <sub>flightsim/</sub>.

<ul>
<li>code/occupancy_map.py</li>
</ul>
In order to find paths with a graph search algorithm in a <strong><sub>World</sub></strong>, it is necessary to first represent the environment as a graph. To do this we discretize space into a regular grid and attach graph nodes to each voxel. An <strong><sub>OccupancyMap </sub></strong>object is a voxel grid corresponding to a <strong><sub>World </sub></strong>object. Voxels with value <em><sub>False </sub></em>enclose free space while voxels with value <em><sub>True </sub></em>intersect obstacles.

The choice of grid resolution is especially important and impacts both the runtime of the algorithm as well as its ability to find a path. Another consideration is safety, which becomes critical when considering real world applications. Since quadrotors are not infinitesimal points but rather physical objects that take up space, it is important to ensure that generated paths avoid all obstacles in the environment with some margin. The appropriate choice of margin is a balance between safety and path length. Choose a margin too small and your quad may strike an obstacle and crash. Choose a margin too big and the goal may become inaccessible. The provided <strong><sub>OccupancyMap </sub></strong>class is already parameterized by the resolution of the discretization and the margin of inflation.

You are free to modify <sub>occupancy_map.py</sub>, though it is not necessary to complete the assignment.

<ul>
<li>code/sandbox.py</li>
</ul>
This script loads a <sub>World</sub>, runs your algorithm, and plots the results. It is useful for debugging.

<ul>
<li>util/test.py</li>
</ul>
This script runs tests against all <sub>test_*.json </sub>maps in <sub>util</sub>, including any you have created yourself.

Tasks

<ul>
<li>graph_search.py</li>
</ul>
Your main task is to implement Dijkstra’s algorithm as described in class. A description of the inputs and expected outputs can be found in the header of the provided file.

A popular variant of Dijkstra’s algorithm is the A* algorithm. Since both algorithms are very similar, modify your completed graph search function so that when the astar parameter is <em><sub>True</sub></em>, it uses distance to the goal as a heuristic to guide the search. Remember that any heuristic must be admissible and consistent; if not, the algorithm is no longer guaranteed to return the shortest path.

&nbsp;
