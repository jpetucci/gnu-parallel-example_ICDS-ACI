# gnu-parallel-example_ICDS-ACI

This repo contains an example for using GNU parallel (gnu.org/software/parallel/) on the ICDS-ACI systems to complete a list of tasks in a file. The example distributes tasks across multiple nodes.

Requirements:
A conda environment that contains R with the benchmarkme library and the latest version of gnu parallel.
To create this on ICDS-ACI follow the steps below:
$ module purge && module load python/3.6.3-anaconda5.0.1  
$ conda create -n myenv -y  
$ source activate myenv  
$ conda install -c conda-forge r-benchmarkme  
$ conda install -c conda-forge parallel  


Summary:
The list of tasks (given in task_list.txt) are simple R benchmarkme runs defined in the R-script (my_R_script). The jobscript.pbs file requests 2 nodes and 10 cores per node. The env_parallel command distributesthe list of tasks to the nodes assigned to the job ($PBS_NODEFILE). The --jobs restricts that maximum number of jobs simulaneously running on each node to 10. The example_output directory contains expected output of a successful job
