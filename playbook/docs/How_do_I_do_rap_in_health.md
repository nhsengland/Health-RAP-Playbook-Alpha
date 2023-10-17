# How do I do RAP in health?

> **Note**
>
> For more information on:
>
> - Who else is doing RAP and why you should think about doing it, see ["Who else is doing RAP"](Who_else_is_doing_it.md "Useful Resources from Other Groups Doing RAP")
> - When you should not do RAP, see ["Permitted Exceptions to Open Sharing of Reproducible Analytical Pipelines"](Exceptions_to_open_sharing_of_RAP.md "Permitted Exceptions to Open Sharing of Reproducible Analytical Pipelines")

## Executive Summary



- **Work out what you want to achieve from RAP** - Pick your strategy and think about the benefits in the context of your organisation.
- **Start small and build out** - If your pipelines aren't very mature, the first steps might just be to get everything to [**baseline RAP**](Levels_of_RAP.md), and focus on training your staff in the basics. You could also take some exemplar projects all the way to gold, to find out what's possible.
- **Engage early with key stakeholders and discuss RAP frequently** - Information Governance (IG) and cyber security teams may see risks in open-source tools, publishing code and sharing code between teams. Make sure you have mitigations in place. Platforms and IT need to be brought in to address any shortfalls in technology. Engage early with your data owners, platform owners, IG teams, and internal IT as these can all release blockers to the successful implementation of RAP in health.
- **Set up a RAP champion squad** - Even just two people will be crucial for helping others, figuring out workarounds, and promoting the benefits of RAP.
- **Audit your tooling and existing pipelines** - Recognise how mature the tools and pipelines are and identify what is missing, who needs help and what is blocking progress.
- **When working with secure health data,such as patient level records, you will have to operate in a more secure environment** - Extra stages will need to be added to ensure both you and the secure data are protected from accidentally releasing things that should not be released.

