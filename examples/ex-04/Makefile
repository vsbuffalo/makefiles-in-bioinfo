REF = ref.fa
IN_FILE = sample.fq

all: $(patsubst %.fq, %.vcf, $(IN_FILE))

# since indexing the genome with bwa index does create files, this
# could be those files, but I'm keeping it simple
.PHONY: index clean

index:
	bwa index -a is $(REF)

# don't use this in real life, just a *toy* example!
%.vcf: %.fq $(REF)
	bwa mem $(REF) $< | samtools view -Sb - | samtools mpileup -uf $(REF) - | bcftools view - > $@

clean:
	rm -f *.vcf

clean-index:
	# be careful with clean
	rm -f $(REF).*


# there's a bug here, can you find it?
