# Artifact Evaluation FAQ

<details>
<summary>Click here to see the table of contents.</summary>

* [Artifact evaluation](#artifact-evaluation)
  * [Frequently Asked Questions](#frequently-asked-questions)
    * [What is the difference between Repeatability, Reproducibility and Replicability?](#what-is-the-difference-between-repeatability-reproducibility-and-replicability?)
    * [Do I have to open source my software artifacts?](#do-i-have-to-open-source-my-software-artifacts?)
    * [Is Artifact evaluation blind or double-blind?](#is-artifact-evaluation-blind-or-double-blind?)
    * [How to pack artifacts?](#how-to-pack-artifacts?)
    * [Is it possible to provide a remote access to a machine with pre-installed artifacts?](#is-it-possible-to-provide-a-remote-access-to-a-machine-with-pre-installed-artifacts?)
    * [Can I share commercial benchmarks or software with evaluators?](#can-i-share-commercial-benchmarks-or-software-with-evaluators?)
    * [Can I engage with the community to evaluate my artifacts?](#can-i-engage-with-the-community-to-evaluate-my-artifacts?)
    * [Do I have to make my artifacts public if they pass evaluation?](#do-i-have-to-make-my-artifacts-public-if-they-pass-evaluation?)
    * [How to deal with numerical accuracy and instability?](#how-to-deal-with-numerical-accuracy-and-instability?)
    * [How to validate models or algorithm scalability?](#how-to-validate-models-or-algorithm-scalability?)
    * [Is there any page limit for my Artifact Evaluation Appendix?](#is-there-any-page-limit-for-my-artifact-evaluation-appendix?)
    * [Where can I find a sample HotCRP configuration to set up AE?](#where-can-i-find-a-sample-hotcrp-configuration-to-set-up-ae?)
  

</details>

## Frequently Asked Questions


**If you have questions or suggestions which are not addressed here, please feel free 
to contact vachhabr at asu.edu

### What is the difference between Repeatability, Reproducibility and Replicability?

We use the following definitions [adopted by ACM and NISO](https://www.acm.org/publications/policies/artifact-review-badging):

* *Repeatability (Same team, same experimental setup)*

  The measurement can be obtained with stated precision by the same team using the same measurement procedure, 
  the same measuring system, under the same operating conditions, in the same location on multiple trials. 
  For computational experiments, this means that a researcher can reliably repeat her own computation.

* *Reproducibility (Different team, different experimental setup)*

  The measurement can be obtained with stated precision by a different team using the same measurement procedure, 
  the same measuring system, under the same operating conditions, in the same or a different location on multiple trials. 
  For computational experiments, this means that an independent group can obtain the same result using the author's own artifacts.

* *Replicability (Different team, same experimental setup)*

  The measurement can be obtained with stated precision by a different team, a different measuring system, 
  in a different location on multiple trials. For computational experiments, this means that an independent group 
  can obtain the same result using artifacts which they develop completely independently.



### Do I have to open source my software artifacts?



No, it is not strictly necessary and you can 
provide your software artifact as a binary.
However, in case of problems, reviewers may not be 
able to fix it and will likely give you a negative score.


### Is Artifact evaluation blind or double-blind?



AE is a single-blind process, i.e. authors' names are known to the evaluators
(there is no need to hide them since papers are accepted),
but names of evaluators are not known to authors.
AE chairs are usually used as a proxy between authors and evaluators
in case of questions and problems.


### How to pack artifacts?



We do not have strict requirements at this stage. You can pack 
your artifacts simply in a tar ball, zip file, Virtual Machine or Docker image.
You can also share artifacts via public services including GitHub, GitLab and BitBucket.

Please see [our submission guide](submission.md) for more details.


### Is it possible to provide a remote access to a machine with pre-installed artifacts?



Only in exceptional cases, i.e. when rare hardware or proprietary software/benchmarks are required,
or VM image is too large or when you are not authorized to move artifacts outside your organization.
In such case, you will need to send the access information 
to the vachhabr at asu.edu via private email. 
They will then pass this information to the evaluators.


### Can I share commercial benchmarks or software with evaluators?



Please check the license of your benchmarks, data sets and software. 
In case you have any questions, try to find a free alternative. In fact, 
we strongly suggest you provide a small subset of free benchmarks 
and data sets to simplify the evaluation process to receive functionality badge.



### Do I have to make my artifacts public if they pass evaluation?

No, you don't have to and it may be impossible in the case of commercial artifacts.
Nevertheless, we encourage you to make your artifacts publicly available upon publication, 
for example, by including them in a permanent repository (required to receive the "artifact available" badge)
to support open science as outlined in [our vision](http://dl.acm.org/citation.cfm?id=2618142).


Furthermore, if you make your artifacts publicly available at the time
of submission, you may profit from the "public review" option, where you are engaged
with the community to discuss, evaluate and use your software. See such
examples [here](https://cTuning.org/ae/artifacts.html) (search for "public evaluation").



### How to deal with numerical accuracy and instability?



If the accuracy of your results depends on a given machine, environment and optimizations 
(for example, when optimizing BLAS, DNN, etc), you should provide a script to automatically 
report unexpected loss in accuracy above provided threshold as well as any numerical instability.


### How to validate models or algorithm scalability?



If you present a novel parallel algorithm or some predictive model which should scale 
across a number of cores/processors/nodes, we suggest you 
to provide an experimental workflow that could automatically detect the topology 
of a user machine, validate your models or algorithm scalability, 
and report any unexpected behavior. 


### Is there any page limit for my Artifact Evaluation Appendix?


There is currently a 2 page limit for the AE Appendix in the camera-ready for MLCAD papers.




