# **X-Part**
## Overview
**X-Part** is a high-performance tool designed by Prof. Hailong You's EDA group in <big>**X**<big>idian University for hypergraph <big>**Part**<big>itioning. Traditionally, state-of-the-art hypergraph partitioners utilize heuristic methods for initial partitioning. However, the stochastic nature of these heuristics often leads to considerable variability in final solution quality, reflecting the inherent challenges in comprehensive solution space exploration. 

**X-Part** reformulates the hypergraph partitioning problem as the approximate unconstrained optimization problem, which incorporates the global properties of hypergraphs with the Laplacian matrix inspired by *SpecPart* and *K-SpecPart* to approximate the balance constraint, for overcoming the stochastic nature introduced by heuristic strategies in initial partitioning. Furthermore, the assignment indicator vector (binary variable $x_i \in \{0,1\}$) is relaxed to the angle variable of the continuous interval ($\{0,2\pi\}$) in our approximate unconstrained optimization model to significantly reduce computational complexity and accelerate model convergence. Based on the model, a gradient method with approximate optimal stepsize (GM\_AOS)-based strategy is proposed to offer a better partitioning solution, even when facing a large hypergraph. Generally, **X-Part** follows the multi-level partitioning framework, which consists of three stages: Coarsening, Initial Partitioning, and Refinement.

Our experiments on real-world VLSI benchmarks show **X-Part** achieves state-of-the-art partition quality compared to existing hypergraph partitioners.
### Experimental Results
<img width="1585" height="685" alt="image" src="https://github.com/user-attachments/assets/621ba94a-84d0-49a5-ab32-150687be4e7d" />
<img width="1583" height="677" alt="image" src="https://github.com/user-attachments/assets/cf2d5799-d4f6-449d-a68f-b31d6c041d60" />

## Requirements
* Ubuntu 16.04.7 LTS (intel x86_64) or higher version
* CentOS 7.9.2009 (intel x86_64) or higher version
* Redhat 7.7 (intel x86_64) or higher version

## Installation and Run
1. Clone the repository:

```
git clone https://github.com/XidianEDA/X-Part.git
cd X-Part
chmod +x X-Part
```
2. Run X-Part with the following command:

```
./X-Part -h <hypergraph_file> -e <balance_factor> -k <partition_block>
```
### Example
```
./X-Part -h ibm01.hgr -e 0.04 -k 2
```
## Project Structure
```
X-Part/
|__IBM_weight/                  #IBM benchmark with actual node weight
|__TITAN23/                     #Titan23 benchmark
|__X-Part                       #Executable program
|__READ.ME
```
## Authors
Shunyang Bi<sup>**1**</sup>, Yingying Li<sup>**2**</sup>, Zehong Wei<sup>**1**</sup>, Jing Tang, Hailong You<sup>**1**</sup>, Haonan Wu<sup>**1**</sup>, Qiwang Chen<sup>**1**</sup>, Kexin Zhang<sup>**1**</sup>, Cong Li<sup>**1**</sup>, Hongwei Liu<sup>**2**</sup>, Richard Sun<sup>**3**</sup>

<sup>**1**</sup> Faculty of Integrated Circuit, Xidian University & Engineering Research Center of Digital Integrated Circuit Design and Verification Tools, Ministry of Education

<sup>**2**</sup> School of Mathematics and Statistics, Xidian University

<sup>**3**</sup> S2C Inc., Shenzhen, China
