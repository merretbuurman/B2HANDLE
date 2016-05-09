=======================
B2Handle Release policy
=======================

General policy
==============

For the B2Handle library we follow the following release policy:

We implement short release cycles. Every change to the code leads to a new minor release (e.g. 1.0.x). More significant changes lead to a major release (e.g. 1.x.y). Changes such as typos or minor improvements of the documentation will not lead to a new release be included in the next minor or major release.

Branches
========

B2Handle library has two branches, master and devel. Master always contains the most recent release. All changes are pushed to devel, and if the tests pass, they are merged into master and the next release is announced.

To-Do-List for releases
=======================

Before a release:

- A pull request was made by a developer and reviewed/merged to devel by an admin
- The unit tests pass (continuous integration)

To make a release:

- Check test coverage for the code - is the new/changed code covered by unit tests?
- Update the setup.py (on devel, so this change will be included in both branches)

  - Increase the version number
  
- Merge the devel branch into master branch
- Update the setup.cfg (on master, so this change is included in master branch only):

  - Comment out the ".dev" tag (in order to make sure the ".dev" tag is present in the devel branch, but commented out in the master branch)
  
- Build an egg (setup.py bdist) and a source distribution (setup.py sdist)
- Make a GitHub release based on the last commit in master. Include changes and the two builds created in the last step.
