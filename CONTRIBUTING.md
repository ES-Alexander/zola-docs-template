# Context
This file refers to the process of contributing to this documentation repository.

For contributing to the {SOFTWARE} itself please see the source code repository.

## Repository Structure
1. The documentation infrastructure, theme management, and site generation is handled from the `main` branch
1. The other branches are for content, covering different versions of the software
    - The `latest` and `beta` branches cover the unstable features in development / early testing, and the `X.Y` versioned branches track major and minor stable releases
1. Tags may be made from the stable branches to track patch releases, although this is typically not relevant or necessary

## Release Synchronisation
1. Documentation contributions should be opened as [Draft pull requests](https://github.blog/2019-02-14-introducing-draft-pull-requests/) until the documented features have been merged into the software codebase, or released in the relevant version
1. Documentation completeness should not prevent software feature merging, but may hold up software releases
    - Ideally every released feature and interface should have documentation available, but to avoid confusion documentation should never be merged for features that are not yet available
    - It is recommended that software pull requests that change an interface or part of the documented code structure be marked with a `docs-needed` [label](https://docs.github.com/en/issues/using-labels-and-milestones-to-track-work/managing-labels), and include a comment about which aspects need to be documented prior to the feature being merged (while the details are still front of mind for the developer)
    - If a software pull request is labelled as `docs-needed`, once a corresponding documentation pull request is merged the feature PR can be re-labelled with a completion status (e.g. `docs-minimal` or `docs-complete`)
    - Beta releases may require that no merged features are labelled with `docs-needed`, and stable releases may require that no included features are labelled with `docs-needed` or `docs-minimal`
1. When a new beta release of the software is made, the relevant changes in the `latest` branch get merged or cherry-picked over to the `beta` branch
    - This is handled by the documentation maintainers
1. When a new patch release of a stable software is made, any changes from the branch tracking that version get merged in to the `main` branch by updating its submodules
    - This typically happens automatically, vai the daily "Update Submodules" Action, but can also be run/done manually by a documentation maintainer
    - If relevant, a new tag may also be made from the stable branch
1. When a new major or minor stable release of the software is made, the `beta` branch gets duplicated into a new branch tracking that version, which then gets added as a submodule in the "content" folder of the `main` branch
    - This is handled by the documentation maintainers

# Making a Contribution
Contributions should typically be made from a unique branch in an external fork.

Specific processes are covered below, but the general process is:

0. Create a GitHub account
1. Fork the repository
1. Make a new branch for your changes
1. Commit your changes to your fork
    - Small changes can just be made through GitHub's standard web interface
    - If making significant changes, press `.` to open the repository in an online editor, or clone your fork to your local machine and push your commits up to your fork once they're complete
1. Create a Draft pull request while work is underway, with a link in the description to any issues it resolves or software feature pull requests it documents
1. Change the pull request to "ready for review" once the underlying software change is merged, the documentation is building successfully, and the new content is ready
1. Fix any requested changes/improvements
1. Once your pull request is merged update the status/labels of any relevant issues / software pull requests, or comment on them if you don't have access to do so

## Content Improvements
### Documenting a New/Upcoming Feature
These can often be found by searching the software repository for pull requests with the `docs-needed` label.

...

### Improving/Adding Documentation for Released Features
Relevant features can typically be found by looking through the public documentation for features with minimal information, and/or searching the software repository for pull requests with the `docs-minimal` label.

...

## Infrastructure Improvements
### Modifying the Documentation Structure


...

### Modifying the Theme
The theme is maintained in an external repository, and included in this one as a submodule. Zola supports overriding theme components via the "templates" folder, which can be useful for initial testing and any specifics required for the software being documented, but if you want to update the upstream theme used:

1. Fork and branch out from [the theme repository](https://github.com/bluerobotics/bluetheme), and make your desired changes in a Draft pull request
1. Fork and branch out from the `main` branch of this repository
1. Add your forked theme as a submodule to the "theme" folder of your branch, with a unique name
1. Change the `theme` variable of `config.toml` to match your theme name
1. Generate the docs, to confirm that the theme changes do not break the build process, and the results look as intended
1. Iterate the theme changes as necessary
1. Mark your theme pull request as ready for review
1. Once the theme changes are merged, ensure the theme submodule in the documentation `main` branch gets updated, along with any relevant changes to the docs configuration, shortcodes, or template
    - The submodule update is generally automatic, via the daily "Update Submodules" Action, but you may need to create a [documentation pull request](#modifying-the-documentation-structure) if there are other changes required

## Testing
### Automatic Generation on Pull Requests
### Local Setup
