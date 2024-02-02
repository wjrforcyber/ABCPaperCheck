# Research related to ABC

[ABC](https://github.com/berkeley-abc/abc) is a very popular opensource Logic Synthesis project, some of the research implemented in ABC or related to ABC is recorded here.

This repo also helps people who want to read ABC code properly, research paper is a good start before accessing plain code.

Most of the paper referenced here can be found at Prof Alan Mishchenko's [publication page](https://people.eecs.berkeley.edu/~alanmi/publications/).

Another [EPFL Isils group](https://github.com/lsils) also has very high quality synthesis research, feel free to add anything interesting to the list.

## Command and Research Related

### IO Group

#### read_aiger

- [Local Two-Level And-Inverter Graph Minimization without Blowup](https://fmv.jku.at/papers/BrummayerBiere-MEMICS06.pdf)
<br>This one is referenced in ABC when constructing AIG.
- [AIGER 1.9 AND Beyond](https://fmv.jku.at/papers/BiereHeljankoWieringa-FMV-TR-11-2.pdf)
- [The AIGER And-Inverter Graph (AIG) Format Version 20071012](https://fmv.jku.at/papers/Biere-FMV-TR-07-1.pdf)
<br>This version is much more detailed than the latest one and illustrates the original AIG format and how to parse.

#### read_blif
- [Berkeley Logic Interchange Format(BLIF)](https://course.ece.cmu.edu/~ee760/760docs/blif.pdf)
- [BLIF-MV](https://people.eecs.berkeley.edu/~alanmi/publications/other/blifmv.pdf)
<br>BLIF-MV format is the extended BLIF format.


### Optimization Group

#### rewite/refactor/balance
- [DAG-Aware AIG Rewriting A Fresh Look at Combinational Logic Synthesis](https://people.eecs.berkeley.edu/~alanmi/publications/2006/dac06_rwr.pdf)

#### if -g 
- [Delay Optimization Using SOP Balancing](https://people.eecs.berkeley.edu/~alanmi/publications/2011/iccad11_sop.pdf)
<br>*Openroad flow use SOP balance in their [script](https://github.com/The-OpenROAD-Project/OpenROAD-flow-scripts/blob/master/flow/scripts/abc_speed.script) (Update 2024.1.2).
<br>Optimize some aig structure rw/rf/b can not optimize.

#### if -y
- [Lazy Man’s Logic Synthesis](https://people.eecs.berkeley.edu/~alanmi/publications/2012/iccad12_lms.pdf)
<br>Frequency based method to collect better pattern from design. Can even deal with pattens SOP-balance can not break.

#### if -u 
- [Busy Man’s Synthesis: Combinational Delay Optimization With SAT](https://people.eecs.berkeley.edu/~alanmi/publications/2017/date17_bms.pdf)


### Mapper Group

### Post-Mappinng Group
- [Scalable Don’t-Care-Based Logic Optimization and Resynthesis](https://people.eecs.berkeley.edu/~alanmi/publications/2011/trets11_mfs.pdf)
<br>Re-sub based resynthesis + don't care based resynthesis

- [FlowMap: An Optimal Technology Mapping Algorithm for Delay Optimization
in Lookup-Table Based FPGA Designs](https://limsk.ece.gatech.edu/course/ece6133/papers/flowmap.pdf)
<br>FlowMap

## Others
- [Old version of Logic synthesis tools](https://jackhack96.github.io/logic-synthesis/mvsis.html)
<br>Espresso, SIS, MVSIS are here.

