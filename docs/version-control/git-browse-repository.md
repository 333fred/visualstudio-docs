---
title: Browse a repo in Visual Studio
titleSuffix: ""
description: Browse any Git repository in Visual Studio using the Git Repository window.
ms.date: 11/1/2021
ms.topic: how-to
author: Taysser Gherfal
ms.author: tagherfa
ms.manager: anthc
ms.prod: visual-studio-windows
ms.technology: vs-ide-general
---
# Browse Git repositories in Visual Studio

The Git Changes window provides a seamless way to interact with Git while coding without having to switch away from your code; however, there are times when it makes more sense to focus on your Git repository. For example, you might need to get a good picture of what your team has been working on or maybe compare two commits to investigate a bug.
## Browse local and remote branches

To get started, open the Git Repository window by clicking **Git Repository** on the View menu. You can also access the Git Repository window by clicking on the **outgoing/incoming** links in the Git changes window and the status bar.

:::image type="content" source="media/vs-2022/Git-Repository-Browse.png" alt-text="The anatomy of the Git Repository Window":::

The Git repository window contains 3 main sections:
1. **Branches:** Git empowers users to multi-task and experiment with their code through branches. If you are working on multiple features at the same time or if you would like to explore ideas without effecting your working code, branching can be very helpful. 
1. **Git Graph:** The Git graph section visualizes the state of your branch. It has three different sections: incoming, outgoing and local history. The incoming section shows incoming commits that your team has been contributing, the outgoing section shows your local commits that you still haven’t pushed, and the local history shows the rest of commits tracked by your local repository.
1. **Commit Details:** clicking any commit on the Git Graph section opens the commit details UI showing the details of commits. You can check the changes introduced by commits by clicking on them which would show a difference. For example, on the previous screenshot you can see that we are viewing the changes that one commit introduced to the Files.csproj file

You can browse any local or remote branches without having to switch your branch and when you find a commit that you would like to focus on, just click the **Open in New Tab** button to open the commit in a different tab or maximize it in a different screen as shown here.

:::image type="content" source="media/vs-2022/Git-Repository-OpenNewTab.png" alt-text="New Tab":::

:::image type="content" source="media/vs-2022/Git-Repository-DetailsTab.png" alt-text="Commit details tab":::

> [!TIP]
> To display your commit in full screen, detach your commit tab and maximize the commit window using the **maximize button**. You can also select your favorite diff configuration by clicking the **Diff Configuration Gear**. 
:::image type="content" source="media/vs-2022/Git-Repository-CommitDetails-FullScreen.png" alt-text="Full Screen Commit Details with diff configurations":::

## Compare Commits
To compare between any two commits in your branch, use the **Ctrl key** on your keyboard to select the two commits you would like to compare. Then right click on one of them and chose the **Compare Commits** option.

:::image type="content" source="media/vs-2022/Git-Repository-CompareCommitsOption.png" alt-text="Compare between two commits":::

:::image type="content" source="media/vs-2022/Git-Repository-CompareCommitsUI.png" alt-text="Compare Commits UI":::

> [!TIP]
>Similar to Commit Details, you can use the **Open in New Tab** button to open the Compare Commit UI in a different tab or maximize it in a different screen.

## Next steps

To continue your journey, visit the [Manage Git Repositories in Visual Studio](git-manage-repository.md) page.

## See also

- [The Git experience in Visual Studio](../ide/git-with-visual-studio.md)