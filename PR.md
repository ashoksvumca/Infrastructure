### Before creating a pull request:


- [ ]  **PR with any merge commits, fail**
```diff
- A PR with any merge commits will fail PR validation, even if the local validation passes. 
- Be sure to not have any merge commits in your PR. If your PR has any merge commit, 
- please close it and open a new PR without any merge commits.
```
- [ ]  **Run local validation**
See instructions [here].  
***Note:*** The validator only validates the syntax and syntactically correct templates may still be rejected by Spinnaker.

- [ ]  **Do not remove keys in application.j2**
Spinnaker treats all updates to application JSONs strictly as a delta. It cannot determine how to treat keys that are present in its current JSON but missing from the incoming JSON.  Adjust the value of a key instead of removing it.

- [ ]  **Add the key in application.j2 if it was added/enabled on the GUI**
A manual change in the Application on the GUI may add a key in its JSON.  Even if the change is subsequently undone, the key stays (though its value is changed).  Be sure to also add the key in the application.j2 with the desired value.

### PR Approval via ACL Authorization file:

**NOTE: Service owners need to create 'acl.yaml' file  authorizing their team or individual approvers for their PRs.
Please see for details**

If the change affects only your own pipelines, then as long as your team is part of 'acl.yaml' (see note above),  validate.sh is successful and above steps are followed, you can get a colleague to approve your PR by going to the 'Files changed' tab of the PR and clicking on the 'Review Changes' button on the top right corner of the page and commenting on the PR with an '**Approve**' or '**Approved**' comment string (not case-sensitive).


#### NOTE: SELF-APPROVAL WAS DISABLED ON 2020-02-18!
> For details see: 
```

