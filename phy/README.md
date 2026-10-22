# 1. Create a safe temporary directory in your scratch space
mkdir -p /scratch/project_123456/$USER/apptainer_build_tmp

# 2. Run make, passing the safe TMPDIR
make TMPDIR=/scratch/project_123456/$USER/apptainer_build_tmp

# 3. To use 

apptainer run --nv phy_ubuntu.sif template-gui /path/to/your/spikesorting/output/params.py 
e.g., the path could be
(.kilosort/.test_data/kilosort4/params.py)