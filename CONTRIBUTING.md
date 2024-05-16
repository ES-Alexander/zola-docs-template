# Context
## Overview
This file refers to the process of contributing to this documentation repository.

For contributing to the {SOFTWARE} itself please see the source code repository.

## Repository Structure
1. The documentation infrastructure, theme management, and site generation is handled from the `main` branch
1. The other branches are for content, covering different versions of the software
    - The `latest` and `beta` branches cover the unstable features in development / early testing, and the `X.Y` versioned branches track major and minor stable releases
1. Tags may be made from the stable branches to track patch releases, although this is typically not relevant or necessary

## Release Synchronisation
1. Ideally every released feature and interface should have documentation available, but to avoid confusion documentation should never be merged for features that are not yet available
1. Documentation pull requests should be opened as Drafts until the documented features have been merged into the software codebase, or the relevant version
1. When a new beta release of the software is made, the relevant changes in the `latest` branch get merged or cherry-picked over to the `beta` branch
1. When a new patch release of a stable software is made any changes from the branch tracking that version get merged in to the `main` branch by updating its submodules
    - If relevant, a new tag may also be made from the stable branch
1. When a new major or minor stable release of the software is made, the `beta` branch gets copied into a new branch tracking that version, which then gets added as a submodule in the "content" folder of the `main` branch

# Making a Contribution
Contributions should be made from an external branch.

1. Fork the repository
1. Make a new branch for your changes
1. If making significant changes, clone your fork to your local machine or press `.` to open the repository in an online editor
    - small changes can just be made through GitHub's standard web interface

## Infrastructure Improvements
### Modifying the Theme

### Modifying the Documentation Structure

## Content Improvements
## Documenting a New/Upcoming Feature

## Improving/Adding Documentation for Released Features

## Testing
### Automatic Generation on Pull Requests
### Local Setup
