seqlens.txt: input.fa
	bioawk -cfastx '{print $$name"\t"length($$seq)}' input.fa > seqlens.txt
