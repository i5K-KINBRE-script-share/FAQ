##Download your data to Beocat

###wget

If your sequencing facility gives you an address (URL) to download your data from you can use wget. To get the URL of the file you want you can right-click (control-click on Macs) on the hyperlink for the file and copy the link. More examples of using wget can be found at http://www.gnu.org/software/wget/manual/html_node/Simple-Usage.html#Simple-Usage.

In this example assume I have a URL that points to a single file. In this case I can just `cd` to the directory I would like to store my data in and type `wget` followed by the URL.

```S
wget ftp://ftp.ncbi.nlm.nih.gov/genomes/Tribolium_castaneum/README

```

Here is an example of using `wget` to download multple files from the NCBI FTP site https://www.ncbi.nlm.nih.gov/Ftp/. In this case I want all files with the files extension `.gz`. 

```S
wget -r -A.gz ftp://ftp.ncbi.nlm.nih.gov/genomes/Tribolium_castaneum/CHR_MT/

##My files will be in directories matching the organization of the data on the FTP.

ls ftp.ncbi.nlm.nih.gov/genomes/Tribolium_castaneum/CHR_MT/

##If I would like to put these files in my own directory I can move them using the mv command.

mv ftp.ncbi.nlm.nih.gov/genomes/Tribolium_castaneum/CHR_MT/* ~/tester/

##Now I should decompress my files using gunzip

gunzip ~/tester/*.gz
```

###Decompressing files

Raw data is often compressed so that it can be transferred more quickly. Look at your file extension to see what commands to use to decompress your data. You can also use `*` as a wildcard in the filename to decompress multiple files at once.

####If your file extension is .gz

```S
gunzip filename.gz

##The following command will decompress all .gz files in the current directory

gunzip *.gz
```

####If your file extension is .zip

```S
unzip filename.zip

##The following command will decompress all .zip files in the current directory

gunzip *.zip
```

####If your file extension is .tar.gz


```S
tar -xvzf filename.tar.gz

##The following command will decompress all .tar.gz files in the current directory

tar -xvzf *.tar.gz

```

####If your file extension is .tar.bz2


```S
tar -jxvf  filename.tar.bz2

##The following command will decompress all .tar.bz2 files in the current directory

tar -jxvf  *.tar.bz2

```

####If your files are from the Short Read Archive (SRA)

Files stored on the NCBI Short Read Archive (SRA) need to be converted to fastq or the appropriate format after downloading. The data in this example is from project http://www.ncbi.nlm.nih.gov/sra/SRX026694. It was also used as a dataset in Adam Roberts & Lior Pachter (2012) paper "Streaming fragment assignment for real-time analysis of sequencing experiments" you can find a link to this paper at http://suggestedbioinfo.blogspot.com/2012/11/expression-profiling-faster-more.html.

```S
#Use wget to download from the SRA

wget http://ftp-trace.ncbi.nlm.nih.gov/sra/sra-instant/reads/ByExp/sra/SRX/SRX026/SRX026678/SRR065509/SRR065509.sra

#Use the approriate data-dump program (e.g. fastq-dump for a fastq file like this one).

/homes/bioinfo/bioinfo_software/sratoolkit.2.3.5-ubuntu64/bin/fastq-dump SRR065509.sra

#For more sra tool options type:

ls /homes/bioinfo/bioinfo_software/sratoolkit.2.3.5-ubuntu64/bin/

```


