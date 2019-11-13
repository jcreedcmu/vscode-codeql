# CodeQL extension for Visual Studio Code

This project is an extension for Visual Studio Code that adds rich language support for [CodeQL](https://help.semmle.com/codeql) and allows you to easily find problems in codebases. In particular, the extension:

* Enables you to use CodeQL to query databases generated from source code.
* Shows the flow of data through the results of path queries, which is essential for triaging security results.
* Provides an easy way to run queries from the large, open source repository of [CodeQL security queries](https://github.com/Semmle/ql).
* Adds IntelliSense to support you writing and editing your own CodeQL query and library files.

## Quick start overview

The information in this `README` file describes the quickest way to start using CodeQL.
For information about other configurations, see the separate [CodeQL help](https://help.semmle.com/codeql/codeql-for-vscode.html).

**Quick start: Installing and configuring the extension**

1. [Install the extension](#installing-the-extension).
1. [Check access to the CodeQL CLI](#checking-access-to-the-codeql-cli).
1. [Clone the CodeQL starter workspace](#cloning-the-codeql-starter-workspace).

**Quick start: Using CodeQL**

1. [Import a database from LGTM.com](#importing-a-database-from-lgtmcom).
1. [Run a query](#running-a-query).

-----

## Quick start: Installing and configuring the extension

### Installing the extension

The CodeQL extension requires a minimum of Visual Studio Code 1.39. Older versions are not supported.

1. Install and open Visual Studio Code.
1. Open the Extensions view (press **Ctrl+Shift+X** or **Cmd+Shift+X**).
1. At the top of the Extensions view, type `CodeQL` in the box labeled **Search Extensions in Marketplace**.
1. Locate the CodeQL extension and select **Install**. This will install the extension from the [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=github.vscode-codeql).

### Checking access to the CodeQL CLI

The extension uses the [CodeQL CLI](https://help.semmle.com/codeql/codeql-cli.html) to compile and run queries. The extension automatically manages access to the CLI for you by default (recommended). To check for updates to the CodeQL CLI, you can use the **CodeQL: Check for CLI Updates** command.

If you want to override the default behavior and use a CodeQL CLI that's already on your machine, see [Configuring access to the CodeQL CLI](https://help.semmle.com/codeql/codeql-for-vscode/procedures/setting-up.html#configuring-access-to-the-codeql-cli).

If you have any difficulty with CodeQL CLI access, see the **CodeQL Extension Log** in the **Output** view for any error messages.

### Cloning the CodeQL starter workspace

When you're working with CodeQL, you need access to the standard CodeQL libraries and queries.
Initially, we recommend that you clone and use the ready-to-use starter workspace, https://github.com/github/vscode-codeql-starter/.
This includes libraries and queries for the main supported languages, with folders set up ready for your custom queries. After cloning the workspace (use `git clone --recursive`), you can use it in the same way as any other VS Code workspace—with the added advantage that you can easily update the CodeQL libraries.

For information about configuring an existing workspace for CodeQL, [see the documentation](https://help.semmle.com/codeql/codeql-for-vscode/procedures/setting-up.html#updating-an-existing-workspace-for-codeql).

## Quick start: Using CodeQL

You can find all the commands contributed by the extension in the Command Palette (**Ctrl+Shift+P** or **Cmd+Shift+P**) by typing `CodeQL`, many of them are also accessible through the interface, and via keyboard shortcuts.

### Importing a database from LGTM.com

While you can use the [CodeQL CLI to create your own databases](https://help.semmle.com/codeql/codeql-cli/procedures/create-codeql-database.html), the simplest way to start is by downloading a database from LGTM.com.

1. Log in to LGTM.com.
1. Find a project you're interested in and display the **Integrations** tab (for example, [Apache Kafka](https://lgtm.com/projects/g/apache/kafka/ci/)).
1. Scroll to the **CodeQL databases for local analysis** section at the bottom of the page.
1. Download databases for the languages that you want to explore.
1. Unzip the databases.
1. For each database that you want to import:
    1. In the VS Code sidebar, go to **CodeQL** > **Databases** and click **+**.
    1. Browse to the unzipped database folder (the parent folder that contains `db-<language>` and `src`) and select **Choose database** to add it.

When the import is complete, each CodeQL database is displayed in the CodeQL sidebar under **Databases**.

### Running a query

The instructions below assume that you're using the CodeQL starter workspace, or that you've added the CodeQL libraries and queries repository to your workspace.

1. Expand the `ql` folder and locate a query to run. The standard queries are grouped by target language and then type, for example: `ql/java/ql/src/Likely Bugs`.
1. Open a query (`.ql`) file.
3. Right-click in the query window and select **CodeQL: Run Query**. Alternatively, open the Command Palette (**Ctrl+Shift+P** or **Cmd+Shift+P**), type `Run Query`, then select **CodeQL: Run Query**.

The CodeQL extension runs the query on the current database using the CLI and reports progress in the bottom right corner of the application.
When the results are ready, they're displayed in the CodeQL Query Results view. Use the dropdown menu to choose between different forms of result output.

If there are any problems running a query, a notification is displayed in the bottom right corner of the application. In addition to the error message, the notification includes details of how to fix the problem.

## What next?

For more information about the CodeQL extension, [see the documentation](https://help.semmle.com/codeql/codeql-for-vscode.html). Otherwise, you could:

* [Create a database for a different codebase](https://help.semmle.com/codeql/codeql-cli/procedures/create-codeql-database.html).
* [Try out variant analysis](https://help.semmle.com/QL/learn-ql/ql-training.html).
* [Learn more about CodeQL](https://help.semmle.com/QL/learn-ql/).
* [Read how security researchers use CodeQL to find CVEs](https://securitylab.github.com/research).

## License

The CodeQL extension for Visual Studio Code is [licensed](LICENSE.md) under the MIT License. The version of CodeQL used by the CodeQL extension is subject to the [CodeQL Research Terms & Conditions](https://securitylab.github.com/tools/codeql/license).
