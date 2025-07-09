
This document describes a short process to effectively use GitHub to achieve the following main goals:

- Proposing a change.
- Reporting a bug.
- Making improvement suggestions.

Note

The intent of this document is not to teach the use of GitHub. The document just gathers some basic rules for a quick reference.

# Create issues
You use the Issues mechanism to report problems, bugs and suggest general improvements. This is for both internal and external contributors.

This approach is useful if you want to:

Flag items that cannot be addressed by a single PR.
Request that may need to be analyzed to find the proper course of action.
Record information to put on backlog.
Please, include relevant details the rest of the community needs to understand in order to discuss the issue effectively.

For more information, see [Creating an issue](https://docs.github.com/en/issues/tracking-your-work-with-issues/creating-an-issue).

# Create a fork
You fork a repository to propose changes to the original repository. This is the recommended practice for community contributions.

For more information, see [Fork a repo](https://docs.github.com/en/get-started/quickstart/fork-a-repo).

If you use the Github desktop app, see [Cloning and forking repositories fromGitHub Desktop](https://docs.github.com/en/desktop/contributing-and-collaborating-using-github-desktop/adding-and-cloning-repositories/cloning-and-forking-repositories-from-github-desktop).

It's good practice to regularly sync your fork with the original repository. For more information, see [Syncing a fork](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/syncing-a-fork).

# Create a Pull Request
You can make any changes to a fork, including making branches and opening pull requests. If you want to contribute to the original repository, you can submit a pull request.

For more information, see [Creating a pull request from a fork](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request-from-a-fork).

If you use the Github desktop app, see [Creating an issue or pull request](https://docs.github.com/en/desktop/contributing-and-collaborating-using-github-desktop/working-with-your-remote-repository-on-github-or-github-enterprise/creating-an-issue-or-pull-request).

# PR Review Phase
Pull requests generally are open to community review and get accepted as-is or with requested changes. The more impactful the changes, the more review activity is to be expected.

# PR Accept Phase
Once a PR has received sufficient review and concerns are satisfied, a designated [Maintainer](https://github.com/InfraDDS/Policies/blob/main/MAINTAINERS.md) with sufficientpermissions can accept the Pull Request.

# Directly Editing Artifacts
Contributors with write access permission or higher have rights to directly edit documents and push changes. This practice should be used very sparingly, and only in the draft stages of documents, or to make trivial changes in documents already in use.

# Warning

Direct edits (without proper review phases) to "released" documents short-circuits the normal community process and can result in breaking changes and significant disruption, resulting in potential impact to downstream consumers.

# Use checklists for large issues or PRs
When working on a complex Issue or PR, it is often preferable to use a checklist within one Issue or PR. This avoids the use of multiple Issues or PRs that could be difficult to track.

Especially with an issue related to a feature, all of the pull requests used to implement the feature can refer to the same issue. The progress made can be easily understood by looking at which boxes are checked and which are not. The status is found in one place.

The checklist system is also useful to track work, such as a progress summary, when reviewing lists of open Issues.

A contributor would enter the checklist in the comment when creating the Issue or PR. To create a checklist, please use a markdown format similar to the one shown in the example below.

- [x] Fix TOC
- [x] Add checklist section

Note: Any work item is check-marked with x when the related tasks are completed.

# Tools
[GitHub desktop](https://desktop.github.com/)

[How to Use the Github Workflow](https://www.youtube.com/watch?v=8UguQzmswC4)

[Visual studio code](https://code.visualstudio.com/)

[Drawing tool: diagrams.net](https://www.diagrams.net/)
