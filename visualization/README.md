# 1. Create a safe temporary directory in your scratch space
mkdir -p /scratch/project_****/$USER/apptainer_build_tmp

# 2. Run make, passing the safe TMPDIR
make TMPDIR=/scratch/project_****/$USER/apptainer_build_tmp