
# gitflow
This is the Git flow that I mostly follow in my personal or profession projects

		Git branching structure

**Master Branch**

 “master” branch should be a production ready branch and it always contain code in a very stable form. Developers should not be allowed to directly directly push to this branch except through pull request (PR). 


**Develop Branch**

 “develop” branch is copy of code in “master” branch. This branch is usually not as stable as master branch. No developer should be allowed to directly push to this branch except through pull request (PR). This branch should not be deleted even after the merging code to master branch.

**Feature Branches**

May branch off: develop
Merged back: develop
Naming conventions: feature/s1_asif_signup_UI

If you want to work on new functionality, create a new branch from develop branch. Naming convention should be feature/<sprint_number>_<firstname>_<feature_name>, for instance, if you are working on login feature, it would be feature/asif_signup_ui. The scope of such type of branches are limited because eventually they will be removed after merging with develop branch. 

**Release branches**

May branch off: develop
Merged back: develop, master
Naming conventions: release/s1_asif_1.7

This branch is created to prepare a new production release. We can fix bugs, prepare meta data for release (version number, build number, build date, etc.) Once we have created a new branch from develop, now other developers can start creating feature branches from develop and start pushing code to it.

When this release branch is ready for a real release, this should be merged into master and develop as well. Remember every commit or merge to master branch is a new release by definition. Also, this commit on master branch should be tagged for easy references. Next, this release should be merged in develop branch so that future releases also contain these bug fixes. 


After merging with master and develop, release brach “release/s1_asif_1.7” should be deleted.
Next, that commit on master must be tagged for easy future reference to this historical version.

**Hotfix branches**

May branch off: master
Merged back: develop, master
Naming conventions: hotfix/s1_asif_1.7.1

Whenever there is an issue in live branch or production build, we will create this branch. For example, current release release/s1_asif_1.7 on live server is up and running and there came a severe bug. But changes on develop are yet unstable. So we will create a separate branch from master tag with bumped up version number (hotfix/s1_asif_1.7.1)

These branches are just like release branches but unplanned. When a critical bug in a production version must be resolved immediately, a hotfix branch may be branched off from the corresponding tag on the master branch that marks the production version. The purpose of this is that work of other team members can continue while another develop is preparing a quick production fix.

After fixing the bug, merge this branch with master and develop branch as well so that it can be part of this release as well. After merge tag the release as well. 

The one exception to the rule here is that, when a release branch currently exists, the hotfix changes need to be merged into that release branch, instead of develop because eventually, when a release branch is finished, it will be merged into develop branch. Once it is merged, this branch should be deleted.

**Pull Request**

When you have completed a feature, create a Pull Request with develop branch and assign it to a reviewer. A reviewer could be your team member or technical lead. Only should merge your Pull Request. No PR should merged until it is reviewed by someone else. Once a feature branch is reviewed and merged, it should be deleted both locally and remotely.

**To avoid conflict**

Make sure that you regularly update your branch with parent branch to avoid conflicts.


**Acknowledgements:**

https://nvie.com/posts/a-successful-git-branching-model/

