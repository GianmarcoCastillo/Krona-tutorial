# Krona-tutorial
Krona Tutorial install
# Krona ejecutable install
## Step 1
mkdir taxonomy

wget -c ftp://ftp.ncbi.nih.gov/pub/taxonomy/taxdump.tar.gz

wget -c ftp://ftp.ncbi.nih.gov/pub/taxonomy/accesion2taxid/dead_prot.accesion2taxid.gz

wget -c ftp://ftp.ncbi.nih.gov/pub/taxonomy/accesion2taxid/dead_wgs.accession2taxid.gz

wget -c ftp://ftp.ncbi.nih.gov/pub/taxonomy/accesion2taxid/nucl_gb.accession2taxid.gz

wget -c ftp://ftp.ncbi.nih.gov/pub/taxonomy/accesion2taxid/nucl_wgs.accession2taxid.gz

wget -c ftp://ftp.ncbi.nih.gov/pub/taxonomy/accesion2taxid/prot.accession2taxid.gz

wget -c ftp://ftp.ncbi.nih.gov/pub/taxonomy/accesion2taxid/dead_nucl.accession2taxid.gz

mkdir taxonomy/accession2taxid
mv taxonomy/*accession*.gz accession2taxid
mv taxdump.tar.gz taxonomy

## Step 2 - Run the update files
wget https://github.com/marbl/Krona/releases/download/v2.8.1/KronaTools-2.8.1.tar

tar xvf KronaTools-2.8.1.tar

cd KronaTools-2.8.1

perl install.pl --prefix /media/mordor/gianmarco/apps/krona/KronaTools-2.8.1  ## Install krona PATH!!

./updateTaxonomy.sh --only-build     ## Install database Taxonomy

./updateAccessions.sh --only-build       ## Install Accession

