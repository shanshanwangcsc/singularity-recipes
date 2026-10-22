# 1. Create a temporary directory in your scratch space
```bash
mkdir -p /scratch/project_****/$USER/apptainer_build_tmp
```
# 2. Run `make`, passing the `TMPDIR`
```bash
make TMPDIR=/scratch/project_****/$USER/apptainer_build_tmp
```
# 3. To use the `phy_ubuntu` container 
```bash
apptainer run --nv phy_ubuntu.sif template-gui /path/to/your/spikesorting/output/params.py 
``` 