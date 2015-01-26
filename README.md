# General Info
General Info about how to use the MultirotorGeeks github organization for sharing and collaborating on projects.

Right now the repositories in this organization are open source.  However, if we ever reach a point where we are generating IP, we can upgrade the account to allow private repositories.

# Useful Links for general Git info

[Where To Download Git For Your Computer] (http://git-scm.com/downloads)

[Git Documentation](http://git-scm.com/doc)

[Git Branching and Merging Info] (http://git-scm.com/book/en/v2/Git-Branching-Basic-Branching-and-Merging)

[Very Useful Git Tutorials] (https://www.atlassian.com/git/tutorials)

[Feature Branch Workflow] (https://www.atlassian.com/git/tutorials/comparing-workflows/feature-branch-workflow)

[Info about using the Git tools built into the Eclipse IDE] (http://wiki.eclipse.org/EGit/User_Guide)

# Other Useful Links for the Multirotor Geeks Organization

[Our Website] (http://multirotorgeeks.github.io/)

[Our Private Facebook Group] (https://www.facebook.com/groups/542875275814916/)

[Our Repositories] (https://github.com/MultirotorGeeks)

# Recommended Workflow for Multirotor Geeks

This section is where we will write down descriptions of how our workflow will happen.  Currently, the recommended workflow is the standard [Feature Branch Workflow] (https://www.atlassian.com/git/tutorials/comparing-workflows/feature-branch-workflow).  We all have a say in the workflow, so feel free to open discussions about this, so we can improve it to fit our needs.

In this workflow, any new development for a repository is done in a dedicated branch (with descriptive name such as PaulDevelopingLibraryX) instead of the master branch.  This dedicated branch can be pushed upstream from anybody's local repository to the [github] (https://github.com/MultirotorGeeks) repository as often as desired.  Then, once the development is complete, a [Pull Request] (https://www.atlassian.com/git/tutorials/making-a-pull-request) is issued by the person who worked on that branch.  [This Help Page] (https://help.github.com/articles/using-pull-requests/) describes how to use pull requests specifically on the github website.  This essentially requests that the development branch gets merged into the master branch on github.  All members of the Multirotor Geeks organization can view the pull request and the files in the development branch, and make comments as fit.  Once it is agreed that the branch is ready, it will then be merged into the master branch on [github] (https://github.com/MultirotorGeeks).  Then, each person can Fetch the newly updated master branch from upstream into their local copy of the repository, and continue working as before on their respective branches.  Git is very good about merging multiple branches together.  Note that pull requests are used to request merging from a development or feature branch into the master branch, but not necessary for vice versa.

At this point, guidelines are not set about how to reach agreement for when a branch is ready to be merged once a pull request has been issued.  Since we are all intelligent people, I think we can all just do as we see fit on a case by case basis.  If the branch you are wanting to merge is relatively independent of other people's work, or if it is fairly simple, you can go ahead and approve your own pull request and go ahead and do the merge.  If the branch adds a complicated set of features, or if it is highly dependent on what others may be doing, it is recommended to give others a bit of time to look it over first.

If you are just adding documentation, help files, readmes, etc to the repository, it is probably acceptable to just push those straight to the master branch without requiring a separate feature or development branch first.

Many of the basic Git functions can be performed from directly within the Eclipse IDE.  See [This Website] (http://wiki.eclipse.org/EGit/User_Guide) for a user guide on how to use those tools.  At this point, I believe everything in our workflow (for eclipse projects) can be done from within Eclipse, except the pull requests (which are done from the github website).  For any projects or files created outside Eclipse, the standard [Git Bash or Git Gui programs] (http://git-scm.com/downloads) work great.

# What to put in the repositories?

We can create as many public repositories in this group as we want!  In each repository, it is recommended that we use the [.gitignore](.gitignore) and [.gitattributes](.gitattributes) files which are provided at the top level of this [GeneralInfo repository](https://github.com/MultirotorGeeks/GeneralInfo).  It is also highly recommended that each top level repository directory and each project directory contains a readme file of some sort, which describes the repository or project.  For project readme files, it should also describe how to set up and use the project.

The main type of files to include in the repository are source files (*.c, *.cpp, *.h, *.java, *.m, *.mdl, *.brd, *.sch, *.dxf, etc).  Users are also encouraged to include pdf, word, html, or other forms of documentation in the repository where helpful.  I believe that videos and photos can also be included.

By default, all types of software binary files and built project outputs are ignored, as well as user-specific project configuration files.  This allows us to all work with our own project settings without interfering with one another through the course of pushing and pulling.

When a particular project reaches a point where it's binary output is ready to publish to the repository, those files can be manually forced to be included in the repository using the command git add -f <filename>.  This way, we only include static libraries, hex outputs, etc. which have been determined ready.  It also helps prevent accidentally including garbage files in the repository.

For project configuration files (such as the .project and .cproject files or the .metadata folder in eclipse), it is recommended that those remain ignored so they stay out of the master branch of the repository.  If any user wishes to back up their .project, .cproject, .metadata or other workspace settings in the repository, they can create a new branch of that repository with a descriptive name (such as PaulProjectSettings), and force inclusion of the files in that branch only (using git add -f <filename>).  This branch should not be merged with the master branch.  Other users may pull from this particular branch if they want to attempt importing project settings or other metadata.  I haven't yet tried to see if this works.