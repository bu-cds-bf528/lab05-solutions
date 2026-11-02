# Lab 5 - Sequencing Quality Control: Worksheet

**Group members:**

- _____________________
- _____________________
- _____________________
- _____________________

---

## Part 1: Discussion

Rank the 8 items below from **most concerning (1)** to **least concerning (8)** for a 2x100nt paired-end Illumina mRNA-seq experiment. For each, give a one-sentence rationale for its placement.

| Rank | Item | Rationale |
|------|------|-----------|
|      | Unequal read lengths | |
|      | Average PHRED score <20 in the last 10 bases | |
|      | 15% of reads have identical sequence | |
|      | 50% of reads are multimapped after alignment to the reference | |
|      | 10% of reads are unmapped after alignment to the reference | |
|      | Non-random nucleotide distribution in the first 6 bases | |
|      | Nucleotide frequencies of A, C, G, T are not equal over the entire read | |
|      | Unequal number of forward and reverse reads | |

---

## Part 2: Match Six Cases to Six Situations

For each case, cite **at least 2-3 specific statistics/metrics per output** (FastQC, STAR, RSeQC), write a short paragraph interpreting what they mean about the experiment, and match the case to one of the six situations below. 

The cited metrics / statistics can include any potential issues as well as metrics that
indiciate high quality data. 

List at least one follow-up analysis that would confirm the match, make a recommendation about whether you would proceed with further analysis, and note how you would theoretically mitigate the problem (if one exists, or explain why none is needed).

**Situations:**

1. Validated human mRNAseq reads with adapter contamination aligned to the human genome
2. Validated human mRNAseq reads with incomplete gDNA depletion aligned to the human genome
3. Validated human mRNAseq reads with bacterial (Pseudomonas Aeruginosa) contamination aligned to the human genome
4. Validated human mRNAseq reads with human rRNA contamination aligned to the human genome
5. Validated human mRNAseq reads aligned to the mouse genome
6. Validated human mRNAseq reads aligned to the human genome

### Case A

**FastQC statistics cited:**

1.
2.
3.

**STAR statistics cited:**

1.
2.
3.

**RSeQC statistics cited:**

1.
2.
3.

**Interpretation:**




**Matched situation (1-6):** ___________

**Rationale for match:**




**Suggested follow-up to confirm this is the stated situation:**




**Recommendation** (proceed / do not proceed with further analysis) **and why:**




**Theoretical mitigation** (how would you address this problem if one exists, or explain why none is needed):




---

### Case B

**FastQC statistics cited:**

1.
2.
3.

**STAR statistics cited:**

1.
2.
3.

**RSeQC statistics cited:**

1.
2.
3.

**Interpretation:**




**Matched situation (1-6):** ___________

**Rationale for match:**




**Suggested follow-up to confirm this is the stated situation:**




**Recommendation** (proceed / do not proceed with further analysis) **and why:**




**Theoretical mitigation** (how would you address this problem if one exists, or explain why none is needed):




---

### Case C

**FastQC statistics cited:**

1.
2.
3.

**STAR statistics cited:**

1.
2.
3.

**RSeQC statistics cited:**

1.
2.
3.

**Interpretation:**




**Matched situation (1-6):** ___________

**Rationale for match:**




**Suggested follow-up to confirm this is the stated situation:**




**Recommendation** (proceed / do not proceed with further analysis) **and why:**




**Theoretical mitigation** (how would you address this problem if one exists, or explain why none is needed):




---

### Case D

**FastQC statistics cited:**

1.
2.
3.

**STAR statistics cited:**

1.
2.
3.

**RSeQC statistics cited:**

1.
2.
3.

**Interpretation:**




**Matched situation (1-6):** ___________

**Rationale for match:**




**Suggested follow-up to confirm this is the stated situation:**




**Recommendation** (proceed / do not proceed with further analysis) **and why:**




**Theoretical mitigation** (how would you address this problem if one exists, or explain why none is needed):




---

### Case E

**FastQC statistics cited:**

1.
2.
3.

**STAR statistics cited:**

1.
2.
3.

**RSeQC statistics cited:**

1.
2.
3.

**Interpretation:**




**Matched situation (1-6):** ___________

**Rationale for match:**




**Suggested follow-up to confirm this is the stated situation:**




**Recommendation** (proceed / do not proceed with further analysis) **and why:**




**Theoretical mitigation** (how would you address this problem if one exists, or explain why none is needed):




---

### Case F

**FastQC statistics cited:**

1.
2.
3.

**STAR statistics cited:**

1.
2.
3.

**RSeQC statistics cited:**

1.
2.
3.

**Interpretation:**




**Matched situation (1-6):** ___________

**Rationale for match:**




**Suggested follow-up to confirm this is the stated situation:**




**Recommendation** (proceed / do not proceed with further analysis) **and why:**




**Theoretical mitigation** (how would you address this problem if one exists, or explain why none is needed):




---

## Summary

Complete the matching below — each situation should be used exactly once.

| Case | Matched Situation (1-6) |
|------|--------------------------|
| A    |                          |
| B    |                          |
| C    |                          |
| D    |                          |
| E    |                          |
| F    |                          |

**Which case matches Situation 6 (reads aligned to the human genome with no contamination or reference mismatch)?** ___________

**Why, compared to the other five cases?**


