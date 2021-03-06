# Google Summer of Code 2020
The development team of the [C3G](http://computationalgenomics.ca/) Montreal node is aiming to participate as an organization in Google Summer of Code 2020. We are offering to mentor students who wish to spend their summer working on interesting and user-friendly software pipelines for the analysis of Next-Generation Sequencing data. This page hosts information for prospective GSoC students and our project ideas. We are looking for 4 to 6 excellent students to collaborate on some of our research and development projects.

[**See GSoC 2020 full time line**](timeline.md)

--------------
Table of content:

[TOC]

--------------
# The C3G montreal node 
The Montreal C3G nodes is hosted at the McGill University and Genome Quebec Innovation Center (MUGQIC). The Montreal node is strongly involved in the [GenAP](https://genap.ca/) developement team and had developed a robust genomic data analysis pipeline set. Since 2011, we have completed more than 400 bioinformatics analysis projects with over 290 distinct groups of researchers across Canada. Our teams have significant experience in personalized medicine applications. These have included genome analysis and interpretation of personal genomes, technology and services to record patient presentations, DNA-, RNA- and ChIP-seq data analysis, and analysis of complete human epigenomes in both germline disorders and cancers.

The current members of the team are:

 * Guillaume Bourque, _Ph.D_ - Director
 * Mathieu Bourgey, _Ph.D_ - R&D Bioinformatics manager
 * Francois Lefebvre, _MSc_ - Services Bioinformatics manager
 * David Bujold, _MSc_ - GenAP project manager  
 * Edouard Henrion, _MSc_ - Software developer
 * Emmanuel Gonzalez, _Ph.D_ - Bioinformatics specialist
 * Gary Leveque, _MSc_ - Bioinformatics specialist
 * Robert Eveleigh, _MSc_ - Bioinformatics specialist
 * Rola Dali, _Ph.D_ - Bioinformatics specialist
 * Pierre-Olivier Quirion, _Ph.D_ - HPC specialist   
 * José Héctor Gálvez López, _MSc_ - Bioinformatics specialist
 * Ulysse Fortier-Gauthier, _Ph.D_ - Bioinformatics software developer
 * Pascale Marquis, _MSc_ - Bioinformatics consultant
 * Alain Pacis, _Ph.D_ - Bioinformatics consultant
 * Robert Syme, _Ph.D_ - Bioinformatics consultant
 * Senthilkumar Kailasam, _Ph.D_ - Bioinformatics consultant
 * Paul Stretenowich, _MSc_ - Bioinformatics consultant
 * Ksenia Zaytseva, __ - Scientific Data Architect
 * Lindsay Dayton, _MSc_ - Research administrator
 * Ksenia Egorova, __ - Research administrator
 * Rachade Hmamouchi, __ - Program manager
 * David Anderson, _B.FA_ - Web designer
 * Romain Grégoire, Web Application Developer
 * David Lougheed, Web Application Developer
 * Patricia Goerner-Potvin, _MSc_ - PhD student
 * Maxime Caron, _MSc_ - PhD student
 * Jeffrey Hyacinthe, PhD student
 * Audrey Baguette, MSc student
 * Cristian Groza, Undergraduate student
 * Alexis Nolin Lapalme, Undergraduate student
 * David Lougheed, Undergraduate student


Collaborators:

 * Simon Gravel, _Ph.D_ - Assistant Professor at McGill University - [Simon's lab](simongravlabel.lab.mcgill.ca/Home.html)

# Mailing list

Students will be added to the mailing list once accepted into the program.

# Student application
Selected students will be automatically added to the mailing list

Selected students should follow the [student application guideline](Student_application.md)

# INSTRUCTIONS

Please read the list of available projects hosted for this year. If you are interested in a project, please complete the *Selection tests* for that project and contact the project mentors directly by email. If the project does not have Selection tests, contact the project mentors with your CV and ask about their requirements. Please **DO NOT post on the genpipes forum**, as not all mentors monitor the forum.


-----------------------------

# Proposed Projects 


## Creating a new pipeline for long-read RNA-seq using StringTie v2

The majority of contemporary genomics and transcriptomics research is carried out using short-read technology such as the output of Illumina sequencers. However, newer long-read technologies such as PacBio and Oxford Nanopore (ONT) are becoming more prevalent due to the advantages they offer over short reads. The main advantage of long reads is that they span a much larger portion of the genome or transcriptome, making it easier to detect events such as structural variants or isoforms. As more researchers begin to take advantage of long reads, GenPipes needs to evolve and support long-read technology in its main pipelines. 

The objective of this project is to create a new RNA-seq pipeline (rnaseq_longreads), that supports long-read inputs. The new pipeline would be created based on the current versions of the RNA-seq pipeline, with the addition of the minimap2 aligner as well as StringTie v2 and Ballgown for generating transcript counts. 

If time allows, in addition to implementing a long-read RNA-seq pipeline within the GenPipes framework, the student will help update the RNA-seq pipeline to also use StringTie2 as well as test both pipelines to ensure they are working properly. 


### Developer profile

**Required skills:** Python, R, bash, git  
**Nice to have:** Experience with genomics data, especially long-reads


### Selection tests

1. Install the following software in your computing environment: 

	a. [StringTie v2](https://github.com/gpertea/stringtie/tree/v2.1.1)  (run test suite to ensure it is working).   
	b. The [Ballgown](http://bioconductor.org/packages/release/bioc/html/ballgown.html) R-Bioconductor library (If required, install R and any additional dependencies).     
	c. [Tablemaker](https://github.com/leekgroup/tablemaker).  
	 
        
2. Download the following nanopore mouse RNA-seq datasets from [this recent study](https://www.nature.com/articles/s41598-019-51470-9): 

   a. Brain C1: [BAM file](http://www.genoscope.cns.fr/externe/ONT_mouse_RNA/data/transcriptome/RNA_nanopore.brain.C1R1_mapping_E94_minimap2_primary_no_read_less_than_80QC.bam)       
   b. Liver C1: [BAM file](http://www.genoscope.cns.fr/externe/ONT_mouse_RNA/data/transcriptome/RNA_nanopore.liver.C1R1_mapping_E94_minimap2_primary_no_read_less_than_80QC.bam)
   
        
3. Using StringTie v2 long-read mode, generate a GTF file for each of these samples. 

4. Run Tablemaker on the two samples above (use the BAM and GTF files used above). 

5. Import the output of Tablemaker into R using Ballgown. 


Save your work in an external repository and send us a link to it. The repository must contain: 

* A bash script with your StringTie v2 and Tablemaker commands. 
* An R script with your Ballgown commands. 
* The first 1000 lines of both GTF files generated using StringTie2. 
* The first 1000 lines of the FPKM matrix produced by Ballgown, saved as a csv. 
* Hint: use the `texpr` function in Ballgown to obtain this matrix.


### Mentors
[Jose Hector Galvez](mailto:jose.hector.galvez@computationalgenomics.ca)



-----------------------------


## Large-scale modelling of genetic data

Genomic data poses formidable modelling challenges. At the simplest level, genetic information can be summarized as a matrix with rows corresponding to individuals and columns corresponding to genetic markers. Contemporary datasets have hundreds of thousands of rows and millions of columns. Even though we have pretty good mathematical models of how genetic data gets transmitted from generation to generation, fitting those on computers is VERY challenging.

Understanding genetic data requires careful modelling of historical events and efficient computing. Our group is involved in open-source efforts to build better simulations (https://github.com/tskit-dev/msprime), better encode genetic data (https://github.com/tskit-dev/tskit), and provide community curated quantitative models of human history (https://github.com/popsim-consortium/stdpopsim).

There are multiple related projects projects including:
* building more efficient simulation algorithms and data structures,
* implementing more biologically realistic simulations (including information about function , sex-specific recombination and mutation processes, biased gene conversion, inbreeding,etc).
and
* implementing existing historical models from the literature into model databases.


### Selection tests

First read and run the Hardy-Weiberg-allel.ipynb notebook in the data_test directory. This will provide instructions to download a genetic data file.  
Complete the notebooks fst\_allel-hints.ipynb and wright-fisher-hints.ipnb found in the "data_test" folder by filling in the blanks and ellipses (…), run the code, and answer the interpretation questions.

In your application, submit a cv, your completed notebooks (in ipynb or pdf format), and specific interests that you may have. There are many needs on this project from user interface, algorithms, implementations of statistical inference tools, and implementations  of more realistic biological models.  

### Mentors
[Dr. Simon Gravel](mailto:simon.gravel@mcgill.ca)

-----------------------------


## Automatic update of the C3G software stack catalog

GenPipes is one of the main bioinformatics tools/services offered by the [Canadian Center for Computational genomics (C3G)](http://www.computationalgenomics.ca). It consists of bioinformatics pipelines designed for Genomics sequencing analysis.
In order to perform those analysis, the C3G developers maintain a software stack which continuously grows and updates.
A catalog of the installed softwares was built in JSON format and is available on the C3G website (http://www.computationalgenomics.ca/cvmfs-modules/).

This project consists of implementing a system to automate the update of the JSON catalog as new versions and softwares are installed. This system will have to be fully integrated in the current installation workflow of the C3G developers (https://bitbucket.org/mugqic/genpipes/src/master/#markdown-header-install-a-new-module) and eventually be able to parse Tcl module files (https://modules.readthedocs.io/en/stable/modulefile.html) which would represent the source of the catalog.

### Developer profile

**Required skills:** JSON, Git, Python, Bash  
**Nice to have:** Tcl modules experience, software versioning

### Selection tests

The content of the `data_test/SoftStackCatalog` folder mimics the file structure of the C3G software stack, where the `modulefiles/mugqic` directory contains all the Tcl module files used by the GenPipes anaylsis pilelines to call all their required software.
The `software` directory would actually contain all the tools provided by the software stack.

Here the `modulefiles/mugqic` folder only contains a handful of the C3G module files. These modules refer to softwares installed in the `software` directory.

The `software` folder contains all the directory structures of the software specified in the `modulefiles/mugqic` module files (it does not contain the software itself as it is not necessary for the test).


1- Parse the whole file structure of the [`data_test/SoftStackCatalog/modulefiles/mugqic/`](https://bitbucket.org/mugqic/gsoc_2020/src/master/data_test/SoftStackCatalog/modulefiles/mugqic/) folder and create a JSON file that would represent all the provided software and available versions.

2- Identify the lacking information for a comprehensive and meaningful software catalog : besides the name and version of the software, what relevant information should be provided by the catalog (software description, website, etc...).
   Propose ways to find, gather and store this missing information.

Optionally, you could have a look at how we install software on the C3G software stack by looking at some of our installaton scripts [here](https://bitbucket.org/mugqic/genpipes/src/master/resources/modules/).
These scripts allow us to install software, as well as create the associated module files for the desired versions.

Save your work (script and result JSON) in an external repository and send us a link to it.
Additional information that you think of can be either sent by email or included in the repo within a text file.


### Mentors
[Edouard Henrion](mailto:edouard.henrion@computationalgenomics.ca)   
[Pierre-Olivier Quirion](mailto:po.quirion@mcgill.ca)  

-----------------------------



## DevOps for the McGill Genome Center Scientific Workflow System

We have a Powerful system used to do Genomics sequencing called Genpipes. It is optimized to run on  the High Performance Computing (HPC) system of Compute Canada (https://docs.computecanada.ca/wiki/Systems_overview)
We now want to push things further by allowing GenPipes to deploy into the cloud.
In order to do this the student will adapt Terraform recipes so our system can be deployed on Openstack, on GCP, AWS, Azur, etc.

**Some Key word for that project:**  
 Terraform, Yml, Git, Python, Bash, CloudInit, Puppet, Networking

### Selection tests

1- Install Singularity on a Linux computer. You will need to be sudoer to do that: https://github.com/sylabs/singularity/blob/master/INSTALL.md

2- Clone our pipeline system from bitbucket (https://bitbucket.org/mugqic/genpipes) in  a work directory $WORKDIR.  

3- Checkout the dev branch of our repo, note the hash value of the commit, you will need to send us that information. 

4- Get the Genpipes in a container wrapper utilities and set it up: https://bitbucket.org/mugqic/genpipes/src/dev/#markdown-header-genpipes-container & https://github.com/c3g/genpipes_in_a_container
Now you technically have all that is needed to run our pipeline in "batch" mode

5- Create the instruction for the Chipseq Pipeline with this extremely long command:
$WORKDIR/genpipes/pipelines/chipseq/chipseq.py  --wrap -c $WORKDIR/genpipes/pipelines/chipseq/chipseq.base.ini  $WORKDIR/genpipes/pipelines/chipseq/cit.ini $WORKDIR/genpipes/pipelines/chipseq/chipseq.batch.ini -r /cvmfs/soft.mugqic/CentOS6/testdata/chipseq/readset.chipseq.txt -d /cvmfs/soft.mugqic/CentOS6/testdata/chipseq/design.chipseq.txt -j batch --no-json > chipseq_commands.sh

6- Send us your chipseq_commands.sh file and the hash of the genpipes commit you used to create it.

Good luck!


### Mentors
[Pierre-Olivier Quirion](mailto:po.quirion@mcgill.ca)  
[Edouard Henrion](mailto:edouard.henrion@computationalgenomics.ca) 

-----------------------------


## Ingesting the Canadian Common CV

The Canadian Common CV (CCV) is a tool that allows Canadian researchers to input their resume in a standardized format. It is used by multiple organizations such as granting agencies, federal, provincial and academic instituions. The tool enable users to output results in an XML document, that can be used in external applications. More information on the CCV is available here:

https://ccv-cvc.ca/indexresearcher-eng.frm

This project involves building an application that can ingest, store and query data from the CCV. It includes the following components:

1- A standalone library to parse CCV documents and organize them in a data structure.

2- A tool using the above library on the command line to ingest a CCV, and store its components in a relational database.

3- An API to query available CCVs based on multiple criteria.

4- A web application to output results.

The libraries will be implemented in Python, and data should be collected and organized in a SQLite database. The web application back-end should be implemented either using Flask or Django, and the front-end should be written in React.

### Selection tests

Coming soon

### Mentors

[Romain Gregoire](mailto:romain.gregoire@computationalgenomics.ca)   
[David Bujold](mailto:david.bujold@computationalgenomics.ca)   


-----------------------------


