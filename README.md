# taxon-utils: utils for taxonomy manipulation

### interface

    $ taxon-utils

    Usage:   taxon-utils <command> <arguments>
    Version: 0.0.1-r1

    Command:
          translate   translate the taxon_id map to lineage.
          lineage     translate the taxon_id map to full lineage.
          name        translate the taxon_id map to name.
          lca         perform lca for given taxon match per query.
          bin         bin reads for specify level. default: [species] .
          clade       get clade taxon id from NCBI taxonomy tree.
          filter      filter the entries with specified taxonIds.

    Licenced:
    (c) 2018-2020 - LEI ZHANG
    Logic Informatics Co.,Ltd.
    zhanglei@logicinformatics.com

## species_assign

Example:

    wget https://zenodo.org/record/824551/files/silva_species_assignment_v128.fa.gz
    gunzip silva_species_assignment_v128.fa.gz
    grep ">" silva_species_assignment_v128.fa | sed 's/>//' | cut -f1,2,3 -d ' ' >silva_species_assignment_v128.map

    bowtie  -f -v 0 -a silva_species_assignment_v128 example_seqs.fa 2>/dev/null | species_assign  silva_species_assignment_v128.map
 