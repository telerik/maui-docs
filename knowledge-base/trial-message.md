---
title: Removing the Trial Message after Purchasing a License
page_title: Removing the Trial Message after Purchasing a License
description: I still see the trial message even though I have purchased and installed the commercial license.
type: troubleshooting
published: False
slug: trial-message-commercial-license
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| All versions | Telerik UI for .NET MAUI |[Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova)| 

@[template](/_contentTemplates/common/trial-package-deprecation.md#kb-note-for-upgrades)

## Description

While using a trial license, a trial message is rendered over the components and you see a popup window:

![Telerik .NET MAUI Trial Message](images/trial-message.png)

If you have a commercial license, but you still see the trial message:

1. Ensure that the licensed package is referenced in the project (`Telerik.UI.for.Maui` instead of `Telerik.UI.for.Maui.Trial`).

1. Uninstall any installed trial versions from the machine.

1. If you have created local NuGet feeds, ensure they do not contain Trial versions of our packages.

1. <a href="https://docs.microsoft.com/en-us/nuget/consume-packages/managing-the-global-packages-and-cache-folders#clearing-local-folders" target="_blank">Clean the NuGet packages</a> on the machine.

1. Clean the projects.

1. Delete the `bin` and `obj` folders where packages and assemblies may be cached.

1. Re-build your project.