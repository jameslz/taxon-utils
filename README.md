# taxon-utils
taxon-utils: utils for NCBI taxonomy manipulation

## species_assign

Example:

    wget https://zenodo.org/record/824551/files/silva_species_assignment_v128.fa.gz
    gunzip silva_species_assignment_v128.fa.gz
    grep ">" silva_species_assignment_v128.fa | sed 's/>//' | cut -f1,2,3 -d ' ' >silva_species_assignment_v128.map

    bowtie  -f -v 0 -a silva_species_assignment_v128 example_seqs.fa 2>/dev/null | species_assign  silva_species_assignment_v128.map
 
