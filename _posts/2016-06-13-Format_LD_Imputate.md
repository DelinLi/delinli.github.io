LD  Calculation:
  
		plink --file Raw.LMD60.plk  --mind 0.5 --geno 0.3 --recode  --out  LMD30Ind50   --noweb --nonfounders
		plink --file LMD30Ind50 --r2 --ld-window-kb 1000 --ld-window-r2 0 --inter-chr --out  LD   --noweb  --allow-no-sex  --freq --geno 0.1  --nonfounders


Hapmap to VCF:     
		
		~/softwares/tasseladmin-tassel-5-standalone-168dac0ed0ac/run_pipeline.pl  -Xmx5g -fork1 -h V534.unimputed.MAF5.Here20.LMD60.txt  -export V534.imputed.MAF5.Here20.LMD60 -exportType VCF -runfork1
 
Imputation:    
		
		java -Xmx32g -jar ~/softwares/beagle.03May16.862.jar gt=V534.imputed.MAF5.Here20.LMD60.vcf out=V534.imputed.MAF5.Here20.LMD60.beagle.vcf   nthreads=20 

VCF to Hapmap: 
		
		~/softwares/tasseladmin-tassel-5-standalone-168dac0ed0ac/run_pipeline.pl  -Xmx5g -fork1 -VCF V534.imputed.MAF5.Here20.LMD60.beagle.vcf.vcf  -export V534.imputed.MAF5.Here20.LMD60.beagle  -exportType Hapmap -runfork1
 
