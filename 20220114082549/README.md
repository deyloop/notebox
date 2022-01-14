# Maintain a local `git` Repository, Even if the rest of your Team does not

When working in a collaborative project where part of your team is
either not familiar with Version Control Systems like `git` or they
refuse to use such tools for some reason, it can be a hassle to
incorporate changes made by other team members into the copy of files
that you are working on. 

Maintaining a `git` repository of the files at your end helps in
collaboration even in this case.

When upstream changes are to be merged with your local version, which
may have your own changes made locally, you can 

1. Make a commit, saving your local changes.
1. Make a new branch (`upstream`)
1. Replace your local files with the updated files received from your
   colleagues. In this new branch 
1. A `git diff` will now highlight what is different between your
   version and the upstream version. 

   At this point you can focus on integrating the changes by hand.
1. Make a commit with these upstream changes
1. Attempt to merge the `upstream` branch into the parent branch. 

   This will give you a merge conflict if things are not right, giving
   you another opportunity to integrate changes.
1. Continue working with the merged version.

Tags:

    #permanent-note #version-control #collaboration #team-work
