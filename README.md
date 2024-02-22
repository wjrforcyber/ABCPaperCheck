# Research related to ABC

[ABC](https://github.com/berkeley-abc/abc) is a very popular opensource Logic Synthesis project, some of the research implemented in ABC or related to ABC is recorded here.

This repo also helps people who want to read ABC code properly, research paper is a good start before accessing plain code.

Most of the paper referenced here can be found at Prof Alan Mishchenko's [publication page](https://people.eecs.berkeley.edu/~alanmi/publications/).

Another [EPFL Isils group](https://github.com/lsils) also has very high quality synthesis research, feel free to add anything interesting to the list.

## Command and Research Related


<details>
  <summary>
    <h3>
      Structure & algorithm
    </h3>
  </summary>

Some structure concept such as K-feasible cuts, priority cuts, MFFC in ABC can be found in following research paper.

- [Quick Look under the Hood of ABC](https://people.eecs.berkeley.edu/~alanmi/abc/programming.pdf)
<br>A brief but important manual helps understand basic network types and structures in ABC.

- [CUDD package](https://web.mit.edu/sage/export/tmp/y/usr/share/doc/polybori/cudd/cuddIntro.html)
<br>A manual helps get familar with CUDD package.

- [Liberty Reference Manual](https://people.eecs.berkeley.edu/~alanmi/publications/other/liberty07_03.pdf), there's probably a new version though, if anyone has a legal reference link, please update.  

- [Priority Cuts Defination](https://people.eecs.berkeley.edu/~alanmi/publications/2007/iccad07_map.pdf)

- [Factor Cus Defination](https://people.eecs.berkeley.edu/~alanmi/publications/2006/iccad06_cut.pdf)

- [Cut Ranking and Pruning: Enabling A General And Efficient FPGA Mapping Solution](https://dl.acm.org/doi/pdf/10.1145/296399.296425)

- [The Disjunctive Decomposition of Logic Functions](https://dl.acm.org/doi/pdf/10.5555/266388.266429)
<br> Good DSD reference.

- [Fast Heuristic Minimization of Exclusive-Sums-of-Products](https://people.eecs.berkeley.edu/~alanmi/publications/2001/rm01_heu.pdf)
<br>ESOP minimizer EXORCISM-4, compared with early EXMIN2/MINT/EXORCISM-2/EXORCISM–3.

#### SAT
- [MiniSAT](https://people.eecs.berkeley.edu/~alanmi/courses/2007_290N/papers/intro_een_sat03.pdf)

</details>


### IO & Util Group

`read_aiger`
- [Local Two-Level And-Inverter Graph Minimization without Blowup](https://fmv.jku.at/papers/BrummayerBiere-MEMICS06.pdf)
<br>This one is referenced in ABC when constructing AIG.
- [AIGER 1.9 AND Beyond](https://fmv.jku.at/papers/BiereHeljankoWieringa-FMV-TR-11-2.pdf)
- [The AIGER And-Inverter Graph (AIG) Format Version 20071012](https://fmv.jku.at/papers/Biere-FMV-TR-07-1.pdf)
<br>This version is much more detailed than the latest one and illustrates the original AIG format and how to parse it.
<br>Prof Armin Biere's [repo](https://github.com/arminbiere/aiger) would help you do the transformation between aig and other format.

`read_blif`
- [Berkeley Logic Interchange Format(BLIF)](https://course.ece.cmu.edu/~ee760/760docs/blif.pdf)
- [BLIF-MV](https://people.eecs.berkeley.edu/~alanmi/publications/other/blifmv.pdf)
<br>BLIF-MV format is the extended BLIF format.

`testnpn`
- [Fast Boolean Matching Based on NPN Classification](https://people.eecs.berkeley.edu/~alanmi/publications/2013/icfpt13_npn.pdf)
- [Fast Adjustable NPN Classification Using Generalized Symmetries](https://people.eecs.berkeley.edu/~alanmi/publications/2019/trets19_npn.pdf)

`&cec`
- [Parallel Combinational Equivalence Checking](https://people.eecs.berkeley.edu/~alanmi/publications/2019/tcad19_cec.pdf)

### Optimization Group

`fraig`
- [FRAIGs: A Unifying Representation for Logic Synthesis and Verification](https://people.eecs.berkeley.edu/~alanmi/publications/2005/tech05_fraigs.pdf)
<br>*Note that the MVSIS link in the paper is no longer avaiable, unofficial source code could be retrived from the **Traditional Logic synthesis tools** part below.

`rewite/refactor/balance`
- [DAG-Aware AIG Rewriting A Fresh Look at Combinational Logic Synthesis](https://people.eecs.berkeley.edu/~alanmi/publications/2006/dac06_rwr.pdf)
<br>*Note that based on this [thread](https://github.com/YosysHQ/yosys/issues/4039), you should consider using `drw/drf`.

`satclp`
- [Progressive Generation of Canonical Irredundant Sums of Products Using a SAT Solver](https://people.eecs.berkeley.edu/~alanmi/publications/2017/book17_satclp.pdf)

`lutmin`
- [Encoding of Boolean functions and its application to LUT cascade synthesis](https://people.eecs.berkeley.edu/~alanmi/publications/2002/iwls02_enc.pdf)
<br>The paper itself does not mention ABC but in this [paper](https://people.eecs.berkeley.edu/~alanmi/publications/2023/iwls23_lut.pdf), reference links `lutmin` here.

`dchoice`
<br> *Note: *"The command dchoice uses various methods for rewriting the AIG to minimize the number of AIG nodes while not increasing the number of its levels. In particular, dchoice strives for smaller delay by “balancing”, which decreases the number of AIG levels by decomposing “wide-input” AND gates in a balanced way."* - [Reference](https://people.eecs.berkeley.edu/~alanmi/publications/2010/fpga10_speedup.pdf)

`if -S`
- [Mapping into LUT Structures](https://people.eecs.berkeley.edu/~alanmi/publications/2012/date12_lut.pdf)


`if -g` 
- [Delay Optimization Using SOP Balancing](https://people.eecs.berkeley.edu/~alanmi/publications/2011/iccad11_sop.pdf)
<br>*Openroad flow use SOP balance in their [script](https://github.com/The-OpenROAD-Project/OpenROAD-flow-scripts/blob/master/flow/scripts/abc_speed.script) (Update 2024.1.2).
<br>Optimize some aig structure rw/rf/b can't optimize.

`if -y`
- [Lazy Man’s Logic Synthesis](https://people.eecs.berkeley.edu/~alanmi/publications/2012/iccad12_lms.pdf)
<br>Frequency based method to collect better pattern from design. Can even deal with pattens SOP-balance can not break.

`if -u` 
- [Busy Man’s Synthesis: Combinational Delay Optimization With SAT](https://people.eecs.berkeley.edu/~alanmi/publications/2017/date17_bms.pdf)


### Mapper Group
`if`
- [Combinational and Sequential Mapping with Priority Cuts](https://people.eecs.berkeley.edu/~alanmi/publications/2007/iccad07_map.pdf)

`&sif`
- [Mapping and Retiming Revisited](https://people.eecs.berkeley.edu/~alanmi/publications/2023/iwls23_m&r.pdf)


#### Other reference
- Recommend this [slide](http://cc.ee.ntu.edu.tw/~jhjiang/instruction/courses/fall14-lsv/lec08_2p.pdf) about technology mapping by Prof Jie-Hong Roland Jiang.
- [FlowMap: An Optimal Technology Mapping Algorithm for Delay Optimization
in Lookup-Table Based FPGA Designs](https://limsk.ece.gatech.edu/course/ece6133/papers/flowmap.pdf)
<br>FlowMap
- [Chortle: A Technology Mapping Program for Lookup Table-Based Field Programmable Gate Arrays](https://dl.acm.org/doi/pdf/10.1145/123186.123418)
<br>Chortle
- [Chortle-crf Fast Technology Table-Based Mapping for FPGAs](https://www.ece.iastate.edu/~zambreno/classes/cpre583/documents/FraRos91A.pdf)
<br>Chortle-crf
- [DAGON: Technology Binding and Local Optimization by DAG Matching](https://dl.acm.org/doi/pdf/10.1145/62882.62957)
<br>The well known DAGON, you could probably see this in any reference(especially lecture slides/research paper etc) online. Based on treeifying and dynamic programming.
- [Delay-Optimal Technology Mapping by DAG Covering](https://dl.acm.org/doi/pdf/10.1145/277044.277142)
<br>DAG mapper
<br>*Note: Faster than tree covering method in DAGON.
- [Logic Decomposition during Technology Mapping](https://dl.acm.org/doi/pdf/10.5555/224841.225050)
<br>Graph mapper
<br>*Note: *"Using supergates and choices, the mapper outperforms both **Graph Map** and **DAG mapper** in delay and area and has a significantly shorter run-time."* - [Reference](https://people.eecs.berkeley.edu/~alanmi/publications/2005/iccad05_map.pdf).


### Post-Mappinng Group
`speedup`
- [Global Delay Optimization using Structural Choices](https://people.eecs.berkeley.edu/~alanmi/publications/2009/tech09_speed.pdf)
<br>*Note: ABC LUT library format also has examples in this paper.

`mfs` & `mfs2`
- [Scalable Don’t-Care-Based Logic Optimization and Resynthesis](https://people.eecs.berkeley.edu/~alanmi/publications/2011/trets11_mfs.pdf)
<br>Re-sub based resynthesis + don't care based resynthesis

`mfs3`
- [Versatile SAT-based Remapping for Standard Cells](https://people.eecs.berkeley.edu/~alanmi/publications/2016/iwls16_mfs3.pdf)
<br> Experiment is performed after `amap` and `&nf -R 1000`.
<br> *Note: `mfs` & `mfs2` are for **LUT-based FPGAs** while `mfs3` is for **standard cells**.
<br> *Gain-based [approach](https://www.ece.ucdavis.edu/~vojin/CLASSES/EPFL/Papers/LE-orig-paper.pdf) deals with delay information.


#### NPN
- [Classifying n-Input Boolean Functions](https://iie.fing.edu.uy/investigacion/grupos/microele//iberchip/pdf/75.pdf)
<br> Very clear illustration of P/NPN class and examples are shown.

## Delay target optimization
- [Enabling Exact Delay Synthesis](https://people.eecs.berkeley.edu/~alanmi/publications/2017/iccad17_eds.pdf)
<br> Personally really recommend this paper which combines timing information with supergates idea and optimized using P classes.

## Area target optimization



## Traditional Logic synthesis tools
- [Old Logic synthesis tools](https://jackhack96.github.io/logic-synthesis/mvsis.html)
<br>Espresso, SIS, MVSIS are here.
<br>*Note: Some of the algorithm in ABC is directly from SIS and MVSIS.

<details>
  <summary>
    <h2>
      Benchmarks
    </h2>
  </summary>
  Here are some famous benchmarks from research/paper above.

- [IWLS 2005 Benchmarks](https://iwls.org/iwls2005/benchmarks.html)
- [EPFL combinational benchmark suite](https://github.com/lsils/benchmarks)
<br>There's also a [paper](https://core.ac.uk/download/pdf/148012141.pdf) related to the benchmark.
<br>*Note that case `hyp` is quite big and skip it if necessary.
- Official AIG benchmarks can be found at [here](https://fmv.jku.at/aiger/).
- [ISCAS](https://web.eecs.umich.edu/~jhayes/iscas.restore/)
- [ITC99](https://github.com/cad-polito-it/I99T)
</details>




## Other repo
[Yosys](https://github.com/YosysHQ/yosys) and [OpenRoad-flow-scripts](https://github.com/The-OpenROAD-Project/OpenROAD-flow-scripts) are good place to find out discussion about ABC since original ABC repo's issues are not very active.


<details>
  <summary>
    <h3>
      SAT solver
    </h3>
  </summary>

This [repo](https://www.cs.cmu.edu/~mheule/15816-f21/slides/practice.pdf) from CMU can give you a brif introduction on the DIMACS format and how to use SAT solver as an interface.

I was trying to matain a collection list of SAT solvers but I have found that [PySAT](https://github.com/pysathq/pysat) seems contain all the well-known SAT solvers. 
</details>
