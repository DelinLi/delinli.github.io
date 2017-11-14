### Local BLAST

#### Step I. Build the database    
	makeblastdb -in db.fasta -dbtype prot/nucl -parse_seqids -out dbname


#### Step II. BLAST (N/P/X...)    
	blastn  -query seq.fasta -out seq.blast -db GL -outfmt 6 -evalue 1e-10 -max_target_seqs 2 -num_threads 1
