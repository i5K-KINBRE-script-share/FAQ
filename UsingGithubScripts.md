###Installing scripts

Scripts in the i5K-KINBRE Script Sharing Organization are organized by function (e.g. scripts to assemble genomes or trnscriptomes are found in the transcriptome-and-genome-assembly repository https://github.com/i5K-KINBRE-script-share/transcriptome-and-genome-assembly). A Git repository is a directory (like a folder on Windows or Macs) with a history of all changes made to this repository and information on which version of the repository this copy is.

A repository and the scripts within it can be installed quickly from the terminal by typing:

    git clone [repository URL]
    
For example, to install all scripts related to RNA-Seq annotation and comparison type:

    git clone https://github.com/i5K-KINBRE-script-share/RNA-Seq-annotation-and-comparison
    
All repositories in the i5K-KINBRE Script Sharing Organization are listed at https://github.com/i5K-KINBRE-script-share.

###Updating scripts

You should change directories (cd) into your copy of the Git repository and type:

    cd [repository directory]
    git pull
    
Your version will be automatially updated to the most recent version.

For example to update my copy of RNA-Seq-annotation-and-comparison I would type:

    cd RNA-Seq-annotation-and-comparison
    git pull

###Updating if you have accedentally altered your scripts

If you would like to update your scripts but you have accedently altered your copies type:

    cd [repository directory]
    git fetch origin
    git reset --hard origin/master
    

