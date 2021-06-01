## Stages of Review 

Full Instructions can be found on confluence [Git and Contributing to a Repo](https://sabiogroup.atlassian.net/wiki/spaces/SOF/pages/13663963041/Git%2Band%2BContributing%2Bto%2Ba%2BRepo) 

Code Review documentation [Code Review](https://sabiogroup.atlassian.net/wiki/spaces/SOF/pages/10925015501/Code+Review)

#### Overview:

#### Dependencies:
*Describe anything blocked or related to this PR, i.e other PR link*

## Design 
Determine on size and delete where not used. Large Features typically take a sprint or more to develop and test. 
Smaller Features or Bugs typically can be completed within a sprint or a minimal amount of effort. 

#### Type of Change 

*What types of changes does your code introduce? Put an `x` in all the boxes that apply:*
- [ ] Bug fix (non-breaking change which fixes an issue)
- [ ] New feature (non-breaking change which adds functionality)
- [ ] Breaking change (fix or feature that would cause existing functionality to change)

  *Description:*

#### Large Feature

- [ ] Technical Design *(could include the following Confluence Page detailed design, output from a design session or additional supporting documentation)*
- [ ] Test Plan *(include Link to the Verification Test Plan in XRay within Jira)

*Confluence Page:* [Link](https://)
*Test Plan:* [Link](https://)
*Supporting Info:* [Link](https://)

#### Minor or Bugs

- [ ] Technical Info *(could include the following detail in Jira story or supporting documentation)*
- [ ] Test Info *(include Link to the associated Test within Jira)

*Jira Ticket(s):* [Link](https://)
*Test Issue:* [Link](https://)

## REVIEWER SIGNOFF

- [ ] Reviewer has approved the Draft Pull Request 
*mark request as WIP*


## Validations:

Have the changes made affected:

- [ ] PCI Compliance
- [ ] API Versioning  
- [ ] Data Persistence
- [ ] Configuration Options

If any checkboxes are marked please, update the following sections on the changes :

#### PCI Compliance

#### API Versioning

#### Data Persistence

#### Configuration Options

## Testing:

- [ ] Tested locally
- [ ] Completed Verification Test Plan
- [ ] Tested on a staging environment 
- [ ] Updated Documentation


## Review Checklist 
*Prior requesting a review with the reviewer please ensure the checklist below is completed*
*What types of changes does your code introduce? Put an `x` in all the boxes that apply:*

- [ ] My code follows the style guidelines of this project (*if available*)
- [ ] I have performed a self-review of my own code
- [ ] I have commented my code, particularly in hard-to-understand areas
- [ ] I have made corresponding changes to the documentation
- [ ] My changes generate no new warnings
- [ ] I have added tests that prove my fix is effective or that my feature works
- [ ] New and existing unit tests pass locally with my changes
- [ ] Any dependent changes have been merged and published in downstream modules
