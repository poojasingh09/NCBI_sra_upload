# NCBI_sra_upload
# pooja.singh09@gmail.com
# this repo has instructions on how to upload raw sequencing reads to the NCBI SRA from a linux server.

## step 1 make an account with ncbi and register a bioproject and biosamples. I usually create one bioproject per manuscript
https://www.ncbi.nlm.nih.gov/sra/docs/submitbio/

## step 2 install command-line aspera on your server to facilate data upload. It is much faster than ftp or any other option. Make sure you download a key.
https://www.ncbi.nlm.nih.gov/sra/docs/submitfiles/

## step 3 upload your data to ncbi SRA. Make sure you name a new destination subdirectory every time you upload data for a new project. Having zipped fastq files makes life easier too (gzip *.fq)

/.aspera/connect/bin/ascp -i aspera.openssh -QT -l800m -k1 -d <path to folder with .fq.gz files> subasp@upload.ncbi.nlm.nih.gov:uploads/<user@email.com_xxxxx>/project1
  
## step 4 add aspera uploaded data to a registered bioproject. this can be done though the ncbi website. 
https://submit.ncbi.nlm.nih.gov/subs/

  
### once your data is added to a bioproject, I do believe that it gets automatically deleted from the ncbi uploads folder, but dont quote me on this.

