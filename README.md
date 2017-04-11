# NovelVirusSeq
Scans ngs fasta sequences for putative viruses - uses prokka, blast, and hhpred to predict ORFs and gene products

# Virus_annotate
Searches a file with many fastas for ORFs and does gene prediction here - basically prokka in batch mode that automatically will blast and HHPRED every single predicted viral gene. Requires prokka (in -c mode) and BLAST+ and HHPRED

# Installation - Virus_annotate

1. You'll need to set the path to the HHPRED database as well as blast and prokka
2. Make two direcotries in the folder that you'll be running from called 'prokka_output' and 'temp_contig_dir'

# Usage - Virus_annotate
To annotate a scaffold simply call 'python virus-annotate 'scaffold-path' 'minimum base cutoff' 'choose a name' 
You can also call it with the -h option to get a not very detailed description of these arguments.

If minimum base cutoff is passed a zero the program will take a pre assembled segmented genome and attempt to annotate and send it to tbl2asn

This generates a folder with the name 'choose a name'
Inside the folder will be all of the different contigs that were over the minimum base cutoff
Inside each of these folders will be the output of tbl2asn as well as an hhpred and blastp result for any ORF that prokka couldn't figure out

You would then have to go through and use your human brain to look at the results and figure if you want to rename anything.
After manually doing this you would have to run tbl2asn again yourself, although I'm going to at some point cook up a quick script to do this automatically.
