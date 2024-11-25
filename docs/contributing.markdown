---
layout: default
title: Contribution
nav_order: 9
---

# Contributing to the Toolkit

_Under construction_

## Publishing a new version

To publish a new package, create a single commit with a change to the <a href='https://git.autodesk.com/design-system/weave-wpf/blob/main/.version'>version file</a>. Upon merging the commit to the `main` branch, a build will be triggered and a new NuGet package (with version number from the `.version` file) will be created and deployed to Artifactory. Please also update the version on the badge in README.md (yes, ideally that would be automated, but it is a manual process for now).
