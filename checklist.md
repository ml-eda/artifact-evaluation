# Artifact Checklist


Here, we provide a few informal suggestions to help you fill in the abstract template.
[Unified Artifact Appendix with the Artifact Checklist](https://github.com/mlcommons/ck/blob/master/docs/artifact-evaluation/template/ae.tex)
for artifact evaluation while avoiding common pitfalls.


## Abstract

 Briefly and informally describe your artifacts including minimal hardware, software and other requirements,
 how they support your paper, and what are the key results to be validated.
 Note that evaluators will use artifact abstracts to bid on artifacts.
 The AE chairs will also use it to finalize artifact assignments.


## Checklist


 Together with the artifact abstract, this checklist will help us make sure that evaluators
 have appropriate competency and access to the technology required to evaluate your artifacts.
 It can also be used as meta information to find your artifacts in Digital Libraries.

 ![](https://raw.githubusercontent.com/mlcommons/ck/master/docs/artifact-evaluation/image-general-workflow1.png)


 Fill in whatever is applicable with some informal keywords and remove unrelated items
 (please consider the questions below just as informal hints
 that reviewers are usually concerned about):


* **Algorithm:** Are you presenting a new algorithm?
* **Program:** Which benchmarks do you use? (e.g., ISCAS-85, Open-cores RTL, etc.)
 Are they included or should they be downloaded? Which version?
 Are they public or private? If they are private, is there a public analog to evaluate your artifact?
 What is the approximate size?
* **EDA Tools:** If you use EDA tools, which ones? Are they open source or proprietary? Have you provided scripts to run these tools?
 If proprietary tools, commercial/foundry PDKs, licensed IP, or licensed technology files are required, specify the tool/vendor/version, license assumptions, required PDK or technology package, required libraries/files, setup instructions, smoke test, expected outputs, and whether an open-source proxy or open PDK path is available.
* **Compilation:** Do you require a specific compiler? Public/private? Is it included? Which version?
* **Transformations:** Do you require a program transformation tool (source-to-source, binary-to-binary, compiler pass, synthesis, place-and-route, etc)?
 Public/private? Is it included? Which version?
* **Binary:** Are binaries included? OS-specific? Which version?
* **Model:** Do you use specific ML or LLM models (GPT, BERT, MobileNets, etc.)?
 Are they included, archived, downloadable, or API-based? If not, how should reviewers identify, download, install, or access them?
 Specify the exact model name, version/revision/hash or API model ID, license, approximate size, and model-serving requirements when applicable.
 For LLM-based artifacts, also summarize prompts or prompt-generation code, inference settings, metrics, raw or cached outputs, tolerance bands, and expected API cost or local GPU requirements.
* **Data set:** Do you use specific data sets?
 Are they included or should they be downloaded? Which version?
 What is their approximate size?
* **Run-time environment:** Is your artifact OS-specific (Linux, Windows, MacOS, Android, etc)?
 Which version? Which are the main software dependencies (JIT, libs, run-time adaptation frameworks, containers, locked Conda environments, etc)?
 Do you need root access?
* **Hardware:** Do you need specific hardware (supercomputer, architecture simulator, CPU, GPU, neural network accelerator, FPGA)
 or specific features (hardware counters
 to measure power consumption, SUDO access to CPU/GPU frequency, etc)?
 Are they publicly available?
* **Run-time state:** Is your artifact sensitive to run-time state (cold/hot cache, network/cache contentions, random seeds, API availability, etc.)?
* **Execution:** Any specific conditions should be met during experiments (sole user, process pinning, profiling, adaptation, no network access, etc)? How long will it approximately run?
* **Metrics:** Which metrics will be evaluated (execution time, inference per second, Top1 accuracy, power consumption, pass rate, QoR, etc.)?
* **Output:** What is the output of your key experiments (console, file, table, graph, logs, reports) and what are your key results
 (numerical results, empirical characteristics, generated artifacts, qualitative behavior, etc.)?
 Are expected results and acceptable tolerances included?
* **Experiments:** How to prepare experiments and validate results
 (README, scripts, [IPython/Jupyter notebook](https://jupyter.org "https://jupyter.org"),
 [MLCommons CM automation language](https://doi.org/10.5281/zenodo.8105339), containers etc)?
 Mention the validation path, such as full rerun, bounded subset rerun, cached-output validation, or evidence/log inspection.
 Do not forget to mention the maximum allowable variation or similar-result criterion for empirical results.
* **How much disk space required (approximately)?:** This can help evaluators and end-users to find appropriate resources.
* **How much time is needed to prepare workflow (approximately)?:** This can help evaluators and end-users to estimate resources needed to evaluate your artifact.
* **How much time is needed to complete experiments (approximately)?:** This can help evaluators and end-users to estimate resources needed to evaluate your artifact.
* **API cost or GPU-hours required (if applicable)?:** This is especially important for LLM or large training/inference artifacts.
* **Publicly available?:** Will your artifact be publicly available? If yes, we may spend an extra effort to help you with the documentation.
* **Code licenses (if publicly available)?:** If your workflows and artifacts will be publicly available, please provide information about licenses.
 This will help the community to reuse your components.
* **Data/model licenses and usage restrictions (if applicable):** If your data sets or models are included, archived, downloaded, or accessed through an external provider, please provide information about licenses and usage restrictions.
* **Workflow frameworks used?** Did authors use any workflow framework which can automate and customize experiments?
* **Zenodo DOI:**
 Note that the author-created artifacts relevant to this paper
 will receive the ACM "artifact available" badge *only if*
 they have been archived on [Zenodo](https://zenodo.org "https://zenodo.org")
 and the Zenodo DOI is provided in the final Artifact Appendix.
 The Zenodo record may archive a snapshot of the authors' GitHub repository.
 Personal web pages, Google Drive, GitHub, GitLab and BitBucket alone
 are not accepted for this badge.
 Authors can provide the Zenodo DOI for their artifacts at the end of the evaluation.




## Description



### How to access



Describe how reviewers will access your artifacts:

* Clone a repository from GitHub, GitLab or any similar service
* Download a package from a public website
* Download a package from Zenodo or another author-provided public archive during review
* Download a package from a private website or private review upload shared by the AE chairs
* Pull or load a Docker/Apptainer image, VM image, model cache, generated outputs, or logs
* Access artifact via private machine with pre-installed software (only when access to rare or publicly unavailable hardware is required or proprietary
  software is used - you will need to send credentials to access your machine to the AE chairs)



 Please describe approximate disk space required after unpacking your artifact.


### Hardware dependencies



 Describe any specific hardware and specific features required to evaluate your artifact
 (vendor, CPU/GPU/FPGA, number of processors/cores, interconnect, memory,
 hardware counters, GPU memory, etc).


### Software dependencies

 Describe any specific OS, EDA tools, and software packages required to evaluate your
 artifact. This is particularly important if you share your source code
 and it must be compiled or if you rely on some proprietary software that you
 cannot include in your package. In that case, we strongly suggest that you
 describe how to obtain and install all third-party software, data sets
 and models.

 If commercial EDA tools, commercial/foundry PDKs, proprietary IP, or licensed
 technology files are required, document the exact tool name, vendor, version,
 license assumptions, PDK name/release, required libraries/files, directory
 layout, setup commands, smoke test, expected reports/logs, and whether an
 open-source proxy or open PDK path is available. Do not include restricted
 license files, proprietary installers, or PDK contents unless redistribution
 is allowed.



### Data sets



 If third-party data sets are not included in your packages (for example,
 they are very large or proprietary), please provide details about how to download
 and install them.

 *In case of proprietary data sets, we suggest you provide reviewers
 a public alternative subset for evaluation*.


### Models



 If third-party models are not included in your packages (for example,
 they are very large, proprietary, or API-based), please provide details about how to identify,
 download, install, or access them.

 For open-weight or locally hosted models, specify the exact model source,
 checkpoint revision or hash, license, download or staging instructions, and
 approximate disk footprint. For closed API models, specify the provider, exact
 model ID, endpoint or service version if available, date range of the experiments,
 access assumptions, and known model-drift limitations.

 For LLM-based artifacts, provide prompts or prompt-generation code, inference
 settings, metrics, raw or cached outputs, expected values, tolerance bands,
 and expected API cost or local GPU/runtime requirements.



## Installation



 Describe the setup procedures for your artifact (even when containers are used).
 If a Docker image, Dockerfile, Apptainer/Singularity image, VM, locked Conda
 environment, or module-based setup is provided, describe how reviewers should
 build, load, or activate it. Include a smoke-test command and expected output
 when possible.



## Experiment workflow



 Describe the experimental workflow and how it is implemented
 and executed, i.e. some OS scripts,
 [IPython/Jupyter notebook](https://jupyter.org "https://jupyter.org"),
 containers, workflow frameworks, or scheduler scripts.
 Check [examples of Artifact Appendices](https://cknow.io/reproduced-papers "https://cknow.io/reproduced-papers").




## Evaluation and expected result

 Describe all the steps necessary to validate the key results from your paper.
 Describe expected results, including maximum allowable variation
 or similar-result criteria for empirical results.
 For each key result, specify the command or workflow reviewers should run,
 the expected output or metric, and whether reviewers should use a full rerun,
 bounded subset rerun, cached-output validation, or evidence/log inspection.
 For LLM artifacts, exact text reproduction is not required unless exact text is
 central to the paper's claim.


## Experiment customization

 It is optional but can be useful for the community if you describe all the knobs
 to customize and tune your experiments and maybe even trying them
 with a different data sets, benchmark/applications,
 machine learning models, software environment (compilers, libraries,
 run-time systems) and hardware.







----

*This document was prepared by [Grigori Fursin](https://cKnowledge.org/gfursin)
 with contributions from [Bruce Childers](https://people.cs.pitt.edu/~childers),
 [Michael Heroux](https://www.sandia.gov/~maherou),
 [Michela Taufer](https://gcl.cis.udel.edu/personal/taufer) and other great colleagues.
 It is maintained by the [cTuning foundation](https://cTuning.org/ae) and the
 [MLCommons taskforce on automation and reproducibility](https://github.com/mlcommons/ck/blob/master/docs/taskforce.md).*
