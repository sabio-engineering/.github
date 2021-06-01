## Stages of Review 

Full Instructions can be found on confluence [Git and Contributing to a Repo](https://sabiogroup.atlassian.net/wiki/spaces/SOF/pages/13663963041/Git%2Band%2BContributing%2Bto%2Ba%2BRepo) 

Code Review documentation [Code Review](https://sabiogroup.atlassian.net/wiki/spaces/SOF/pages/10925015501/Code+Review)

#### Overview:

#### Dependencies:
*Describe anything blocked or related to this PR, i.e other PR link*

## Design 
Determine on size and delete where not used. Large Features typically take a sprint or more to develop and test. 
Smaller Features or Bugs atypically can be completed within a sprint or a minimal amount of effort. 

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

Have the changes made affected:

- [ ] Authentication pathways
- [ ] Call recording functionality
- [ ] Call escalation to agent functionality
- [ ] Functionality around Google BigQuery
- [ ] Functionality around Google's DLP API

If any checkboxes are marked please:
- Check [here](http://github.com/0xRadi/OWASP-Web-Checklist) to ensure you have tested
  appropriately. Select points which are relevant to the change.
- Ensure git commit messages including changes to the above contain a thorough
  description of the change along with any potential impact and the testing
  effort around it.
- Include testing efforts for PCI compliance in the validation section along with
  a link to your QA checksheet if required.
- If your change is 'significant' in scale or complexity, or if you have ticked any
  of the PCI controlled changes above, you may need to conduct a vulnerability scan
  or a penetration test.  You should contact Vimal Goricha (vgoricha@sabiogroup.com)
  to determine if this is required and arrange for it to be carried out

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

#### Post deploy validations:

-
-

#### Downtime Envisaged:

Kubernetes controlled deployment should ensure no downtime except in these cases:

- [ ] Migrations required (Time for migrations to run)


## Deployment
#### Go Live Plan:

- Deploy code from master to production
- Watch CircleCi pipeline and accept the push to production if tests pass
- Run validation process

#### Rollback Plan:

  - Rollback to previous version
    (version will _increment_)
  - Ensure all works as needed, no errors triggered

#### Risks:

-
-

## Monitoring:

#### Who:

-

#### Immediately:

Using either `kubectl` or `rube` monitor:
  - cluster behavior in Grafana while deploying
  - pods spinning up in cluster

#### 1 hour after release:

Manually check:
  - production logs
  - sentry channel
  - pod state in cluster


#### Continuously:

- Manually Check Sentry logs
- Check state of cluster
- Request client feedback

## Commands
#### Change cluster
Ensure the cluster is _airline-production_ for deploy and rollback.

```
kubectl-ctx gke_airline-production_europe-west2_airline-production-gke-cluster
```
or
```
rube enter production
```

#### Rollback
Only rollback to a stable deployment.

```
helm history airline-analytics-api -n airline-production
helm rollback <previous version> airline-analytics-api -n airline-production
```

#### Logging
Watch a pods log output:

```
kubectl get pods -n airline-production
kubectl logs <pod_name> airline-analytics-api -n airline-production
```
or
```
rube logs analytics
```
(choose a pod).


#### Grafana Access (Metrics)
Expose the cluster Grafana instance on a local port:

```
kubectl port-forward svc/prometheus-operator-grafana 8080:80 -n core
```
or
```
rube metrics
```

and go to `locahost:8080` in your browser.
