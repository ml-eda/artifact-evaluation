# Artifact evaluation

This document provides the guidelines for evaluating artifacts at the ACM/IEEE International Symposium on Machine Learning for CAD based on the [ACM artifact review and badging policies](https://www.acm.org/publications/policies/artifact-review-and-badging-current). This artifact evaluation repository is derived and inspired by the [artifact evaluation standards](https://github.com/mlcommons/ck/tree/master/docs/artifact-evaluation) set by the MLCommons. 

## Overview

Shortly after the artifact submission deadline, the AE committee members 
will bid on artifacts they would like to evaluate based on their competencies 
and the information provided in the artifact abstract such as software and hardware dependencies
while avoiding possible conflicts of interest.

Within a few days, the AE chair will make the final selection of evaluators
to ensure at least two or more evaluators per artifact.

Evaluators will then have approximately 2 weeks to review artifacts submitted via TBD,
discuss with the authors about all encountered issues and help them fix all the issues.
Remember that our philosophy of artifact evaluation is not to fail problematic artifacts 
but to help the authors improve their public artifacts, pass the evaluation
and strengthen their Artifact Appendix.

In the end, the AE commitee and chairs will decide on a set of standard ACM reproducibility badges (see below)
to award to a given artifact based on all reviews and the authors' responses.
Such badges will be printed on the 1st page of the paper and will be available 
as meta information in the [ACM Digital Library](https://dl.acm.org)

Authors and reviewers are encouraged to check the [AE FAQ](faq.md)
and contact chairs and the community via  TBD
in case of questions or suggestions.


## ACM reproducibility badges

Reviewers must read the paper and then thoroughly go through the Artifact Appendix 
to evaluate shared artifacts. They should then describe their experience 
at each stage (success or failure, encountered problems and how they were possibly solved, 
and questions or suggestions to the authors), and give a score on scale -1 .. +1:

- *+1* if exceeded expectations
- *0* if met expectations (or inapplicable)
- *-1* if fell below expectations

### Artifacts available badge

![](https://www.acm.org/binaries/content/gallery/acm/publications/replication-badges/artifacts_available_dl.jpg)

The author-created artifacts relevant to this paper will receive an ACM "artifact available" badge 
**only if** they have been placed on a publicly accessible archival repository
such as [Zenodo](https://zenodo.org), [FigShare](https://figshare.com),
and [Dryad](http://datadryad.org).

A DOI will be then assigned to their artifacts and must be provided in the Artifact Appendix!

*Notes:*

* ACM does not mandate the use of above repositories. However, publisher repositories,
  institutional repositories, or open commercial repositories are acceptable
  **only** if they have a declared plan to enable permanent accessibility!
  **Personal web pages, GitHub, GitLab and BitBucket are not acceptable for this purpose.**
* Artifacts do not need to have been formally evaluated in order for an article
  to receive this badge. In addition, they need not be complete in the sense
  described above. They simply need to be relevant to the study and add value
  beyond the text in the article. Such artifacts could be something as simple
  as the data from which the figures are drawn, or as complex as a complete
  software system under study.
* The authors can provide the DOI at the very end of the AE process 
  and use GitHub or any other convenient way to access their artifacts 
  during AE.

#### ML-EDA-specific additional review criteria:

* Are all artifacts related to this paper publicly available?
  

### Artifacts functional badge

![](https://www.acm.org/binaries/content/gallery/acm/publications/replication-badges/artifacts_evaluated_functional_dl.jpg)
This badge is applied to papers whose associated artifacts have completed an independent audit. Artifacts need not be made publicly available to be considered for this badge. However, they do need to be made available to reviewers. 

The artifacts associated with the research are found to be documented, consistent, complete, exercisable, and include appropriate evidence of verification and validation.

* Documented: At a minimum, an inventory of artifacts is included, and sufficient description is provided to enable the artifacts to be exercised.

* Consistent: The artifacts are relevant to the associated paper, and contribute in some inherent way to the generation of its main results.

* Complete: To the extent possible, all components relevant to the paper in question are included. (Proprietary artifacts need not be included. If they are required to exercise the package then this should be documented, along with instructions on how to obtain them. Proxies for proprietary data should be included so as to demonstrate the analysis.)

* Exercisable: Included scripts and/or software used to generate the results in the associated paper can be successfully executed, and included data can be accessed and appropriately manipulated.

#### ML-EDA-specific review criteria

* Are all components relevant to evaluation included in the package?
* Data and benchmarks used for the paper must be available in the artifact. If they are proprietary, suitable proxies must be provided that demonstrate the key findings of the papers. For example, if the paper leverages industry testcases (proprietary designs or PDKs), the same methodology must be shown on some non-proprietary testcases made available to the reviewers.
* If proprietary tools (e.g., commercial EDA tools) are required, the artifact must contain documentation (name of the tool, version) and scripts (e.g., commercial tool TCL) to obtain it. Alternatively, the paper can demonstrate its key takeaways and findings using proxy/non-proprietary tools.
* The evaluation will consider the practicality of validating the results given the limitations in computing and time.  For example, the artifact can include training scripts that begin on a pretrained model or provide scripts for pretrained models to perform inference.
* Reviewers should report any unexpected artifact behavior to the authors (depending on the type of artifact, such as unexpected output, scalability issues, crashes, performance variation, etc).
  

### Results reproduced

![](https://www.acm.org/binaries/content/gallery/acm/publications/replication-badges/results_reproduced_dl.jpg)

The artifacts associated with the paper will receive a "Results reproduced" badge *only if* the key results 
of the paper have been obtained in a subsequent study by a person or team other than the authors, using 
artifacts provided by the author. Some variation of empirical and numerical results is tolerated.

For this badge, a peer-reviewed publication which reports the replication or reproduction must be submitted as evidence, and if awarded, the badge will contain a link to this paper.


#### ML-EDA-specific Review Criteria
MLCAD2024 is NOT awarding this badge. MLCAD will consider awarding this in the future as this requires a separate peer evaluation process and is after the publication of the paper. 


## Distinguished artifact award for open-source artifacts

MLCAD2024 will provide a distinguished artifact award for being completely open-source, functional, well-documented, portable, and easily usable by the community.

----
