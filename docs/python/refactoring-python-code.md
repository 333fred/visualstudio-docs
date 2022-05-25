---
title: Refactor Python code
description: Visual Studio makes it easy to refactor Python code by renaming identifiers, extracting methods, adding imports, and removing unused imports.
ms.date: 05/24/2022
ms.topic: how-to
author: rjmolyneaux
ms.author: rmolyneaux
manager: jmartens
ms.technology: vs-python
ms.custom: devdivchpfy22
ms.workload:
  - python
  - data-science
---
# Refactor Python code

 [!INCLUDE [Visual Studio](~/includes/applies-to-version/vs-windows-only.md)]

Visual Studio provides several commands for automatically transforming and cleaning up your Python source code:

- [Rename](#rename) renames a selected class, method, or variable name.
- [Extract method](#extract-method) creates a new method from the selected code.
- [Add import](#add-import) provides a smart tag to add a missing import.
- [Remove unused imports](#remove-unused-imports) removes unused imports.

## Rename

::: moniker range="<=vs-2019>"

1. Right-click the identifier you wish to rename and select **Rename**, or place the caret in that identifier and select the **Edit** > **Refactor** > **Rename** menu command (**F2**).
1. In the **Rename** dialog that appears, enter the new name for the identifier and select **OK**:
:::image type="content" source="media/code-refactor-rename-1.png" alt-text="Screenshot of Rename prompt for new identifer name.":::

1. In the next dialog, select the files and instances in your code to which to apply the renaming; select any individual instance to preview the specific change:
:::image type="content" source="media/code-refactor-rename-2.png" alt-text="Screenshot of Rename dialog to select where to apply the changes.":::

1. Select **Apply** to make the changes to your source code files. (This action can be undone.)

::: moniker-end

::: moniker range=">=vs-2022>"

1. Right-click the identifier you wish to rename and select **Rename**, or place the caret in that identifier and select the **Edit** > **Refactor** > **Rename** menu command (**F2**), or select the identifier and press **Ctrl+R**.
1. In the **Rename** dialog that appears, enter the new name for the identifier and press **Enter**:
:::image type="content" source="media/vs-2022/code-refactor-rename-1.png" alt-text="Screenshot of Rename prompt for new identifer name.":::

::: moniker-end

## Extract method

::: moniker range="<=vs-2019>"

1. Select the lines of code or the expression to extract into a separate method.
1. Select the **Edit** > **Refactor** > **Extract method** menu command or type **Ctrl**+**R** > **M**.
1. In the dialog that appears, enter a new method name, indicate where to extract it to, and select any closure variables. Variables not selected for closure are turned into method arguments:
:::image type="content" source="media/code-refactor-extract-method-1.png" alt-text="Screenshot of Extract method dialog.":::

1. Select **OK** and the code is modified.
:::image type="content" source="media/code-refactor-extract-method-2.png" alt-text="Screenshot showing effect of extracting a method.":::

::: moniker-end

::: moniker range=">=vs-2022>"

1. Select the lines of code or the expression to extract into a separate method.
1. When you place the caret on code sample, Visual Studio provides a smart tag (the wrench icon to the left of the code).
1. In the dialog that appears, select **Extract** for closure to be turned into method arguments:
:::image type="content" source="media/vs-2022/code-refactor-extract-method-1.png" alt-text="Screenshot of Extract method dialog.":::

1. Select **OK** and the code is modified.
:::image type="content" source="media/vs-2022/code-refactor-extract-method-2.png" alt-text="Screenshot of Effects of extracting a method.":::

::: moniker-end

## Add import

When you place the caret on an identifier that lacks type information, Visual Studio provides a smart tag (the light bulb icon to the left of the code) whose commands add the necessary `import` or `from ... import` statement:

::: moniker range="<=vs-2019>"

:::image type="content" source="media/code-refactor-add-import-1.png" alt-text="Screenshot of Add import smart tag.":::

::: moniker-end

::: moniker range=">=vs-2022>"

:::image type="content" source="media/vs-2022/code-refactor-add-import-1.png" alt-text="Screenshot of Add import smart tag.":::

::: moniker-end

Visual Studio offers `import` completions for top-level packages and modules in the current project and the standard library. Visual Studio also offers `from ... import` completions for submodules and subpackages as well as module members. Completions include functions, classes, or exported data. Selecting either option adds the statement to at the top of the file after other imports, or into an existing `from ... import` statement if the same module is already imported.

:::image type="content" source="media/code-refactor-add-import-2.png" alt-text="Screenshot showing result of adding an import.":::

Visual Studio attempts to filter out members that aren't defined in a module, such as modules that are imported into another but aren't children of the module doing the importing. For example, many modules use `import sys` rather than `from xyz import sys`, so you don't see a completion for importing `sys` from other modules even if the modules are missing an `__all__` member that excludes `sys`.

Similarly, Visual Studio filters functions that are imported from other modules or from the built-in namespace. For example if a module imports the `settrace` function from the `sys` module, then in theory you could import it from that module. But it's best to use `import settrace from sys` directly, and so Visual Studio offers that statement specifically.

Finally, if something would normally be excluded but has other values that would be included (because the name was assigned a value in the module, for example), Visual Studio still excludes the import. This behavior assumes that the value shouldn't be exported because it's defined in another module, and thus another assignment is likely to be a dummy value that is also not exported.

## Remove unused imports

When writing code, it's easy to end up with `import` statements for modules that aren't being used at all. Because Visual Studio analyzes your code, it can automatically determine whether an `import` statement is needed by looking at whether the imported name is used within the scope, after the statement occurs.

::: moniker range="<=vs-2019>"

Use right-click anywhere in the editor and select **Remove Imports**, which gives you options to remove from **All Scopes** or just the **Current Scope**:
:::image type="content" source="media/code-refactor-remove-imports-1.png" alt-text="Screenshot of Remove imports menu.":::

::: moniker-end

::: moniker range=">=vs-2022>"

When you place the caret on the import that lacks usage, Visual Studio provides a smart tag (the light bulb icon to the left of the code) whose commands remove the necessary `Remove unused import` statement:
:::image type="content" source="media/vs-2022/code-refactor-remove-imports-1.png" alt-text="Screenshot of Remove imports menu.":::

::: moniker-end

Visual Studio then makes the appropriate changes to the code:
:::image type="content" source="media/code-refactor-remove-imports-2.png" alt-text="Screenshot showing effects of removing imports.":::

> [!Note]
> Visual Studio doesn't account for control flow. Using a name before an `import` statement is treated as if the name was in fact used. Visual Studio also ignores all `from __future__` imports, imports that are performed inside of a class definition, as well from `from ... import *` statements.
