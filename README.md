# SVcnn
## Introduction

Structural variations (SVs) are variations with a length greater than 50bp in an organism's chromosome structure. They play important roles in genetic diseases and evolution mechanisms. With the development of long-read sequencing technology, there are so many SV caller methods based on long-read developed by researchers, but their performance results are not good enough. We observe that current SV callers miss a lot of true SVs and call a lot of false SVs in repetitive regions and in regions with multi-allelic SVs. Hence, we propose a new method-SVcnn, a more accurate deep learning-based method for detecting SVs by using long-read sequencing data. Compared with current SV callers, SVcnn has better performance.

---
## Installation
```
git clone https://github.com/nwpuzhengyan/SVcnn.git
```
---
## Dependence
    1. python3
	2. pysam
	3. cigar
	4. numpy
	5. pyfaidx
	6. copy
	7. time
	8. argparse
	9. PIL
	10. pytorch
	11. torchvision
	12. os
	
---
## Running
The sorted bam files from NGMLR, Minimap and Minimap2 are all be used as input sorted bam. The input reference.fa and reference.fa of bam file must be the same one.
```
cd dist
SVcnn <input sorted bam> <input reference.fa>	
```
---
## Convert SV region into image
SVcnn can convert SV regionS into images and store the images in this folder SV_into_image. If users want to check the converted images, they can look for them in folder SV_into_image. The name of each image consists of the chromosome name and SV start and end position.
---
## Output format
The output format is as follows. CHROM is chromosome name. POS is the SV start position. ID is the SV name. REF is the reference sequence and ALT is the alternate sequence. QUAL is the quality of SV and FILTER means filter status. INFO is the basic information of SV.
```
#CHROM	POS	ID	REF	ALT	QUAL	FILTER	INFO
chr1	10780	SVcnn.INS.1	G	GAACACATGCTAGCGCGTCCGGGGGTGGAGGCGATAGCGCAGGCGCAGAGAGCGCCGCGCC	.	PASS	SVTYPE=INS;SVLEN=61;END=10780;RNAMES=NULL
chr1	30893	SVcnn.DEL.1	catttctctctatctcatttctctctctctcgctatct	c	.	PASS	SVTYPE=DEL;SVLEN=-37;END=30930;RNAMES=NULL
```
---
## Contact
For advising, bug reporting and requiring help, please contact yan.zheng@nwpu-bioinformatics.com.
