# Lab 5 - Sequencing Quality Control

**Estimated time:** ~90 minutes total (Part 1: ~30 minutes discussion; Part 2:
remaining time for case analysis)

## Part 1 (AIAS Level 1 - No AI)

### Instructions

Please make small groups of 3-4 with your peers around you and discuss the
following question:

Assume you were given 2x100nt paired-end Illumina sequencing from an mRNA-seq
experiment, rank the following from most concerning to least concerning:

1. Unequal read lengths
2. Average PHRED score <20 in the last 10 bases
3. 15% of reads have identical sequence
4. 50% of reads are multimapped after alignment to the reference
5. 10% of reads are unmapped after alignment to the reference
6. Non-random nucleotide distribution in the first 6 bases
7. Nucleotide frequencies of A, C, G, T are not equal over the entire read
8. Unequal number of forward and reverse reads

Use [`worksheet_template.md`](worksheet_template.md) to record your group's
answers for both Part 1 and Part 2.

## Part 2 (AIAS Level 1 - No AI)

### Instructions

In real sequencing experiments, artifacts or issues often arise from
experimental protocols or methodological choices. Before you can be confident
in the biological analysis, it is critical to carefully evaluate the quality
of your sequencing experiment. This is typically done by inspecting the base
quality of the actual reads through a tool like FastQC as well as checking
certain key statistics like alignment rate to the target genome, and
distribution of reads across various features in the reference genome. Some
of these statistics and metrics have clear interpretations (base call
confidence, etc.) while some may show experiment-specific bias that is
expected and can be mitigated or ignored for most downstream purposes.

For the following activity, you have been provided the sequencing quality
control results from FastQC, the alignment rate statistics from STAR, and
statistics on read distribution from RSeQC for six different experiments
(Case A, Case B, Case C, Case D, Case E, Case F). Each case has its own directory
(`case_A/` through `case_F/`), containing `fastqc/`, `star/`, and `rseqc/`
subdirectories with the raw tool output, plus a combined `multiqc_report.html`
summarizing all three.

The `all_multiqc_report.html` summarizes and compares the same modules and
stats across all the cases.

### wgs_reference

I included the same QC info for actual whole genome sequencing data aligned
using the same pipeline. Please note that you would almost certainly not
want to use STAR to align WGS data since STAR is **expecting** reads to be
spliced and we do not have that expectation with WGS data. In a real WGS experiment,
you would simply align your reads with a general-purpose sequence aligner (bowtie2, bwa, etc.)

This example is included so you can get a sense for what characteristics shift based on
what population of sequences you are assaying. STAR was used intentionally just
to illustrate the differences in QC metrics between RNA-seq and WGS data. You can 
view this as an extreme example of the situation where reads generated from gDNA were
processed in a RNAseq pipeline using a splice-aware aligner with the only difference being
that in this case, every single read originated from a WGS experiment. It's also a reminder to use
the appropriate tools for the experiment: a splice-aware alignment tool for RNAseq and a
general alignment algorithm for WGS. 

You can see that as we expected, there are zero annotated splice events. You'll also
notice that there is a generally high overall alignment rate, but the
distribution of features is far more weighted towards intronic regions. Take note also
of the GC content distribution as well as the sequence duplication levels and how they
are different from the mRNAseq experiments. 

**Guiding Questions:**

#### FastQC

- For poly-A selected mRNA-seq, what pattern would you expect in the first
  several bases of each read, and would that pattern actually make a
  module fail?

#### STAR

- What alignment rate would you consider normal for a well-prepped
  mRNA-seq library against the correct reference, and what would make
  that rate drop sharply?
- Look at the uniquely mapped, multi-mapped, and unmapped percentages
  together. How might these categories connect back to what you saw in
  FastQC (e.g., duplication levels, overrepresented sequences)?

#### RSeQC

- For poly-A mRNA-seq, which genomic regions (CDS exons, UTRs, introns,
  intergenic) do you expect most reads to fall into, and why?

#### Putting It Together

- In general, all of these cases are known potential situations where
  issues occurred either during sample preparation in the lab, quality
  control of the reads, or alignment to the reference.
- Try to match each case to one of the six situations described below,
  then compare its specific statistics and metrics to the other cases to
  confirm the match.

**Assumptions:**

- The data is derived from a real mRNA-seq experiment with poly-A selected,
  100bp paired-end reads.
- One case represents an experiment with high-quality reads and successful
  alignment to the reference genome.

In your same groups, for each case, please comment on the output of each
report by specifically citing at least 2-3 statistics / metrics per output
(FastQC, STAR, RSeQC), and a short paragraph explaining what this means
about the success of the underlying experiment. When you have completed this,
please try to match every case with the situation that generated it, listed
below. List at least one follow-up analysis you would do to confirm that
this is the stated situation. Finally, make a recommendation about whether
you will proceed with further analysis and why. Note that this should include
how you would *theoretically* mitigate the problem if one exists or if you even
need to.

**Situations:**

1. Validated human mRNAseq reads with adapter contamination aligned to the human genome
2. Validated human mRNAseq reads with incomplete gDNA contamination aligned to the human genome
3. Validated human mRNAseq reads aligned to the mouse genome
4. Validated human mRNAseq reads with human rRNA contamination aligned to the human genome
5. Validated human mRNAseq reads with bacterial (Pseudomonas Aeruginosa) contamination aligned to the human genome
6. Validated human mRNAseq reads aligned to the human genome

Use [`worksheet_template.md`](worksheet_template.md) to record your group's
answers for both Part 1 and Part 2.

## AI Use Policy

AI Level 1 (No AI) was chosen for this lab because these judgments remain
the domain of the individual. As a scientist, you are ultimately
responsible for ensuring your results are sound before submitting them for
publication. If you publish data based on wrong conclusions made by an
LLM, the ultimate responsibility is still yours. This lab is meant to help
you exercise and develop your skills in evaluating sequencing quality
control data, and to give you confidence in justifying your decisions
based on your evaluation of multiple metrics.

## AI Use Disclosure (Course Materials)

This README was developed with AI assistance from Claude Sonnet 5, used to
edit existing text for clarity and organization and to suggest the draft
learning objectives above. The accompanying
[`worksheet_template.md`](worksheet_template.md) was fully AI-generated: it is
a fixed fill-in-the-blank template (headings, prompts, and blank fields)
mechanically derived from this README's own Task section and each objective's
inline Criteria, not original narrative or graded content.

The analysis code used to produce this lab's case data was generated with
Claude using a behavior-driven design (BDD) workflow — behavior/test
specifications were written first, then Claude generated implementation code
to satisfy them — and was manually reviewed and tested by the instructor
before use.

All experimental case data and the original lab narrative text were authored
manually by the instructor. AI was used to generate analysis code (via the BDD
workflow above) and the structural worksheet template; it was not used to
generate case data or original narrative content. AI's other role was limited
to editorial revision of existing text and suggesting candidate learning
objectives, both critically reviewed, edited, and validated by the instructor
before inclusion.

**Boundary:** AI was not used to generate case data or grading criteria, and
is not used to evaluate or grade student submissions for this lab. All
AI-generated code was manually reviewed and tested by the instructor before
use.

The instructor reviewed, edited, and takes full responsibility for all
content in this document.
