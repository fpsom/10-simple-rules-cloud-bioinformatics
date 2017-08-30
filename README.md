# Ten Simple Rules for Using Cloud Computing (in Life Sciences?)
A short article for 10 simple rules in Cloud Computing and Bioinformatics / Life Sciences


## Introduction

[^fn1]

[@Beaulieu-Jones2016]



## Rule 1:

_Understand what Cloud Computing actually is (and stands for)._

Although Cloud Computing, as a technology buzz word, is fortunately beyond it's hype phase (ref?), the notion of what cloud computing is and how it can be best utilized can be still quite fuzzy, especially when moving beyond the traditional ICT sciences and into other domains such as Life Sciences.

The formal, dictionary definition of cloud computing is "*the practice of using a network of remote servers hosted on the Internet to store, manage, and process data, rather than a local server or a personal computer*". In the simplest terms, cloud computing means storing and accessing data and executing software over the Internet instead of on your local computer. The cloud is just a metaphor for the Internet. It goes back to the days of flowcharts and presentations that would represent the gigantic server-farm infrastructure of the Internet as nothing but a puffy, white cumulus cloud, accepting connections and doling out information as it floats (https://www.pcmag.com/article2/0,2817,2372163,00.asp).

In practical terms, cloud computing stands for computational resources (i.e. CPU, RAM and hard disk space) that are available through a dedicated provider and to which you have no access (or knowledge for that matter) to the actual physical resources.  At a more technical level, cloud computing resources are usually in the form of Virtual Machines (or for short VMs) which are tailored made to the requirements of each case / client. An oversimplified case of such a VM is one that provides only disk space without any actual computational capabilities, which essentially devolves cloud computing down to an online storage service (one of the reasons that services such as Dropbox have been interchangeably used in the past with the term cloud computing).

In Life Sciences, VMs are being increasing utilized both in research as well as at production level, in order to address scalability issues as well as for convenience purposes. Key examples of public services being provided through cloud computing are Galaxy????.

https://www.youtube.com/watch?v=g334gTtpvo4

## Rule 2:

_Search for existing advice (there is always someone who tried something similar already)_

So, you have understood what Cloud Computing is and now the goal is to use Cloud Computing in your own research. Although the axiom is almost as old as computer science, before attempting to start everything from scratch, do an adequate (if not exhaustive) review of what is actually out there. Odds are that something similar has already been attempted before so there are probably some rough guidelines on how to proceed.


## Rule 3:

_Decide on the “Pet” or “Cattle” approach._

This is one of the key decisions when dealing with Cloud Computing: do you require a VM that will be up and running 24/7 providing a continuous service, or would you rather need the successful execution of a single (or multiple) processes and the release the computational resources?

In the former case, the solution is to have a single VM (usually with sufficient specifications for the required service) that you will need to constantly manage and care for - hence the _"pet"_ classification. In this case, as the cost of maintaining a VM in commercial resources can rise significantly given sufficient time, a good practice is to do first a cost-benefit analysis before moving forward. Alternatively, and especially for research purposes, most Universities and Research Centers provide some form of Cloud Infrastructure, in addition to other National or cross-national infrastructures (such as EGI and XSEDE to name a few). For a more detailed discussion on the different types of Cloud Computing providers, have a look at Rule #7.

In the second case, you will need to define a process of quickly setting up VM(s) for running the specific software, before deleting them - hence the _"cattle"_ classification. One of the most convenient ways of running processes in this approach is through the use of Docker images and containers. Simply put, a Docker image is a snapshot of a tool with its environment (i.e. library dependencies, OS and otherwise) so that it can be executed anywhere that the Docker daemon is present. Essentially, a Docker image is a lightweight environment (compared to a full VM) that the code can be successfully run. Each image can produce any number of containers (i.e. the live, running instance of the image) which can be safely discarded when the execution of the tool is completed.


## Rule 4:

_Data Management planning_

Security and privacy are primary concerns especially in Life Sciences. Therefore, putting your whole data center in the cloud, beyond impractical for most cases, it is almost always prohibited by security requirements. For this reason you need to specify and design a data management plan that will define the particular aspects of data that will be moved for processing in the cloud, which VMs or containers will have access to the data, how any intermediate files will be handled and how the final output will be returned or stored in the Cloud Infrastructure.

When dealing with sensitive data, one of the key policies that you need to be aware of is HIPAA-compliant data. HIPAA, the Health Insurance Portability and Accountability Act of 1996, sets the standard for protecting sensitive patient data. Any company that deals with protected health information (PHI) must ensure that all the required physical, network, and process security measures are in place and followed. In terms of Cloud Computing, most of the commercial Cloud providers (including Amazon, Microsoft and Google) can conform to the HIPAA standard through specific, enterprise-level agreements.

However, it is equally important to note that many users are so accustomed to using these commercial platforms in their daily lives that they may not consider the necessary steps to protect the information within their Cloud solutions. For example, it isn't enough to make sure that the data are secured in the Cloud infrastructure and accessible only by authorized parties - you also need to make sure that the users do not download the data into unauthorized and/or unsecured devices as well.


## Rule 5:

_Integrating different components is always a puzzle; solve it before it happens_

Most processes in Bioinformatics can be boiled down to a set of individual steps that are chained together, the output of one tool being the input of the next. The technical requirements of each step are usually known a priori - however the actual chaining process is not always the most straightforward process. Given that an efficient Cloud Computing solution usually means an automated, unsupervised computational process, the different components of the puzzle should be integrated before the main execution of the final workflow.





## Rule 6:

_Establish a reproducible computational workflow_


Technical requirements are always known, but expect serious re-tweaking to get a cloud-based solution to work in the optimal way. There are several tools that can help you automate any workflow, such as snakemake ...




## Rule 7:

_Commercial or public e-infrastructure?_

Public is good in order to evaluate the ultimate feasibility of the solution. Commercial shines for short-/mid-term production-level deployment (especially of the “cattle” paradigm).

## Rule 8:

_First attempt will always have issues; treat it as a training experience_



## Rule 9:

_Documentation is King._

Establish the success metrics and test against them at each iteration.

## Rule 10:

_Maintain and publish the log book_

i.e. adhere to the Open Science rules)

## Conclusion


## Supporting Information


## Acknowledgments


## References
[^fn1]: [@Beaulieu-Jones2016], ¶6.

* blogs.nature.com/naturejobs/2017/06/01/techblog-c-titus-brown-predicting-the-paper-of-the-future
* Serverless scientific computing (function as a service) SWC thread

pandoc README.md --smart --standalone --bibliography literature.bib -o README.html
pandoc README.md --smart --standalone --bibliography literature.bib -o README.pdf
pandoc --filter=pandoc-crossref --filter=pandoc-citeproc --smart --listings --number-sections --standalone README.md -o README.pdf
