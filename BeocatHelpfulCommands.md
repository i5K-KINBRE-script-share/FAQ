##Submitting  jobs
    qsub [ options ] [ command]
    
Example:

    qsub -l mem=10G,h_rt=10:00:00 cell_lines_index.sh
    
Useful options:

    #recieve emails at start and completion of jobs
    -m abe -M [myemail@gmail.com]
    #memory and time requests
    -l mem=10G,h_rt=10:00:00
    #redirect standard out
    -o [path]
    #redirect standard error
    -e [path]
    
##Checking the queues
To check all jobs in the queue or running type:

    qstat
    
To check status  of only your jobs on BEOCAT type:

    status
    
You will see a report similar to the following one:

    868261 0.02298 mira-tick. sheltonj     r     03/25/2014 13:57:50 long.q@scout25.beocat              1 

The job ID, the priority of the job, the name of the job, the job owner, the status of the  job, the submission or start time and date of the job, the  queue  the  job  is  assigned  to  (for  running  or suspended jobs only), the number of job slots are listed in this order.

Job status can be either:

    qw = queued and waiting
    r = running
    d=deletion
    E=error
    h=holding
    r=running
    R=Restarted
    s=suspended
    t=transfering
    T=Thresholding
    q=queued
    w=waiting

##Running jobs

In all of these examples replace '868261' with your job number.

To delete a job type this:

    qdel 868261

You will see a report similar to this:

    sheltonj has deleted job 868261

To find out how much memory your job is using type

    qstat -j 868261
    
##After a job has run

To find out how much memory your job is used at its maximum type this. Also find out runtime and exit status (0 = exited without error):

    qacct -j 868261

