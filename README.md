# ksu-hpc-torque
Torque Submission Script for KSU HPC

Submission script for running the adversarial-yolo repo on the Kennesaw State University High Performance Cluster. The documentation used to develop this script can be found on the KSU HPC website:
https://hpcdocs.kennesaw.edu/
as well as the KSU Center for Research Computing website:
https://research.kennesaw.edu/computing/

To run the script, first load the required modules into your user account:
module load CUDA/11.04
module load Anaconda/2023.07

Then create a Conda virtual environment that contains all the necessary packages:
conda env create -f yoloEnvironment.yml

Replace NAME@Kennesaw.edu with your KSU email and JOBNAME with the name you want for your job. Then simply submit the job with:
qsub yolo-torque.pbs

Once running, you can view the status of all jobs with:
qstat -a

To delete a job early, simply use:
qdel JOBID.roland
where JOBID is the ID number given by the HPC on submitting the job.
