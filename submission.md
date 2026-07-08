
# Artifact submission

This document provides the guidelines to submit your artifacts for evaluation at MLCAD.


## Motivation

It's becoming increasingly difficult to reproduce results from MLCAD papers.
Voluntary Artifact Evaluation (AE) was successfully introduced
at programming languages, systems and machine learning conferences and tournaments
to validate experimental results by the independent AE Committee, share unified Artifact Appendices,
and assign artifact badges.


AE promotes artifact sharing and independent validation of experimental results
and encourages artifact sharing to help the community quickly validate and compare alternative approaches.
Authors are invited to formally describe all supporting material (code, data, models, workflows, results)
using the [Artifact Appendix and Artifact Checklist](checklist.md)
and submit it to the [single-blind AE process](reviewing.md).
Reviewers will then collaborate with the authors to evaluate their artifacts under the
[ACM artifact badging framework](https://www.acm.org/publications/policies/artifact-review-and-badging-current),
which includes Artifacts Available, Artifacts Evaluated - Functional, and Results Reproduced.
The three ACM artifact badge images are shown below:


![](https://www.acm.org/binaries/content/gallery/acm/publications/replication-badges/artifacts_available_dl.jpg)
![](https://www.acm.org/binaries/content/gallery/acm/publications/replication-badges/artifacts_evaluated_functional_dl.jpg)
![](https://www.acm.org/binaries/content/gallery/acm/publications/replication-badges/results_reproduced_dl.jpg)

MLCAD 2026 will award only Artifacts Available and Artifacts Evaluated - Functional. MLCAD 2026 will not award a Results Reproduced / Reproducible badge.


## Preparing your Artifact Appendix and Artifact Checklist


You need to prepare the [Artifact Appendix](https://github.com/ml-eda/artifact-evaluation/blob/upstream-ae/template/ae.tex)
describing all software, hardware, and data set dependencies, key results to be validated, and how to prepare, run, and validate experiments.

For MLCAD 2026, authors seeking the Artifacts Evaluated - Functional badge should also describe how each key result should be evaluated. For each result, specify the command or workflow reviewers should run, the expected output or metric, the acceptable tolerance or similar-result criterion, the validation path, and any required compute, model, API, commercial-tool, or PDK access.

If your artifact uses LLMs, the Artifact Appendix and artifact README should explicitly state:

* the exact model used and how reviewers can access or identify it,
* for open-weight or locally hosted models: the source, checkpoint revision/hash, license, download or staging instructions, and whether the model files are included or archived,
* for closed API models: the provider, exact model ID, endpoint or service version if available, date range of the experiments, access requirements, and any known model-drift limitations,
* inference settings such as temperature, top-p/top-k, maximum tokens, seeds if supported, number of samples, stop sequences, and retry policy,
* prompts, prompt templates, few-shot examples, prompt construction code, and generated prompt dumps if prompts are dynamic,
* metric definitions, scoring scripts, raw outputs, expected values, and tolerance bands,
* the expected number of runs or samples for AE,
* API cost or local GPU/runtime requirements,
* whether reviewers should run the full workflow, a smaller audit subset, or recompute metrics from cached outputs.

We strongly encourage you to check the
[Artifact Appendix guide](checklist.md),
[artifact reviewing guide](reviewing.md),
and [AE FAQs](faq.md) before submitting artifacts for evaluation!

You can find the examples of Artifact Appendices
in the following [Artifact Appendix examples](https://cknow.io/reproduced-papers).


## Preparing your experimental workflow

**You can skip this step if you want to share your artifacts without Functional evaluation -
 in such case, your paper can still be entitled to the "artifact available" badge!**

We strongly recommend that authors provide at least some automation scripts to build their workflow,
all inputs to run your workflow, and some expected outputs to validate results from your paper.
You can then describe the steps to evaluate your artifact
using README files or [Jupyter Notebooks](https://jupyter.org "https://jupyter.org").

For MLCAD 2026, authors should provide a Docker image or an equivalent locked environment when possible. The image or environment should have all non-licensed dependencies preinstalled so reviewers do not need to install unspecified packages during AE. Include the Dockerfile or build instructions, dependency versions, a smoke-test command, the full evaluation command or reviewer subset command, and expected outputs.

If Docker is not suitable, authors may provide an Apptainer/Singularity image, VM image, locked Conda environment, module-based setup, or remote machine access. The setup instructions should be detailed enough that reviewers do not need to infer package names, versions, environment variables, model locations, dataset paths, or run commands.

Feel free to reuse [portable CM scripts](https://github.com/mlcommons/ck/tree/master/cm-mlops/script)
being developed by the MLCommons to automate common steps to prepare and run various benchmarks
across continuously changing software, hardware, and data.


## Making artifacts available to evaluators

Most of the time, the authors make their artifacts available to the evaluators via GitHub,
GitLab, BitBucket or private repositories. Public artifact sharing allows
optional "open evaluation". It allows the authors to quickly fix encountered issues during evaluation
before submitting the final version to Zenodo.


Other acceptable methods include:
* Using zip or tar files with all related code and data, particularly when your artifact
 should be rebuilt on reviewers' machines (for example to have a non-virtualized access to a specific hardware).
* Using [Docker](https://www.docker.com "https://www.docker.com"), [Virtual Box](https://www.virtualbox.org "https://www.virtualbox.org") and other containers and VM images.
* Arranging remote access to the authors' machine with the pre-installed software
 - this is an exceptional case when rare or proprietary software and hardware is used.
 You will need to send the private access information to the AE chairs privately.

For MLCAD 2026, AE chairs may also provide a private upload location, such as a Drive folder, for large review artifacts including Docker images, VM images, model caches, generated outputs, and logs. The private upload link will be shared with authors directly and should not be posted in the public Artifact Appendix or GitHub repository.


Note that your artifacts will receive the ACM "artifact available" badge
**only if** they have been archived on [Zenodo](https://zenodo.org "https://zenodo.org")
and the Zenodo DOI is provided in your final Artifact Appendix.

The Zenodo record may archive a snapshot of the authors' GitHub repository. GitHub alone is not sufficient for the Artifacts Available badge because it does not provide the required Zenodo DOI.

Commercial EDA tools, licensed binaries, and commercial/foundry PDKs that cannot be publicly redistributed do not count as publicly available artifacts. Document such dependencies separately and provide public scripts, open proxies, logs, reports, or other evidence when possible.

For model-based artifacts, the model dependency must also be clear. Open-weight or local models should be included in the artifact when redistribution permits, archived with the artifact, or downloadable from a stable source with exact revision/hash and license information. Closed API models cannot be archived by authors, but the provider, model ID, endpoint or service version if available, access assumptions, and cached outputs or metric recomputation path should be documented.



## Submitting artifacts
Write a brief abstract describing your artifact, the minimal hardware and software requirements,
how it supports your paper, how it can be validated, and what the expected result is. The template for the abstract is available in this repository [here](https://github.com/ml-eda/artifact-evaluation/tree/main/template). Specify any proprietary software or hardware requirements, as well as the compute resources needed for training, inference, or evaluation.

If the artifact requires commercial EDA tools, commercial PDKs, proprietary IP, or licensed technology files, describe the setup in enough detail that a reviewer who already has access can install, configure, and validate the flow. Include:

* exact tool vendor, product name, version, build number, supported operating system, and required license features,
* license-server assumptions, environment variables, setup files, and module commands,
* required PDK or technology package, including foundry or source, process node, PDK name, release/version, and required subcomponents,
* required libraries and technology files, such as standard-cell libraries, SRAM or IP libraries, Liberty, LEF/DEF, GDS, SPICE, QRC, DRC/LVS decks, or technology files,
* expected directory layout, mount points, symbolic links, and environment variables for tools, PDKs, libraries, and generated outputs,
* all scripts and configuration files needed to run the flow, such as Makefiles, TCL scripts, Slurm scripts, YAML/JSON configs, and wrapper scripts,
* step-by-step setup instructions starting from the provided container, VM, locked environment, or clean machine image,
* commands to verify that the tool installation, license, and PDK setup are visible to the artifact,
* a smoke-test command and the expected successful output or log message,
* the full evaluation command or reviewer subset command,
* expected reports, metrics, logs, generated files, and tolerances,
* whether an open-source proxy flow or open PDK is available when the commercial setup is not accessible.

Do not include confidential license files, proprietary installers, or restricted PDK contents in a public archive unless redistribution is allowed. If the artifact depends on those components, state what is not included and explain how a reviewer with access should install, mount, or point the artifact to them. Sensitive access details should be shared only through the private AE process.

This abstract will be used by evaluators during artifact bidding to make sure that
they have access to appropriate hardware and software and have the required skills.
Submit the artifact abstract and the PDF of your paper with the Artifact Appendix attached
using the AE submission website provided by MLCAD.




## Asking questions

 If you have questions or suggestions,
 do not hesitate to get in touch with the AE chairs using the contact information provided in the acceptance notification or AE submission site.

## Preparing your camera-ready paper

If you have successfully passed AE with at least one artifact badge,
you will need to add up to 2 pages of your artifact appendix
to your camera-ready paper while removing all unnecessary or confidential information.
This will help readers better understand what was evaluated and how.


If your paper is published in the ACM Digital Library,
you do not need to add badge images - ACM will add them to your camera-ready paper
and will make this information available for search!

In other cases, AE chairs will tell you how to add badges to the first page of your paper.



## Historical examples of shared artifacts and Artifact Appendices:

The following links are historical examples from other AE processes. They are provided as examples of artifact packaging and Artifact Appendices; they do not imply that MLCAD 2026 offers the Results Reproduced badge.

* [Examples from past AE processes](https://cknow.io/?q=%22reproduced-papers%22) (ASPLOS, MICRO, MLSys, Supercomputing, CGO, PPoPP, PACT, IA3, ReQuEST)
* [Historical dashboards with reproduced results](https://cknow.io/?q=%22reproduced-results%22)
* Paper "Highly Efficient 8-bit Low Precision Inference of Convolutional Neural Networks with IntelCaffe" from ACM ASPLOS-ReQuEST'18
  * [Paper DOI](https://doi.org/10.1145/3229762.3229763)
  * [Artifact DOI](https://doi.org/10.1145/3229769)
  * [Original artifact](https://github.com/intel/caffe/wiki/ReQuEST-Artifact-Installation-Guide)
  * [Portable automation](https://github.com/ctuning/ck-request-asplos18-caffe-intel)
  * [Expected results](https://github.com/ctuning/ck-request-asplos18-results-caffe-intel)
  * [Public scoreboard](https://cknow.io/result/pareto-efficient-ai-co-design-tournament-request-acm-asplos-2018)
* Paper "Software Prefetching for Indirect Memory Accesses" from CGO'17
  * [Portable automation at GitHub](https://github.com/SamAinsworth/reproduce-cgo2017-paper)
  * [CK dashboard snapshot](https://github.com/SamAinsworth/reproduce-cgo2017-paper/files/618737/ck-aarch64-dashboard.pdf)


----

*This document was prepared by [Grigori Fursin](https://cKnowledge.org/gfursin "https://cKnowledge.org/gfursin")
 with contributions from [Bruce Childers](https://people.cs.pitt.edu/~childers "https://people.cs.pitt.edu/~childers"),
 [Michael Heroux](https://www.sandia.gov/~maherou "https://www.sandia.gov/~maherou"),
 [Michela Taufer](https://gcl.cis.udel.edu/personal/taufer/ "https://gcl.cis.udel.edu/personal/taufer/") and others.
 It is tailored to suit the MLCAD community.*
