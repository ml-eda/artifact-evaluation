# Artifact evaluation

This document provides the guidelines for evaluating artifacts at the ACM/IEEE International Symposium on Machine Learning for CAD based on the [ACM artifact review and badging policies](https://www.acm.org/publications/policies/artifact-review-and-badging-current). This artifact evaluation repository is derived and inspired by the [artifact evaluation standards](https://github.com/mlcommons/ck/tree/master/docs/artifact-evaluation) set by the MLCommons.

## Overview

Shortly after the artifact submission deadline, the AE committee members
will bid on artifacts they would like to evaluate based on their competencies
and the information provided in the artifact abstract such as software and hardware dependencies
while avoiding possible conflicts of interest.

Within a few days, the AE chair will make the final selection of evaluators
to ensure at least two or more evaluators per artifact.

Evaluators will then have approximately 2 weeks to review artifacts submitted via the AE submission site,
discuss with the authors about all encountered issues and help them fix all the issues.
Remember that our philosophy of artifact evaluation is not to fail problematic artifacts
but to help the authors improve their public artifacts, pass the evaluation
and strengthen their Artifact Appendix.

In the end, the AE committee and chairs will decide on a set of ACM artifact badges (see below)
to award to a given artifact based on all reviews and the authors' responses.
Such badges will be printed on the 1st page of the paper and will be available
as meta information in the [ACM Digital Library](https://dl.acm.org).

Authors and reviewers are encouraged to check the [AE FAQ](faq.md)
and contact chairs and the community via the contact information provided by the AE chairs
in case of questions or suggestions.


## ACM artifact badges

The ACM artifact badging framework includes Artifacts Available, Artifacts Evaluated - Functional, and Results Reproduced.
MLCAD 2026 will award only the following ACM artifact badges:

* Artifacts Available
* Artifacts Evaluated - Functional

MLCAD 2026 will not award a Results Reproduced / Reproducible badge. Reviewers should not recommend or imply that this badge is available for this cycle.

Reviewers must read the paper and then thoroughly go through the Artifact Appendix
to evaluate shared artifacts. They should then describe their experience
at each stage (success or failure, encountered problems and how they were possibly solved,
and questions or suggestions to the authors), and give a score on a scale from -1 to +1:

- *+1* if exceeded expectations
- *0* if met expectations (or inapplicable)
- *-1* if fell below expectations

### Artifacts available badge

![](https://www.acm.org/binaries/content/gallery/acm/publications/replication-badges/artifacts_available_dl.jpg)

The author-created artifacts relevant to this paper will receive an ACM "artifact available" badge
**only if** they have been archived on [Zenodo](https://zenodo.org)
and the Zenodo DOI is provided in the Artifact Appendix.

For MLCAD 2026, the Zenodo record may archive a snapshot of the authors' GitHub repository. GitHub alone is not sufficient for this badge because it does not provide the required Zenodo DOI.

*Notes:*

* MLCAD 2026 requires Zenodo for the Artifacts Available badge. Personal web pages, GitHub, GitLab, BitBucket, Google Drive, and private review uploads are not sufficient for this purpose.
* Artifacts do not need to have been formally evaluated in order for an article
  to receive this badge. In addition, they need not be complete in the sense
  described above. They simply need to be relevant to the study and add value
  beyond the text in the article. Such artifacts could be something as simple
  as the data from which the figures are drawn, or as complex as a complete
  software system under study.
* The authors can provide the Zenodo DOI at the very end of the AE process
  and use GitHub or any other convenient way to access their artifacts
  during AE.

#### MLCAD-specific additional review criteria:

* Are all artifacts related to this paper publicly available?
* Are licenses and redistribution restrictions documented?
* Commercial EDA tools, licensed binaries, and commercial/foundry PDKs that cannot be publicly redistributed do not themselves count as publicly available artifacts. Authors should document these dependencies separately and, when possible, provide public scripts, open proxies, logs, reports, or other evidence.


### Artifacts functional badge

![](https://www.acm.org/binaries/content/gallery/acm/publications/replication-badges/artifacts_evaluated_functional_dl.jpg)

This badge is applied to papers whose associated artifacts have completed an independent audit. Artifacts need not be made publicly available to be considered for this badge. However, they do need to be made available to reviewers.

The artifacts associated with the research are found to be documented, consistent, complete, exercisable, and include appropriate evidence of verification and validation.

* Documented: At a minimum, an inventory of artifacts is included, and sufficient description is provided to enable the artifacts to be exercised.

* Consistent: The artifacts are relevant to the associated paper, and contribute in some inherent way to the generation of its main results.

* Complete: To the extent possible, all components relevant to the paper in question are included. (Proprietary artifacts need not be included. If they are required to exercise the package then this should be documented, along with instructions on how to obtain them. Proxies for proprietary data should be included so as to demonstrate the analysis.)

* Exercisable: Included scripts and/or software used to generate the results in the associated paper can be successfully executed, and included data can be accessed and appropriately manipulated.

For MLCAD 2026, Functional evaluation means that reviewers can exercise or validate the artifact and obtain similar results within the authors' declared tolerance. It does not require bit-for-bit or text-identical reproduction unless exact output is the paper's claim.

Authors should declare how Functional evaluation should be performed for each key result. Reviewers should check that the submission identifies:

* the key result or claim being evaluated,
* the command, script, notebook, or workflow reviewers should run,
* the expected output, report, metric, or qualitative behavior,
* the acceptable tolerance or similar-result criterion,
* the validation path: full rerun, bounded subset rerun, cached-output validation, or evidence/log inspection,
* any required compute, model, API, commercial-tool, or PDK access,
* approximate runtime and disk usage.

#### MLCAD-specific review criteria

* Are all components relevant to evaluation included in the package?
* Data and benchmarks used for the paper must be available in the artifact. If they are proprietary, suitable proxies must be provided that demonstrate the key findings of the paper. For example, if the paper leverages industry testcases (proprietary designs or PDKs), the same methodology must be shown on some non-proprietary testcases made available to the reviewers.
* If proprietary tools (e.g., commercial EDA tools) are required, the artifact must document the tool name and version and provide scripts used to run the tool flow, such as commercial-tool TCL scripts. Alternatively, the paper can demonstrate its key takeaways and findings using proxy/non-proprietary tools.
* The evaluation will consider the practicality of validating the results given the limitations in computing and time. For example, the artifact can include training scripts that begin on a pretrained model or provide scripts for pretrained models to perform inference.
* Reviewers should report any unexpected artifact behavior to the authors (depending on the type of artifact, such as unexpected output, scalability issues, crashes, performance variation, etc).

For commercial EDA tools, commercial/foundry PDKs, proprietary IP, or licensed technology files, reviewers should check that the authors provide enough information for a reviewer who already has access to install, configure, and validate the flow. The submission should include:

* exact tool vendor, product name, version, build number, supported operating system, and required license features,
* license-server assumptions, environment variables, setup files, and module commands,
* required PDK or technology package, including foundry or source, process node, PDK name, release/version, and required subcomponents,
* required libraries and technology files, such as standard-cell libraries, SRAM or IP libraries, Liberty, LEF/DEF, GDS, SPICE, QRC, DRC/LVS decks, or technology files,
* expected directory layout, mount points, symbolic links, and environment variables for tools, PDKs, libraries, and generated outputs,
* all scripts and configuration files needed to run the flow, such as Makefiles, TCL scripts, Slurm scripts, YAML/JSON configs, and wrapper scripts,
* setup instructions, tool/license/PDK verification commands, a smoke-test command, the full evaluation command or reviewer subset command, and expected reports/logs/metrics/tolerances,
* whether an open-source proxy flow or open PDK is available when the commercial setup is not accessible.

Reviewers should not be expected to install unspecified packages manually during AE. A Docker image, Dockerfile, Apptainer/Singularity image, VM, locked Conda environment, or equivalent locked environment should be provided whenever practical. Large runnable artifacts such as Docker images may be submitted through the private upload location shared by the AE chairs.

#### Reviewer-side evaluation resources

AE chairs may provide reviewer-side resources when an artifact cannot reasonably be evaluated on a reviewer's own machine. Reviewers should use these resources only when they are assigned or approved by the AE chairs for a specific artifact.

* [NSF ACCESS](https://access-ci.org): reviewer-side compute resources for CPU/GPU jobs, large training or inference runs, and containerized or Slurm-based workflows. If an artifact is evaluated on ACCESS, reviewers should run the author's provided Docker/Apptainer image, locked environment, shell script, notebook, or Slurm script when possible. Reviewers should record the resource used, wall time, CPU/GPU configuration, job status, and any deviation from the author's declared runtime or Service Unit/GPU-hour estimate.
* [Chipshub platform via nanoHUB](https://nanohub.org/index.php?reset=1&option=com_users&view=login&return=L2dyb3Vwcy9jaGlwc2h1Yi9hYm91dA==): reviewer-side access path for commercial EDA tool evaluation when AE chairs confirm that the required tool, version, license, and any needed PDK or technology files are available. Chipshub is not an author submission requirement. Reviewers should use the author's scripts, tool-version requirements, PDK assumptions, and expected reports/logs/metrics to decide whether the commercial-tool flow can be exercised or validated.

If no open-source proxy or open PDK path is available, AE chairs may use Chipshub or NSF ACCESS resources when available. If the required commercial tool or PDK is still unavailable, reviewers should evaluate any runnable open subset and inspect the authors' captured evidence, such as logs, reports, QoR files, output databases, screenshots, or metric recomputation scripts. Reviewers should distinguish artifact defects from platform friction and escalate platform or account issues to the AE chairs rather than penalizing the authors for reviewer-side infrastructure problems.

#### LLM-specific review criteria

For LLM-based artifacts, reviewers should not require exact textual reproduction unless exact text is central to the paper's claim. LLMs can be stochastic, API models can change, and different serving backends may produce small output differences.

Reviewers should check whether the author provides:

* exact model information, including open-weight model revision/hash or closed API provider and model ID,
* inference settings such as temperature, top-p/top-k, maximum tokens, seed if supported, number of samples, stop sequences, and retry policy,
* prompts, prompt templates, few-shot examples, prompt-generation code, or generated prompt dumps,
* metric definitions, scoring scripts, raw outputs, expected values, and tolerance bands,
* API cost estimates or local GPU/runtime requirements,
* cached outputs when a full API rerun is expensive or API model drift is a concern,
* a declared validation path: full rerun, bounded subset rerun, cached-output validation, or evidence/log inspection.

The artifact should be flagged as a potential blocking issue if the model is ambiguous, prompts are missing, settings are incomplete, metrics cannot be recomputed, API cost is unbounded, or the claimed conclusion depends on cherry-picked outputs without a repeatable evaluation protocol.


### Results reproduced

![](https://www.acm.org/binaries/content/gallery/acm/publications/replication-badges/results_reproduced_dl.jpg)

Under the ACM artifact badging framework, the artifacts associated with the paper receive a "Results Reproduced" badge only if the key results of the paper have been obtained in a subsequent study by a person or team other than the authors, using artifacts provided by the authors. Some variation of empirical and numerical results is tolerated.

For this badge, a peer-reviewed publication that reports the replication or reproduction must be submitted as evidence, and if awarded, the badge contains a link to this paper.

#### MLCAD-specific review criteria

MLCAD 2026 will not award a Results Reproduced / Reproducible badge. Reviewers should not evaluate artifacts for this badge, request additional evidence for this badge, or imply that this badge is available in the MLCAD 2026 AE cycle.


## Distinguished artifact award for open-source artifacts

MLCAD may provide a distinguished artifact award for being completely open-source, functional, well-documented, portable, and easily usable by the community.

----
