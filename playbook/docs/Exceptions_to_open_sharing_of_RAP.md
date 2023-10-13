# Exceptions to open sharing of RAP

It is much easier to write your analysis code as a RAP from the start of a project than it is to make an existing project reproducible later, because you can address issues and ensure quality as you progress. If you do not do this, you will have to spend significant amounts of time at the end of the project checking your code is of high quality, that the analysis is correct, and that colleagues can recreate the results in the event that you are unavailable or move to a different team and the analysis needs to be repeated.  Adopting the principals of RAP from the beginning means you can:

- Follow best practices from the beginning, such as ensuring documentation is well kept, passwords are not hard coded into the scripts, and code is clear and well structured.

- Allow colleagues to identify parts of your code for reuse which you might not have recognised yourself.

- Enable colleagues to contribute ideas as the project is in progress, for example if colleagues know of existing algorithms and techniques that could help.

Whilst all analysis should be created using a RAP approach, an assessment will be required as to whether the RAP should be made publicly available and openly shared, or if the RAP should only be made available to a specific team or department within an organisation.

## When to Adopt an Open Sharing Approach

The default position should be to use RAP approaches for any analysis with a view that the code, documentation, and results will be openly shared and made publicly available.  Only if an exception is identified should the RAP not be made available publicly.  Openly sharing RAPs can lead to a number of additional benefits such as:

- More robust code and analysis.  As other organisations and the general public can scrutinise the code and the analysis, they may be able to identify areas that can be improved as there is an outside view that provides a different perspective or experience.  

- It may help other researchers. Aside from enabling other health researchers to see what methods are used, openly sharing RAP may help reduce the effort to start analysis.  For example, if a RAP has a verified and validated set of codes to create cohorts of patients with Type II diabetes, the code may be utilised by other research groups or organisations who are studying Type II diabetes.

- Ensure confidence that results are valid and health data is being used for public health benefiting purposes.

- Support any journal or conference manuscript submitted for peer-review as the analytics as well as the results can be reviewed in conjunction with the manuscript, resulting in far more robust conclusions.

Whilst RAP should be made open, there are times when it is desirable for there to be a delay in making code open. Research groups could delay making any RAP documentation and code available until after publication of their work or at the point of publication, to maintain a competitive advantage or have an opportunity to refine code in response to reviewer feedback. RAP code and documentation should also not be released before policy decisions have been released to the public as the analytical code will be linked to sensitive decisions that may be going through a number of reviews and iterations. Regardless of any delays, it is still good practice to ultimately make any analytical code open.

## When Not to Adopt an Open Sharing Approach

Whilst it is of great benefit to ensuring open and robust analysis of healthcare data, it may not always be appropriate to openly publish RAP documentation and code.  

For example:  

- Exposing proprietary or protected intellectual property rights: Some analytics will interface with data structures or systems that are copyrighted and are the intellectual property of the organisation that created them.  If RAP artefacts that interface with items are made open, copyrighted and protected intellectual property rights will be made available to the organisation’s competitors.

- Competitive advantage: The UK is a world leader at developing innovative medicines, devices, and digital tools that save patient's lives. Academic, charitable, and commercial institutions spend billions of pounds annually on these innovations, which can only be made available to patients through robust and rigorous clinical research. Making RAP artefacts that contribute to this research open would prevent organisations from having a competitive advantage and hinder research.

- Protecting patient privacy: Some analytics on health care data may risk identifying patients, such as rare diseases that have small cell counts or analysis on data from patients in consented studies.  If there is a risk that individuals may be identified from the analysis, then the RAP code and artefacts should remain private.

- Data and cyber security considerations: Whilst it is good practice to ensure that passwords, private keys or any type of secret are not hard coded into source code, there are times when this is unavoidable.  For example, the way APIs are called in analytics code may be used by hackers to gain access to systems.  

- During policy formation, where publishing your code could prejudice future decision making.

## Summary

- If you can code in the open from the get go this will save you time later on
- There are circumstances where being too open may cause problems such as;
    - Interfering with bidding and procurement processes
    - Release of IP
    - Release of commercially sensitive info
    - Where release of partial information could create a distorted or biased view of a situation
