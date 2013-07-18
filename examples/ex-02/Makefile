SEQ_FILE_1 = in-1.fq
SEQ_FILE_2 = in-2.fq
ADAPTER_FILE = adapters.fa

SEQ_FILE_TRIM_1 = in-trimmed-1.fq
SEQ_FILE_TRIM_2 = in-trimmed-2.fq

# Files we want out:
all: $(SEQ_FILE_TRIM_1) $(SEQ_FILE_TRIM_2)

$(SEQ_FILE_TRIM_1): $(SEQ_FILE_1) $(ADAPTER_FILE)
	scythe -a $(ADAPTER_FILE) -p 0.3 $< 2> scythe-1.stats | seqtk trimfq - > $@

$(SEQ_FILE_TRIM_2): $(SEQ_FILE_2) $(ADAPTER_FILE)
	scythe -a $(ADAPTER_FILE) -p 0.3 $< 2> scythe-2.stats | seqtk trimfq - > $@

clean:
	rm -f $(SEQ_FILE_1) $(SEQ_FILE_2)
