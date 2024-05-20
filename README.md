# GMRec
 For results: if you wish to run it for yourself:
### Environment
setting up: following [environment.yaml] in Mamba4Rec will do \\
activating and running: \\
srun -t 10:05:00 --mem=16000 --gres=gpu:1 --pty /bin/bash # allocating GPU
singularity exec --nv --overlay /vast/[id]/mamba-rec_env/mamba-rec_env.ext3:ro /scratch/work/public/singularity/cuda11.8.86-cudnn8.7-devel-ubuntu22.04.2.sif /bin/bash
source /ext3/env.sh 
conda activate mamba4rec

### Hyperparameters
--dataset=diginetica[yochoose1_16]
--d_state=128 #this is the hidden state dimension I used for getting my results: running time between 6452 and 9699 seconds

python run_1.py # running with embedding from global and local embedding, with attention weights
python run_2.py # running with only local embedding(last item sequentially)