This guide will be broken into sections following the [Government Analysis Function RAP Strategy](https://analysisfunction.civilservice.gov.uk/policy-store/reproducible-analytical-pipelines-strategy/ "Reproducible Analytical Pipelines (RAP) strategy"), discussing how to ensure we have:

- [The right tools](#the-right-tools)
- [The right capability](#the-right-capability)
- [The right culture](#the-right-culture)

## Are You Working with Open Data or Secure Health Data?

> **Note**
>
> This guide **will mostly be concerned with issues arising due to working on sensitive health data.** Open data people can skip past the Secure Environments section and the more generic RAP guides will generally be usable.

There are certain risks and conflicts when we combine the transparency goal of RAP, with the need to handle patient and public data in line with our obligations as health data analysts, which can be health (and NHS) data specific. For example, data versioning is a key desire of RAP, so that results can be reproduced at key points in time. However, with the [National Data Opt-out](https://digital.nhs.uk/services/national-data-opt-out "The national data opt-out is a service that allows patients to opt out of their confidential patient information being used for research and planning"), or even changes in legislation, patients may be removed from historical records.  We need to both be able to mechanically remove patients from datasets, and accept that it could alter the results leading to a level of irreproducibility.

We **MUST** avoid patient and public data leaking out via transparency routes - such as accidentally committing data files to code version control repositories, or leaving record level (and unsuppressed) data visible in any outputs or from being accidentally put into repositories.

Therefore, the first question about RAP and Health data is - is your data and work open, or does it need to be secure?

**If it's open, many of the challenges described elsewhere in this play book may not apply to you** and the more generic RAP guidance available ([much of which can be seen here](https://nhsdigital.github.io/rap-community-of-practice/useful_links/)) will generally be usable.

**If the data is secure, such as patient level records, then you will have to operate in a more secure environment**, and extra stages need to be added to the RAP, to ensure both you and any secure health data are protected from accidentally releasing things that should not be released.

## Some points to consider when getting started

> **In an ideal system**
>
> - Senior leadership will embrace [open source](https://transform.england.nhs.uk/key-tools-and-info/digital-playbooks/open-source-digital-playbook/ "Open source digital playbook: How to use digital ways of working to improve outcomes for patients") and champion the [benefits](https://analysisfunction.civilservice.gov.uk/support/reproducible-analytical-pipelines/benefits-to-government-from-reproducible-analytical-pipelines/ "Benefits to Government from Reproducible Analytical Pipelines") RAP can bring to your organisation.
> - Platforms and tooling will allow use of open source analytical tools, and give analysts access to version control while maintaining [data security](https://www.hra.nhs.uk/planning-and-improving-research/research-planning/how-were-supporting-data-driven-technology/accessing-health-and-care-data-research-data-driven-technology-step-step-guide-and-glossary/ "Accessing Health and Care Data For Research On Data-Driven Technology: A Step-By-Step Guide And Glossary").
> - Analyst leaders will help analysts deal with blockers, and prioritise and protect efforts to do RAP
> - [RAP champions](https://analysisfunction.civilservice.gov.uk/support/reproducible-analytical-pipelines/reproducible-analytical-pipeline-rap-champions/#more-information-about-rap-champions "More Information About RAP Champions") must get the local RAP community going, work across silos and help analysts get unstuck by understanding the local situation.
> - Analysts will take advantage of existing [RAP communities](https://nhsdigital.github.io/rap-community-of-practice/ "RAP Community of Practice: Improve reliability, transparency, and speed of statistics publications.") and contribute to them.

**Pick a strategy**. This might be to get the basics right on a wide set of analytical pipelines, maximise automation, or provide a strong example of the benefits that can be achieved if you go all the way.

**Set up a [RAP champion](https://analysisfunction.civilservice.gov.uk/support/reproducible-analytical-pipelines/reproducible-analytical-pipeline-rap-champions/#more-information-about-rap-champions "More Information About RAP Champions") squad**. Change needs people to champion it, to figure out a way forward and to help others. Even if this is only two people they can make a big difference.

**Audit the current situation in your organisation**.  Identify how mature your existing pipelines are and what is possible within the current platforms. Measure these against [levels of RAP](https://nhsdigital.github.io/rap-community-of-practice/introduction_to_RAP/levels_of_RAP/ "The 'Levels of RAP' Maturity Framework"), and the [RAP strategy](https://analysisfunction.civilservice.gov.uk/policy-store/reproducible-analytical-pipelines-strategy/#section-13 "Platforms for Reproducible Analysis").
  
Once you have a strategy you need to **regularly engage with leadership in analytics, Information Governance, IT, and your risk owners** to agree on your strategy. Agree on what can be done and where the risks lie, and mitigate the risks by following best practices and showing how others have done it.  
  
**Stay resilient as you will hit blockers**. Blockers might be technical, procedural, or conflicting priorities. Refer back to your strategy regularly and use the organisation's leadership to drive change. You are not alone - you can also reach out to the wider RAP community for help.



## The Right Tools

> **In an ideal system...**
>
> **Senior leadership will:**
>
> - Understand the extent to which their platforms are RAP capable, and promote filling the gap.
> - Set an expectation that RAP compliance can compliment meeting Information Governance and  security commitments.  
>  
> **Platforms will:**
>
> - Provide a space in which staff can meet every level and dimension of RAP - namely being able to access the required data, compute, external code (and packages), to be able share and publish code, and for each step to be automatable.
> - Be as easy to use as possible, but also safe, with the appropriate security, controls, and assurance in place.
> - Be conscious of existing and emerging standards, such as the **[NHS Secure Data Environments (SDE) requirements](https://www.gov.uk/government/publications/secure-data-environment-policy-guidelines/secure-data-environment-for-nhs-health-and-social-care-data-policy-guidelines#secure-data-environment-guidelines "Secure Data Environment Guidelines")**: It is not the job of analysts to lobby for platforms to meet these standards.
>
> **Analysts and Data Engineer leaders (and RAP champions) will:**
>
> - Work with platforms, security, and Information Governance teams to develop platforms which are RAP compliant, flexible, and responsive whilst also meeting commitments to data protection and security.
> - Ensure analysts and data engineers get access to the right tools, and that they use them.
>
> **Analysts and Data engineers will:**
>
> - Use open-source tools where appropriate and publish their code in a safe way [unless they are one of the few exceptions to this](https://www.gov.uk/government/publications/open-source-guidance/when-code-should-be-open-or-closed "When code should be open or closed").
> - Ensure data is versioned to allow for analyses to be reproduced, where possible, given health data may change such as due to national opt-outs.

The [Cross Government RAP strategy](https://analysisfunction.civilservice.gov.uk/policy-store/reproducible-analytical-pipelines-strategy/#section-7 "Why Reproducible Analytical Pipelines matter") sets out that analysts often do not have the tools they need to do good analysis and to make it repeatable. Many of the issues faced by analysts in the wider sector are also experienced in health, such as:

- not having the right tools.
- the tools they have entrenching manual processes.
- analyst requirements not being a focus of the platform specification.

This is especially true in the health sector, where due to the very sensitive nature of the data we use, cyber security and Information Governance compliance are used as excuses for creating nearly uncrossable silos, inefficient manual processes, and for not publishing code. Security through obscurity is considered insufficient and bad practice by Government Cyber Security policy (see [security considerations when coding in the open](https://www.gov.uk/government/publications/open-source-guidance/security-considerations-when-coding-in-the-open "Security considerations when coding in the open")).

The tools dimension also encompasses the data we use. Often data is not very easy to do RAP on. The data itself is usually not version-controlled, making precisely recreating previous work not always possible. Some data returns change regularly, and use quite loose data collection tools (such as spreadsheets), requiring frequent adjustment of analytical processes. Other datasets hardly ever change, with many issues commonly known, but poorly documented for decades, meaning each set of analysts starts from scratch doing a lot of pre-processing.

RAP helps solve these issues and makes things more efficient and transparent, but particularly in health, there are a number of hurdles, which require attention before RAP can really take off.

> **What parts of RAP can be done regardless of technology?**
> 
> Many health analysts do not have the perfect tools for RAP, however this should not stop them adopting RAP principles. It is important to remember that something is often better than nothing, and that we need to focus on what the benefits are and how we can achieve them.
>
> For example, if your organisation does not have any open source tools, or git, getting started with RAP might sound impossible, but at least you could start documenting your existing processes, making flow-charts to describe any pain points, and documenting how long and how much resource they take to run.
>
> If you have access to any open source language, but cannot move some key part of the process off a closed source tool, work around it. RAPify those parts of the pipeline you can change, and can access.
>
> It is also wise to start by focussing on the parts causing you the most trouble. Use your open source tool to automate the manual steps, or the tests and checks that are done by eye.
>
> If it is difficult to share code between teams, or extract code and data from a secure environment, then share it when you can, perhaps at some key checkpoints in the work.

### Secure Data Environments (or Trusted Research Environments)

A lot of health data analytics, data engineering, science, and research occurs in secure data environments (SDE), also called trusted research environments (TRE).  The aim of SDEs is to provide a controlled space where analysts can use the data, safe from outside attack, but also that human error on their part won't necessarily cause a data breach.

There are several guidelines that outline how an SDE should function and what features it should contain:

- [Government policy guidelines on an SDE for NHS Health and Social Care Data](https://www.gov.uk/government/publications/secure-data-environment-policy-guidelines/secure-data-environment-for-nhs-health-and-social-care-data-policy-guidelines "Secure data environment for NHS health and social care data - policy guidelines")
- [Health Data Research UK Trusted Research Environments](https://www.hdruk.ac.uk/access-to-health-data/trusted-research-environments/ "Aligning approaches to Trusted Research Environments: A Work Stream Convened by the UK Health Data Research Alliance")
- [NHS England Transformation Directorate Rationale Behind Secure Data Environments](https://transform.england.nhs.uk/key-tools-and-info/data-saves-lives/secure-data-environments/ "A summary of what Secure Data Environments are and why we’re making this change")

The design of SDEs need to be carefully considered. The natural approach of security conscious architects is to lock everything down and make an environment where analysts working for different purposes and with different sets of data cannot share their code (easily), and where extracting code and results from the environment is difficult, sometimes to the extent that analysts refuse to use it. This is not only counter productive, harming the productivity of analysts and their potentially lifesaving work, but it is also in contradiction to one of the aims of the SDEs: to enable open, transparent, and collaborative working on the patient and public data.

In the following sub-sections we will explore the different aspects of the SDEs which need to be considered in their design.

#### Transparency vs Security

Given a key part of RAP is transparency and sharing, this can create a conflict. It is crucial we keep patients' and the public's data safe, however as the Government policy guidelines above sets out: *"code developed in secure data environments must be published in the open unless there is a specific rationale for not doing so"*.

There is risk whenever we move anything held within an SDE outside of the environment. This includes limiting the movement of:

- any analysis outputs such as aggregated data, graphs, charts, etc.
- dashboards and APIs.
- code, including packages and code repositories.
- other artefacts, such as table metadata, [trained machine learning models](https://dareuk.org.uk/sprint-exemplar-project-graimatter/ "GRAIMATTER: Guidelines and Resources for Artificial Intelligence Model Access from Trusted Research Environments"), etc.

It is also important to remember that risk cannot be eliminated - only managed and reduced - and the level of risk that is acceptable from different sources is a business question most likely unique to each organisation. There is also risk posed by poorly implemented, or overly tight security. If a platform is so locked down analysts and researchers cannot do their work, then this could ultimately harm patients and the public. Additionally, if it is too burdensome for analysts to share their work, or reuse the work of others, this also poses a risk, such as a risk of duplication of work, lowered productivity, and reputational damage.

Below we will discuss some approaches to reduce the risk, however, it is crucial that we accept that transparency and sharing are not "nice to have". They are a core objective of RAP, and necessary to avoid duplicated work, inefficiency, and poor practice, whilst also raising public trust.

##### Air Gaps / Working in an SDE

Air gaps are a nearly impenetrable barrier around the space in which code is run against the patient data within an SDE. It prevents data, files, and other connections (such as to the internet) from passing through, except via agreed, monitored, and controlled routes, such as a "safe output service". This is a crucial part of the security of the SDE, however it does make doing RAP more challenging, principally because it will be difficult to share any code developed within the SDE, either publicly published [as recommended by NHS SDE policy guidelines](https://www.gov.uk/government/publications/secure-data-environment-policy-guidelines/secure-data-environment-for-nhs-health-and-social-care-data-policy-guidelines "Secure data environment for NHS health and social care data - policy guidelines"), shared with colleagues, or uploaded to a package repositories such as [CRAN](https://cran.r-project.org "The Comprehensive R Archive Network"), [Pypi](https://pypi.org "The Python Package Index"), etc.

The air gap can lead to a need to break down analytical pipelines into stages. This can be due to a reduced user experience or lack of tools within the SDE making it harder to get needed packages or extensions for IDEs and leading to analysts wanting to do work, where possible, outside the SDE. For example, continuing to process aggregated results into final reports outside of the SDE. There are some use cases that simply need access to the internet or other systems, for example loading outputs onto an organisations website or supporting a dashboard.

Depending on how the SDE is designed, the code version control setup might be located inside the air gap, pass through it, or be outside the SDE with some mechanism to pass code into it. In either case, the core purpose needs to be remembered: it is crucial that code can be backed up, shared and reused.  

The result of this is that SDE air gaps need to be carefully designed with machine readable routes to get inputs and outputs into, and out of, the SDEs. Examples of this are:

- data APIs with credentials
- code version control
- publishing code to package repositories (both internal "private" ones and public global ones)
- downloading outputs for further analysis
- passing data into the system.

##### Repo Checks / Secret Scanning

Due to the sensitive nature of health data, and the novelty of code version control to many of our analysts, within the health industry there is a particular risk of accidental disclosure of patient data via code version control, for example accidentally uploading code with a comment containing some patient data used in testing, to a git repo.  Current approaches taken by SDEs have involved having humans manually checking outputs to ensure they are not disclosive, however this is by definition very manual, not scalable, and simply not feasible for some outputs, such as dashboards and APIs, or very large codebases. Fortunately, there are other options which can be used alongside manual human checks:

- Simply adding `.gitignore` files to the git code repositories will make it harder for data files such as CSV, parquet, or Excel spreadsheets to be added accidentally to the repository.  Adding `.gitignore` files can form a standard part of the organisational git repository template (such as the [govcookiecutter](https://github.com/best-practice-and-impact/govcookiecutter)).
- Using [Git hooks](https://githooks.com/ "Git Hooks"), such as pre-commit, to run scripts against the code and catch any issues prior the code landing in the repository.
- Using continuous integration and continuous deployment (CI/CD) tools, such as GitHub Actions, to scan the code for any issues prior to merges, releases, or further code promotion

Git hooks and CI/CD rely on finding the right scripts or tools to run against the code to identify any issues. There are a number of scripts already available, of varying complexity, that can be used.  This includes simply scanning for "secrets", such as access tokens to AWS, to more complex machine learning approaches. Some examples available to analysts are:

- **[Gitleaks](https://github.com/gitleaks/gitleaks "Gitleaks: Protect and Discover Secrets Using Gitleaks"):** a tool for detecting and preventing hardcoded secrets like passwords, api keys, and tokens in git repositories.
- **[Git Secrets](https://github.com/awslabs/git-secrets "Git Secrets"):** a tool that prevents you from committing secrets and credentials into git repositories.
- **[Amazon Macie](https://aws.amazon.com/macie/ "Amazon Macie: Discover and Protect Your Sensitive Data at Scale"):** a tool that discovers sensitive data using machine learning and pattern matching, provides visibility into data security risks, and enables automated protection against those risks.

##### Platforms Architecture

Given all the considerations above, platform design needs to be thought through carefully so that it is both safe and secure, but also makes RAP as achievable as possible. It is important to note that SDEs fall into one of two categories:

1. SDEs where users work inside the SDE, exposed to the data directly.
1. SDEs where users work outside the SDE against dummy data, and submit their code which is approved and then taken inside the SDE and run against the real data, later returning the results (as in the [OpenSAFELY](https://github.com/opensafely "OpenSAFELY: A Secure Analytics Platform for NHS Electronic Health Records") model).

 The architecture of the two SDE approaches is different in some aspects, but they will need many of the same components to better meet the RAP requirements that have been discussed previously.  Some of the main considerations when designing an SDE are:

1. **Having an on-premises, trusted package repository:** This will allow your organisation to check and assure the packages (such as python packages from [Pypi](https://pypi.org "The Python Package Index"), [Conda](https://docs.conda.io/en/latest/ "Conda: Package, dependency and environment management for any language"), [Maven](https://maven.apache.org "Apache Maven: A Software Project Management and Comprehension Tool"), etc.) used within the SDE once, after which they could be consumed freely by the SDE users. Users will need a straightforward method of requesting packages to be added to the repository, such as through editing some config file held in a git repository they can access. They will also need to be able to install packages into their working area, such as into their compute cluster / [python virtual environment](https://nhsdigital.github.io/rap-community-of-practice/training_resources/python/virtual-environments/why-use-virtual-environments/), etc. There also needs to be a way for users to be able to promote their code into a package within the on-prem trusted package repository, both from the shared and unshared areas.

2. **Work done needs to be reproducible, and this might include work done outside the environment (such as on another SDE):** We want to encourage the transfer and re-use of code and methods and this will involve the creation of compute clusters, and virtual environments in a reproducible, and automatable manner. For example through using config files in the code repositories (requirements.txt for Python virtual environments, or json files for spark clusters). This might also need analysts to use virtualisation, such as using docker to recreate the operating system setup used in the original work and CI/CD tools need to be available to users, so that they can automate the running of tests.

3. **In those SDEs where users are exposed to the data directly, split users into silos based on their intended use of the data:** This will make it difficult to pass anything between these silos, so there needs to be some way for users to share code between the silos. Without this users cannot reuse the code of their peers and will be forced to duplicate work. Code should be checked to ensure it is non-disclosive (such as using Git hooks, etc.) prior to being moved into this shared space and subsequent changes to this shared code can use the functionality of Git to only check the "delta", or any changes to the code, rather than the whole code again.  Exporting code outside the environment from the shared space should be straightforward as the code is already known to be non-disclosive but the process for users to get their code promoted into the shared area needs to be as simple as possible, preferably using the built in features of tools like GitHub (such as special branches, or releases).

4. **Data must be able to flow between the components of the SDE automatically:** This should be in a machine readable way without human intervention. There should be stops in the process, but these should be related to checks being run, and human approvals processes not simply having a download button you must press to get the data out. Instead, APIs or other machine readable approaches should be used to allow pipelines to be automated and prevent needless manual work.

5. **All users (data scientists, data engineers, analysts, etc.) may need to productionise their code:** This will involve code being run, and output, on a schedule, and then those outputs potentially flowing out to external users (such as in a dashboard). This cannot always rely on human output checkers (such as an hourly, or daily dashboard, showing COVID figures for each CCG in the UK), due to scale and fast turn around of outputs. There needs to be a way to sign-off a codebase, as trusted, so that it is known to produce safe outputs and for this to then be run with elevated permissions, potentially by-passing usual safe-guards for "untrusted" code, and outputting directly (such as in this case to a dashboard). The sign-off process will be the same as productionisation, and should allow finalised, signed-off code to be scheduled and run in a privileged space. It should then be difficult to change without further checks and sign-off (though potentially only of the changes rather than the whole codebase).

6. **Data science work such as machine learning models, needs extra thought:** This may require the creation of a model repository and feature store, both within and cross cutting the working silos of the SDE. Data science work may require different compute, including GPU compute clusters. These should not be dismissed out of hand due to cost, as when used properly, a GPU cluster will do data science calculations more efficiently (in terms of time and money) than CPU only clusters.  Such an approach might also need the ability to compile and install "code adjacent" tools, for example when using the Python library [PyStan](https://pystan.readthedocs.io/en/latest/ "PyStan: A Python Interface to Stan, a package for Bayesian Inference"), which under the hood is calling out to Stan.

7. **Users may require access to a pipeline tool:** This can include tools such as [airflow](https://airflow.apache.org "Apache Airflow"), [make](https://www.gnu.org/software/make/ "GNU Make"), or [Dagster](https://dagster.io/blog/dagster-the-data-orchestrator "Dagster: The Data Orchestrator") which enables steps in a process to be automated and scheduled.

8. **Users will need access to a command line:** Much of the tooling discussed above require command line access, hence the users need access to one, and potentially a unix environment.

9. **Modern code development benefits greatly from using an integrated development environment (IDE):** Tools such as [VSCode](https://code.visualstudio.com/ "Visual Studio Code: Code Editing Redefined."), [RStudio](https://www.rstudio.com/tags/rstudio-ide/ "RStudio IDE") and [PyCharm](https://www.jetbrains.com/pycharm/ "The Python IDE for Professional Developers") make code development faster, less manual, and can lead to higher quality code. It is crucial users can also install relevant extensions, which may need to be hosted in the internal package repository of the SDE.

10. **Changes and restrictions should be documented:** Anything blocked, turned off, removed, altered, etc. from software being used within the SDE needs to be clearly explained to users through documentation about the SDE so that they can adapt their workflows or find alternative approaches to carrying out their tasks.

11. **Users will also need access to a more open environment than an SDE** with many of the tools above, more open access to the internet and less controls is required for work on open data that is not patient level or sensitive data. This is because, though a lot of health data work is on sensitive patient level data, often work is also done on publicly available, or aggregated, non-disclosive data. This open environment needs to have access to an identical package repository, code version control instance, compute etc. as the SDE so that code made in secure environment can be used in the more open environment and vice-versa.

## The Right Capability

> **In an ideal system...**
>
> **Senior leadership will:**
>
> - Understand what is needed for RAP
> - Promote and enable capability development
> - Become comfortable managing RAP-enabled teams
>
> **Platforms colleagues will:**
>
> - Help create platforms that are intuitive and support the application of necessary skills and techniques.
>
> **Analyst leaders (and RAP champions) will:**
>
> - Understand what is needed for RAP
> - Champion RAP through their own work
> - Promote, enable and support capability development in their teams
>
> **Analyst will:**
>
> - Understand what is needed for RAP
> - Pursue development of the skills and techniques necessary for RAP
> - Apply RAP in their work

The [second goal of the cross-government RAP strategy](https://analysisfunction.civilservice.gov.uk/policy-store/reproducible-analytical-pipelines-strategy/#section-9 "Reproducible Analytical Pipelines (RAP) Strategy") states that analysts should have the capability to produce analysis in line with the RAP principles and are supported in doing so.

### Understanding What is Required

As a necessary first step to developing the right capability, leaders (both at senior and more operational levels) and analysts should seek to understand RAP, particularly to understand what skills and techniques are needed. For leaders at all levels, this understanding will help them to understand the current capability position and also the scale of both the time and energy commitment needed for skills development and the potential benefits that that investment would bring. It will help leaders better understand how to manage analysts working under this framework and how they, as managers, can help deliver that change. An understanding of the specifics of RAP will also help during recruitment, enabling managers to prioritise the right kinds of skills and experience in their recruitment decisions.

Analysts should of course also seek to understand what is required for their RAP journey, beginning with a skills audit. A framework should be used for this purpose, such as our [Levels of RAP](Levels_of_RAP.md), as this will help analysts to assess where they currently sit on this framework and what they should focus on next in terms of developing themselves and their pipelines. As noted on the [levels of RAP page](Levels_of_RAP.md), we are not suggesting that you should necessarily use our framework exactly, rather you may wish to adapt it to fit the needs and goals for your own organisation.

Key aspects for both leaders and analysts to understand is that:

- RAP is not just for data scientists: the expectation is that anyone involved in the analysis of data should be pursuing RAP.
- RAP is not simply automation: it includes other aspects such as quality assurance, version control, documentation, dependency management and others.
- RAP is not an all-or-nothing exercise: even just applying some techniques will bring about benefit, and it will be easier to take a more iterative approach to development.
- Although RAP does require an initial investment in time and energy, that will be more than returned through the long term benefits it brings.

Those responsible for developing and maintaining analytical platforms should support this process, understanding analysts' needs to discover what is required of platforms in order that they facilitate the application of RAP.

### Links to Learning Resources

A number of learning pathways might be pursued to help develop the skills needed to apply the techniques outlined in our [levels of RAP](Levels_of_RAP.md). These are listed below.

**Coding:**

- [R and Python courses on the ONS learning hub](https://learninghub.ons.gov.uk/local/catalogue/index.php)
- [R for applied epidemiology and public health](https://epirhandbook.com/en/index.html)

**Version control:**

- [Guide to version control with Git on the NHS RAP Community of Practice](https://nhsdigital.github.io/rap-community-of-practice/training_resources/git/introduction-to-git/)

Whilst the links above provide resources to developing the capability to do RAP within an organisation, this can only be achieved if there is support and time provided for analysts to improve their skills, which will require a culture of learning to be established by team leaders.

## The Right Culture

> **In an ideal system...**
>
> **Senior leadership will:**
>
> - Endorse RAP, a culture of transparency and sharing.
> - Promote RAP and monitor the progress towards the RAP strategy within the organisation.
>
> **Platforms colleagues will:**
>
> - Get behind RAP, and make it easy to do on their platforms.
> - Make platforms that allow the regular exchange of code between analysts, and to the wider world.
> - Embrace a culture of transparency in their own work.
> - Cyber Security and Information Governance must not be used as excuses for not meeting RAP standards. "Security through obscurity" is not sufficient as a security strategy.  
>
> **Analyst leaders (and RAP champions) will:**
>
> - Encourage and support learning and working according to RAP, including adopting a culture of transparency
> - Think across pieces of work, and try and identify areas where similar work is taking place
>
> **Analysts, Data Scientists, and Data Engineers will:**
>
> - Carry out analysis and data pipelines work in line with RAP by default, including sharing and promoting their work and reusing the work of others.

At its heart, RAP is about people - not pipelines.  It is about changing how people think, such as creating reusable components, thinking holistically and not just about your silo, and thinking about colleagues and how if you do a good job and share your code, you save another team time and effort.  RAP is not all or nothing and it is not one-size-fits all.  No team will be able to deliver RAP perfectly, no project will be perfectly RAP.  There will be some projects that are more RAP compliant than others and there will be other teams that are more mature at RAP than others. RAP is a process of continuous improvement, where we provide better health outcomes to the public by being open, learning from each other as part of a community, and create the time and space needed to improve our skills and capabilities.

### Create and Support the Time Needed for Developing Skills

The largest barrier often faced in developing capability for RAP is that of having the time for making those developments. It is therefore essential that leaders recognise the importance of RAP and try wherever possible to create the time and space needed for analysts to develop new skills. It is important to recognise that enabling this skills development, particularly capitalising on opportunities presented by quieter periods, will allow analytical people and systems to become more efficient and robust in the long term. Particularly in the health sector, this will pave the way for a more efficient and effective response to any emerging health threats and pandemics.

Leaders should also be confident and not unduly risk-averse in allowing new ideas to be tried out, to enable analysts to apply the skills they are developing. By having a greater understanding of RAP, leaders will be able to manage their teams' RAP journeys, ensuring development takes place in a way that minimises any potential risk of doing so. A consequence of trying new ideas is that leaders should expect projects to take longer and factor this in.  However, they can justify to senior colleagues any prolonged timelines through the benefits that applying RAP will yield. The next project will be faster, any updates will be faster, and the outputs more trustworthy.

Analysts need to seek out and take up opportunities for development, prioritising in the first instance those skills and techniques that will bring about the greatest benefit to their analytical pipelines. Usually those techniques concern better automation, documentation, quality assurance, and version control.  However, skills need to be continuously updated and whilst leaders should provide the time and space for skill development, analysts are responsible for continuously developing their own skills and identifying their own skills gaps.  People learn in different ways so analysts need to factor in their own learning style as part of this development process.

### Actively Support and Build a Community

RAP can be a big change in process and so it is important to provide effective networks of support. While individual analysts can learn and apply RAP in isolation, it is usually advised that this is done as a community instead. Doing so will both provide better support for individual analysts in the development of skills but also provide better business continuity: if an individual develops at a much faster rate than their team, there is a risk that others may not be able to pick up their work in the event they are unavailable or leave the organisation.

You might also consider having nominated RAP champions. These are named individuals who champion RAP across the organisation, supporting others, and might be connected to wider groups such as the [Government Statistical Service (GSS) RAP Champion Network](https://analysisfunction.civilservice.gov.uk/support/reproducible-analytical-pipelines/reproducible-analytical-pipeline-rap-champions/ "Government Statistical Service (GSS) RAP Champion Network"). RAP Champions can set up seminars, have awards, ask questions, and make themselves available to answer questions. Colleagues need to know they can go to their local RAP champions or to the wider RAP community in your organisation (or beyond) for troubleshooting and advice.  

By actively taking part in the wider RAP community, it is a lot easier to break down silos and build cross-cutting, multi-disciplinary connections with other teams that you can learn from.  By breaking down silos, sharing work and ideas, reusing the work of others, and actively contributing to the community, this will ultimately make any RAP outputs more robust, more efficient, and will positively impact the health of the patients for whom we do analysis.

### Be Open and Transparent by Default

Publishing by default and only withholding code and results by exception form a core part of point 3 of the [Government's Technology Code of Practice (TCoP)](https://www.gov.uk/guidance/be-open-and-use-open-source "Guidance: Be Open and Use Open Source").  Openness is also referred to in point 9 of the [Secure data environment for NHS health and social care data policy guidelines](https://www.gov.uk/government/publications/secure-data-environment-policy-guidelines/secure-data-environment-for-nhs-health-and-social-care-data-policy-guidelines#secure-data-environment-guidelines "Secure data environment for NHS health and social care data - policy guidelines") and the [data saves lives NHS policy paper](https://www.gov.uk/government/publications/data-saves-lives-reshaping-health-and-social-care-with-data "Data saves lives: reshaping health and social care with data") repeatedly refers to open source as part of the transformation the NHS must go through to build a more efficient, transparent and integrated health and social care system. Therefore there is support from the top of government for more open and transparent ways of working.  However, there is still a need for analysts, leaders, platforms colleagues, and cyber security and IG colleagues to move away from a culture of relying on "security through obscurity".

Whilst it may initially be uncomfortable, working in the open will benefit all parts of the organisation.  It will allow researchers to view, reuse, and adapt existing code and enhance shared understanding of how the datasets in these environments are used. This will enable users to easily reproduce previous analysis, which will save time and improve the consistency and accuracy of analytical findings.

From a platforms perspective, no solution, whether open or closed, is guaranteed to be free from cyber attacks.  However, platforms that are open tend to be more secure in the long term because issues are identified quicker and there is a focus on ensuring that all processes and features are tested rigorously before they are made live because they will be open and the reliance of "security through obscurity" is no longer available.

By being open and transparent, you are implicitly inviting others beyond your immediate colleagues to review your code, systems, and analysis. This "many eyes" approach will enable a breadth of views, opinions, skills, and experiences to contribute and benefit from your code and this will ultimately lead to better outcomes for patients, the public, and the NHS.

<!--DL: I think the section below would be better placed in "Why is it Important to Health".  We can then add another bullet point at the top note such as For more information on: What are the risks of NOT doing RAP, see [Why is RAP important to the UK health system"](Why_is_it_important_to_health.md "Why is RAP important to the UK health system") 
-->

## What are the risks of NOT doing RAP

> **Note**
>
> - senior leadership must understand not doing RAP will result in a business which is likely opaque, inefficient, brittle and hard to maintain.
> - platforms colleagues must accept there is risk to the business for platforms not supporting RAP fully and work with the business to meet the platform recommendations made elsewhere in this document
> - analyst leaders understood the risks of not doing RAP and impress these up on their colleagues, both above and below.
> - analysts must embrace RAP, understanding that simply not changing has risks too.

RAP can seem like a lot of work at first, especially to replace a bunch of processes which have more or less been working potentially for decades! However, in addition to the opportunity for benefits from RAP, there are also risks associated with not doing RAP.

**A core risk is that opaque legacy processes often have unquantified risks**: staff move, source data and processes change, and if the existing processes aren't understood and documented well, then there is a chance that the outputs generated aren't being produced exactly as we think. By breaking processes apart into manageable, understood and well-tested chunks, RAP greatly reduces this risk.

**More generally, not embarking upon RAP means your analytical processes will be more brittle**. This is more or less associated with using closed-source software or poorly designed Python/R programs and platforms, where you are "locked in" to certain ways of doing things: when that way of doing things is no longer available, then you've got a problem. Done properly, RAP not only describes the analytical/data process (using free, widely used and portable code) but also the exact libraries, compute, etc. use to run it - meaning the process should be able to run (and be reproduced) indefinitely (given supportive IT/platforms).

**Not following RAP, especially the code version control aspect, leaves you more exposed to issues** such as losing the code, the code getting damaged beyond repair, data centres going down, losing access to shared drives where processes are held, servers crashing or major cyber security incidents. If the process, and everything used to run it, is described in a git repo, you can recover from any of the above - recover the code, roll back some damaging change (and identify how it happened), reclone the code to your systems in case your local shared-drives fail and re set-up your entire pipeline including python libraries, and even computer cluster specs, given entire system failure or compromise.

**Duplicate work, and not getting the full value out of your colleagues' work** is a big risk of not doing RAP. Siloed, opaque processes are inevitably repeated by each team which needs to do the same task - this is wasteful of their time, but also means if one of those teams makes something really good, the rest of the business isn't benefiting from this. By promoting sharing, transparency and portability, RAP makes it easier to reap these benefits.

