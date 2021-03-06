# MOpt-AFL
### 1. Description
MOpt-AFL is a AFL-based fuzzer that utilizes a customized Particle Swarm Optimization (PSO) algorithm to find the optimal selection probability distribution of operators with respect to fuzzing effectiveness. More details can be found in the technical report. The installation of MOpt-AFL is the same as AFL's. 

### 2. Cite Information
Chenyang Lv, Shouling Ji, Chao Zhang, Yuwei Li, Wei-Han Lee, Yu Song and Raheem Beyah, MOpt: Optimize Mutation Scheduling for Fuzzers, USENIX Security 2019. 

### 3. Seed Sets
We open source all the seed sets used in the paper "MOpt: Optimize Mutation Scheduling for Fuzzers".

### 4. Experiment Results
The experiment results can be found in https://drive.google.com/drive/folders/184GOzkZGls1H2NuLuUfSp9gfqp1E2-lL?usp=sharing.  We only open source the crash files since the space is limited. 

### 5. Technical Report
MOpt_TechReport.pdf is the technical report of the paper "MOpt: Optimize Mutation Scheduling for Fuzzers", which contains more deatails. 

### 6. Parameter Introduction
Most important, you must add the parameter `-L` (e.g., `-L 0`) to launch the MOpt scheme. 
<br>`-L` controls the time to move on to the pacemaker fuzzing mode.
<br>`-L t:` when MOpt-AFL finishes the mutation of one input, if it has not discovered any new unique crash or path for more than t min, MOpt-AFL will enter the pacemaker fuzzing mode. 
<br>Setting 0 will enter the pacemaker fuzzing mode at first, which is recommended in a short time-scale evaluation. 

Other important parameters can be found in afl-fuzz.c, for instance, 
<br>`swarm_num:` the number of the PSO swarms used in the fuzzing process.
<br>`period_pilot:` how many times MOpt-AFL will execute the target program in the pilot fuzzing module, then it will enter the core fuzzing module. 
<br>`period_core:` how many times MOpt-AFL will execute the target program in the core fuzzing module, then it will enter the PSO updating module. 
<br>`limit_time_bound:` control how many interesting test cases need to be found before MOpt-AFL quits the pacemaker fuzzing mode and reuses the deterministic stage. 
0 < `limit_time_bound` < 1, MOpt-AFL-tmp.  `limit_time_bound` >= 1, MOpt-AFL-ever. 

Having fun with MOpt-AFL. 
