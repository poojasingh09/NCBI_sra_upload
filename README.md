# NCBI_sra_upload
# pooja.singh09@gmail.com
# this repo has instructions on how to upload raw sequencing reads to the NCBI SRA from a linux server.

## step 1 make an account with ncbi and register a bioproject and biosamples. I usually create one bioproject per manuscript but this might be too simple for last projects with overlapping samples etc.
https://www.ncbi.nlm.nih.gov/sra/docs/submitbio/

## step 2 install command-line aspera on your server to facilate data upload. It is much faster than ftp or any other option. Make sure you download a key.
https://www.ncbi.nlm.nih.gov/sra/docs/submitfiles/

## step 3 upload your data to ncbi SRA. Make sure you name a new destination subdirectory every time you upload data for a new project. Having zipped fastq files makes life easier too (gzip *.fq)

ascp -i aspera.openssh -QT -l800m -k1 -d <path to folder with .fq.gz files> subasp@upload.ncbi.nlm.nih.gov:uploads/<user@email.com_xxxxx>/project1
  
## step 4 add aspera uploaded data to a registered bioproject. this can be done though the ncbi website. 
https://submit.ncbi.nlm.nih.gov/subs/
  
## NB1: you can set a public release date for your data. i usually set it to 2 years in the future; and then change it to 'release now' once my manuscript is accepted.
  
## NB2: even if your data is not public, you can and should create a reviewer link to add to your manuscript when you submit it for review.
  
## NB3: I usually upload my raw sequencing data to ncbi sra and embargo it as soon as it comes hot off the illumina sequencer. this ensures that I have my raw data backed up in one other place.

### once your data is added to a bioproject, I do believe that it gets automatically deleted from the ncbi uploads folder, but don't quote me on this.

