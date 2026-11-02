# Identity of Cases

## Case A

Validated human reads from a successful RNA-seq experiment, aligned against the human reference.

### Expectations

- FastQC should look largely normal, apart from possible per-base sequence content bias (from random hexamer priming).
- Alignment rate should be high (80% or more).

## Case B

Validated human reads from a successful RNA-seq experiment, aligned against the mouse reference.

### Expectations

- FastQC should look largely normal, apart from possible per-base sequence content bias (from random hexamer priming).
- This was the same set of reads aligned in Case A, so the sequence quality metrics are in fact identical.
- Alignment rate should be quite low.

## Case C

Validated human reads with spiked-in adapter contamination, aligned against the human reference.

### Expectations

- FastQC should look largely normal, apart from possible per-base sequence content bias (from random hexamer priming).
- FastQC may also flag the Adapter Content, per-sequence bias, or Overrepresented Sequences modules.
- Alignment rate should remain fairly high, since STAR soft-clips adapters. It may be slightly lower if clipping drops some reads' aligned length below the minimum threshold.
- The FastQC module itself will directly identify the adapter contamination

## Case D

Validated human reads with spiked-in *Pseudomonas aeruginosa* contamination, aligned against the human reference.

### Expectations

- FastQC will likely show a bimodal per-sequence GC content distribution, and may also flag sequence duplication or per-base sequence content.
- Alignment rate should drop substantially, with most of the lost reads reported as unmapped.

## Case E

Validated human reads with spiked-in human rRNA contamination, aligned against the human reference.

### Expectations

- FastQC may flag GC content, sequence duplication, or per-base sequence content.
- Uniquely mapped rate should drop substantially, with many reads now reported as multimapped.
- RSeQC read distribution may also show an unusual intronic /intergenic fraction.

## Case F

Validated human reads with spiked-in human WGS reads (to simulate gDNA contamination), aligned against the human reference.

### Expectations

- QC metrics should look almost entirely normal, apart from an increase in the intronic / intergenic fraction in RSeQC read distribution.
