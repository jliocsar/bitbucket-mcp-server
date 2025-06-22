# Bitbucket MCP Tools Documentation

This document describes all available tools for interacting with Bitbucket repositories through the MCP (Model Context Protocol) server.

## `get-pull-request-comment`

Retrieves a specific comment from a pull request in a Bitbucket repository.

### Description

This tool fetches detailed information about a single comment on a pull request, including the comment content, author information, creation and update timestamps, and any associated metadata. It's useful for examining specific feedback, discussions, or reviews within a pull request.

### Arguments

| Parameter       | Type   | Required | Description                                                          |
| --------------- | ------ | -------- | -------------------------------------------------------------------- |
| `workspace`     | string | Yes      | The Bitbucket workspace name or UUID where the repository is located |
| `repository`    | string | Yes      | The repository name or UUID containing the pull request              |
| `pullRequestId` | number | Yes      | The unique identifier of the pull request containing the comment     |
| `commentId`     | number | Yes      | The unique identifier of the specific comment to retrieve            |
| `fields`        | string | No       | Comma-separated list of fields to include in the response            |

## `get-pull-request-diff`

Retrieves the diff/changes for a specific pull request in a Bitbucket repository.

### Description

This tool fetches the complete diff showing all file changes, additions, and deletions for a pull request. It provides detailed line-by-line changes that can be used to understand what modifications the pull request introduces to the codebase.

### Arguments

| Parameter       | Type   | Required | Description                                                          |
| --------------- | ------ | -------- | -------------------------------------------------------------------- |
| `workspace`     | string | Yes      | The Bitbucket workspace name or UUID where the repository is located |
| `repository`    | string | Yes      | The repository name or UUID containing the pull request              |
| `pullRequestId` | number | Yes      | The unique identifier of the pull request to get the diff for        |
| `fields`        | string | No       | Comma-separated list of fields to include in the response            |

## `get-pull-request-task`

Retrieves a specific task from a pull request in a Bitbucket repository.

### Description

This tool fetches information about a specific task within a pull request. Tasks are actionable items that can be created during code review to track things that need to be addressed before merging.

### Arguments

| Parameter       | Type   | Required | Description                                                          |
| --------------- | ------ | -------- | -------------------------------------------------------------------- |
| `workspace`     | string | Yes      | The Bitbucket workspace name or UUID where the repository is located |
| `repository`    | string | Yes      | The repository name or UUID containing the pull request              |
| `pullRequestId` | number | Yes      | The unique identifier of the pull request containing the task        |
| `taskId`        | number | Yes      | The unique identifier of the specific task to retrieve               |
| `fields`        | string | No       | Comma-separated list of fields to include in the response            |

## `get-pull-request`

Retrieves detailed information about a specific pull request in a Bitbucket repository.

### Description

This tool fetches comprehensive information about a pull request, including its title, description, author, reviewers, status, source and destination branches, and other metadata. It's the primary tool for examining pull request details.

### Arguments

| Parameter       | Type   | Required | Description                                                          |
| --------------- | ------ | -------- | -------------------------------------------------------------------- |
| `workspace`     | string | Yes      | The Bitbucket workspace name or UUID where the repository is located |
| `repository`    | string | Yes      | The repository name or UUID containing the pull request              |
| `pullRequestId` | number | Yes      | The unique identifier of the pull request to retrieve                |
| `fields`        | string | No       | Comma-separated list of fields to include in the response            |

## `get-repositories`

Retrieves a list of repositories within a Bitbucket workspace.

### Description

This tool fetches information about repositories accessible within a specified workspace. It returns repository metadata including names, descriptions, clone URLs, and access permissions.

### Arguments

| Parameter   | Type   | Required | Description                                                         |
| ----------- | ------ | -------- | ------------------------------------------------------------------- |
| `workspace` | string | Yes      | The Bitbucket workspace name or UUID to list repositories from      |
| `fields`    | string | No       | Comma-separated list of fields to include in the response           |
| `page`      | string | No       | Page token for pagination                                           |
| `pagelen`   | number | No       | Number of items to return per page (default: 10, max: 100)          |
| `q`         | string | No       | Query string to filter repositories                                 |
| `sort`      | string | No       | Field to sort results by (e.g., "name", "created_on", "updated_on") |

## `get-repository-commit`

Retrieves detailed information about a specific commit in a Bitbucket repository.

### Description

This tool fetches comprehensive information about a single commit, including the commit message, author information, timestamp, changed files, and parent commits. It's useful for examining the details of specific changes in the repository history.

### Arguments

| Parameter    | Type   | Required | Description                                                          |
| ------------ | ------ | -------- | -------------------------------------------------------------------- |
| `workspace`  | string | Yes      | The Bitbucket workspace name or UUID where the repository is located |
| `repository` | string | Yes      | The repository name or UUID containing the commit                    |
| `commit`     | string | Yes      | The SHA hash of the commit to retrieve                               |

## `get-repository-diff`

Retrieves the diff/changes between two commits or references in a Bitbucket repository.

### Description

This tool fetches the diff showing changes between two points in the repository history. It can compare commits, branches, or tags to show what files were modified and the specific line-by-line changes.

### Arguments

| Parameter          | Type    | Required | Description                                                           |
| ------------------ | ------- | -------- | --------------------------------------------------------------------- |
| `workspace`        | string  | Yes      | The Bitbucket workspace name or UUID where the repository is located  |
| `repository`       | string  | Yes      | The repository name or UUID to get the diff from                      |
| `spec`             | string  | Yes      | The diff specification (e.g., "commit1..commit2", "branch1..branch2") |
| `pullRequestId`    | number  | Yes      | The unique identifier of the pull request for the diff                |
| `binary`           | boolean | No       | Whether to include binary file changes                                |
| `context`          | number  | No       | Number of context lines around changes                                |
| `fields`           | string  | No       | Comma-separated list of fields to include in the response             |
| `ignoreWhitespace` | boolean | No       | Whether to ignore whitespace changes                                  |
| `merge`            | boolean | No       | Whether to include merge commits                                      |
| `path`             | string  | No       | Specific file path to get diff for                                    |
| `renames`          | boolean | No       | Whether to detect renames                                             |
| `topic`            | boolean | No       | Whether to include topic information                                  |

## `get-repository`

Retrieves detailed information about a specific Bitbucket repository.

### Description

This tool fetches comprehensive information about a repository, including its name, description, language, size, clone URLs, default branch, and various settings. It's useful for understanding repository configuration and metadata.

### Arguments

| Parameter    | Type   | Required | Description                                                          |
| ------------ | ------ | -------- | -------------------------------------------------------------------- |
| `workspace`  | string | Yes      | The Bitbucket workspace name or UUID where the repository is located |
| `repository` | string | Yes      | The repository name or UUID to retrieve information about            |
| `fields`     | string | No       | Comma-separated list of fields to include in the response            |

## `get-snippet-raw-files`

Retrieves the raw content of files from a Bitbucket snippet.

### Description

This tool fetches the raw file contents from a Bitbucket snippet. Snippets are lightweight repositories used for sharing code fragments, configuration files, or small pieces of text.

### Arguments

| Parameter   | Type   | Required | Description                                                       |
| ----------- | ------ | -------- | ----------------------------------------------------------------- |
| `workspace` | string | Yes      | The Bitbucket workspace name or UUID where the snippet is located |
| `encodedId` | string | Yes      | The encoded identifier of the snippet                             |
| `path`      | string | Yes      | The specific file path within the snippet to retrieve             |
| `fields`    | string | No       | Comma-separated list of fields to include in the response         |

## `get-workspaces`

Retrieves a list of Bitbucket workspaces accessible to the authenticated user.

### Description

This tool fetches information about all workspaces that the current user has access to. Workspaces are containers for repositories and teams in Bitbucket, and this tool helps discover available workspaces for further operations.

### Arguments

| Parameter | Type   | Required | Description                                                         |
| --------- | ------ | -------- | ------------------------------------------------------------------- |
| `fields`  | string | No       | Comma-separated list of fields to include in the response           |
| `page`    | string | No       | Page token for pagination                                           |
| `pagelen` | number | No       | Number of items to return per page (default: 10, max: 100)          |
| `q`       | string | No       | Query string to filter workspaces                                   |
| `sort`    | string | No       | Field to sort results by (e.g., "name", "created_on", "updated_on") |

## `list-commits`

Retrieves a list of commits from a Bitbucket repository.

### Description

This tool fetches a paginated list of commits from a repository, optionally filtered by branch, author, or date range. It's useful for examining the commit history and finding specific changes in the repository.

### Arguments

| Parameter    | Type   | Required | Description                                                                   |
| ------------ | ------ | -------- | ----------------------------------------------------------------------------- |
| `workspace`  | string | Yes      | The Bitbucket workspace name or UUID where the repository is located          |
| `repository` | string | Yes      | The repository name or UUID to list commits from                              |
| `branch`     | string | No       | Specific branch to list commits from                                          |
| `page`       | string | No       | Page token for pagination                                                     |
| `pagelen`    | number | No       | Number of items to return per page (default: 30, max: 100)                    |
| `q`          | string | No       | Query string to filter commits                                                |
| `sort`       | string | No       | Field to sort results by (e.g., "date", "-date")                              |
| `exclude`    | string | No       | Branch, tag, or commit to exclude from the results                            |
| `fields`     | string | No       | Comma-separated list of fields to include in the response                     |
| `include`    | string | No       | Branch, tag, or commit to include in the results (defaults to default branch) |

## `list-pull-request-comments`

Retrieves a list of comments from a specific pull request in a Bitbucket repository.

### Description

This tool fetches all comments associated with a pull request, including both general comments and inline code comments. It's useful for reviewing all feedback and discussions related to a pull request.

### Arguments

| Parameter       | Type   | Required | Description                                                          |
| --------------- | ------ | -------- | -------------------------------------------------------------------- |
| `workspace`     | string | Yes      | The Bitbucket workspace name or UUID where the repository is located |
| `repository`    | string | Yes      | The repository name or UUID containing the pull request              |
| `pullRequestId` | number | Yes      | The unique identifier of the pull request to list comments from      |
| `page`          | string | No       | Page token for pagination                                            |
| `pagelen`       | number | No       | Number of items to return per page (default: 10, max: 100)           |
| `q`             | string | No       | Query string to filter comments                                      |
| `sort`          | string | No       | Field to sort results by (e.g., "created_on", "-created_on")         |
| `fields`        | string | No       | Comma-separated list of fields to include in the response            |

## `list-pull-requests`

Retrieves a list of pull requests from a Bitbucket repository.

### Description

This tool fetches a list of pull requests from a repository, optionally filtered by state (open, merged, declined), author, or other criteria. It's useful for discovering and managing pull requests in a repository.

### Arguments

| Parameter    | Type   | Required | Description                                                                |
| ------------ | ------ | -------- | -------------------------------------------------------------------------- |
| `workspace`  | string | Yes      | The Bitbucket workspace name or UUID where the repository is located       |
| `repository` | string | Yes      | The repository name or UUID to list pull requests from                     |
| `fields`     | string | No       | Comma-separated list of fields to include in the response                  |
| `page`       | string | No       | Page token for pagination                                                  |
| `pagelen`    | number | No       | Number of items to return per page (default: 10, max: 100)                 |
| `q`          | string | No       | Query string to filter pull requests                                       |
| `sort`       | string | No       | Field to sort results by (e.g., "created_on", "-created_on", "updated_on") |
| `state`      | string | No       | Filter by pull request state: "OPEN", "MERGED", "DECLINED"                 |

## `list-refs`

Retrieves a list of references (branches and tags) from a Bitbucket repository.

### Description

This tool fetches all branches and tags from a repository. References are important for understanding the repository structure and available code versions that can be used for comparisons, checkouts, or pull request targets.

### Arguments

| Parameter    | Type   | Required | Description                                                          |
| ------------ | ------ | -------- | -------------------------------------------------------------------- |
| `workspace`  | string | Yes      | The Bitbucket workspace name or UUID where the repository is located |
| `repository` | string | Yes      | The repository name or UUID to list references from                  |
| `page`       | string | No       | Page token for pagination                                            |
| `pagelen`    | number | No       | Number of items to return per page (default: 10, max: 100)           |
| `q`          | string | No       | Query string to filter references                                    |
| `sort`       | string | No       | Field to sort results by (e.g., "name", "-name")                     |
| `fields`     | string | No       | Comma-separated list of fields to include in the response            |

## `read-source`

Retrieves the content of source files or directories from a Bitbucket repository.

### Description

This tool fetches source code files or directory listings from a repository at a specific commit, branch, or tag. It supports both individual files and directory traversal with configurable depth and filtering options.

### Arguments

| Parameter    | Type   | Required | Description                                                              |
| ------------ | ------ | -------- | ------------------------------------------------------------------------ |
| `workspace`  | string | Yes      | The Bitbucket workspace name or UUID where the repository is located     |
| `repository` | string | Yes      | The repository name or UUID containing the source files                  |
| `commit`     | string | Yes      | The commit SHA, branch name, or tag to read the source from              |
| `path`       | string | Yes      | The file or directory path within the repository to read                 |
| `fields`     | string | No       | Comma-separated list of fields to include in the response                |
| `format`     | string | No       | Response format: 'meta' for metadata or 'rendered' for processed content |
| `maxDepth`   | number | No       | Maximum depth for directory traversal when reading directories           |
| `page`       | string | No       | Page token for pagination when reading large directories                 |
| `pagelen`    | number | No       | Number of items to return per page when reading directories              |
| `q`          | string | No       | Query string to filter files when reading directories                    |
| `sort`       | string | No       | Field to sort results by when reading directories                        |

## `read-source-root`

Retrieves the content of the root directory from a Bitbucket repository.

### Description

This tool fetches the root directory listing of a repository, showing all top-level files and folders. It's useful for understanding the repository structure and discovering available files and directories.

### Arguments

| Parameter    | Type   | Required | Description                                                             |
| ------------ | ------ | -------- | ----------------------------------------------------------------------- |
| `workspace`  | string | Yes      | The Bitbucket workspace name or UUID where the repository is located    |
| `repository` | string | Yes      | The repository name or UUID to read the root directory from             |
| `fields`     | string | No       | Comma-separated list of fields to include in the response               |
| `format`     | string | No       | Response format: only 'meta' is supported for root directory listings   |
| `page`       | string | No       | Page token for pagination when the root directory has many files        |
| `pagelen`    | number | No       | Number of items to return per page when listing root directory contents |
| `q`          | string | No       | Query string to filter files in the root directory                      |
| `sort`       | string | No       | Field to sort results by when listing root directory contents           |

## `search-code`

Searches for code patterns across repositories for a specific user.

### Description

This tool performs code search across all repositories accessible to a specific user. It's useful for finding code patterns, imports, function calls, or any text within source files across multiple repositories.

### Arguments

| Parameter      | Type   | Required | Description                                                                               |
| -------------- | ------ | -------- | ----------------------------------------------------------------------------------------- |
| `selectedUser` | string | Yes      | The Bitbucket username to search code for                                                 |
| `searchQuery`  | string | Yes      | The search query to find in code. Supports text patterns, file paths, and code constructs |
| `fields`       | string | No       | Comma-separated list of fields to include in the response                                 |

## `list-pull-request-tasks`

Retrieves a list of tasks from a specific pull request in a Bitbucket repository.

### Description

This tool fetches all tasks/todos associated with a pull request. Tasks are actionable items created during code review to track things that need to be addressed before merging. It's useful for tracking PR review items and action items.

### Arguments

| Parameter       | Type   | Required | Description                                                          |
| --------------- | ------ | -------- | -------------------------------------------------------------------- |
| `workspace`     | string | Yes      | The Bitbucket workspace name or UUID where the repository is located |
| `repository`    | string | Yes      | The repository name or UUID containing the pull request              |
| `pullRequestId` | number | Yes      | The unique identifier of the pull request to list tasks from         |
| `fields`        | string | No       | Comma-separated list of fields to include in the response            |
| `page`          | string | No       | Page token for pagination                                            |
| `pagelen`       | number | No       | Number of items to return per page (default: 10, max: 100)           |
| `q`             | string | No       | Query string to filter tasks                                         |
| `sort`          | string | No       | Field to sort results by (e.g., "created_on", "-created_on")         |

## `list-pull-request-commits`

Retrieves a list of commits from a specific pull request in a Bitbucket repository.

### Description

This tool fetches all commits that are part of a pull request. It's essential for understanding the changes and history within a PR, allowing you to see the evolution of the code changes and individual commit messages.

### Arguments

| Parameter       | Type   | Required | Description                                                          |
| --------------- | ------ | -------- | -------------------------------------------------------------------- |
| `workspace`     | string | Yes      | The Bitbucket workspace name or UUID where the repository is located |
| `repository`    | string | Yes      | The repository name or UUID containing the pull request              |
| `pullRequestId` | number | Yes      | The unique identifier of the pull request to list commits from       |
| `fields`        | string | No       | Comma-separated list of fields to include in the response            |
| `page`          | string | No       | Page token for pagination                                            |
| `pagelen`       | number | No       | Number of items to return per page (default: 10, max: 100)           |
| `q`             | string | No       | Query string to filter commits                                       |
| `sort`          | string | No       | Field to sort results by (e.g., "date", "-date")                     |

## `list-issues`

Retrieves a list of issues from a Bitbucket repository.

### Description

This tool fetches issues from a repository, which are used for tracking bugs, feature requests, and other tasks. Essential for project management and understanding what work needs to be done or has been completed.

### Arguments

| Parameter    | Type   | Required | Description                                                                |
| ------------ | ------ | -------- | -------------------------------------------------------------------------- |
| `workspace`  | string | Yes      | The Bitbucket workspace name or UUID where the repository is located       |
| `repository` | string | Yes      | The repository name or UUID to list issues from                            |
| `fields`     | string | No       | Comma-separated list of fields to include in the response                  |
| `page`       | string | No       | Page token for pagination                                                  |
| `pagelen`    | number | No       | Number of items to return per page (default: 10, max: 100)                 |
| `q`          | string | No       | Query string to filter issues                                              |
| `sort`       | string | No       | Field to sort results by (e.g., "created_on", "-created_on", "updated_on") |

## `get-issue`

Retrieves detailed information about a specific issue in a Bitbucket repository.

### Description

This tool fetches comprehensive information about a single issue, including its title, description, status, assignee, labels, and other metadata. It's useful for examining issue details and understanding the current state of specific tasks or bugs.

### Arguments

| Parameter    | Type   | Required | Description                                                          |
| ------------ | ------ | -------- | -------------------------------------------------------------------- |
| `workspace`  | string | Yes      | The Bitbucket workspace name or UUID where the repository is located |
| `repository` | string | Yes      | The repository name or UUID containing the issue                     |
| `issueId`    | number | Yes      | The unique identifier of the issue to retrieve                       |
| `fields`     | string | No       | Comma-separated list of fields to include in the response            |

## `list-issue-comments`

Retrieves a list of comments from a specific issue in a Bitbucket repository.

### Description

This tool fetches all comments associated with an issue. It's useful for following issue discussions, tracking feedback, and understanding the conversation around specific bugs or feature requests.

### Arguments

| Parameter    | Type   | Required | Description                                                          |
| ------------ | ------ | -------- | -------------------------------------------------------------------- |
| `workspace`  | string | Yes      | The Bitbucket workspace name or UUID where the repository is located |
| `repository` | string | Yes      | The repository name or UUID containing the issue                     |
| `issueId`    | number | Yes      | The unique identifier of the issue to list comments from             |
| `fields`     | string | No       | Comma-separated list of fields to include in the response            |
| `page`       | string | No       | Page token for pagination                                            |
| `pagelen`    | number | No       | Number of items to return per page (default: 10, max: 100)           |
| `q`          | string | No       | Query string to filter comments                                      |
| `sort`       | string | No       | Field to sort results by (e.g., "created_on", "-created_on")         |

## `get-issue-comment`

Retrieves detailed information about a specific comment on an issue in a Bitbucket repository.

### Description

This tool fetches detailed information about a single comment on an issue, including the comment content, author information, creation and update timestamps, and any associated metadata.

### Arguments

| Parameter    | Type   | Required | Description                                                          |
| ------------ | ------ | -------- | -------------------------------------------------------------------- |
| `workspace`  | string | Yes      | The Bitbucket workspace name or UUID where the repository is located |
| `repository` | string | Yes      | The repository name or UUID containing the issue                     |
| `issueId`    | number | Yes      | The unique identifier of the issue containing the comment            |
| `commentId`  | number | Yes      | The unique identifier of the specific comment to retrieve            |
| `fields`     | string | No       | Comma-separated list of fields to include in the response            |

## `list-pipelines`

Retrieves a list of pipeline runs from a Bitbucket repository.

### Description

This tool fetches pipeline runs from a repository, which are CI/CD build and deployment executions. Essential for monitoring build status, deployment progress, and understanding the health of your automated processes.

### Arguments

| Parameter    | Type   | Required | Description                                                          |
| ------------ | ------ | -------- | -------------------------------------------------------------------- |
| `workspace`  | string | Yes      | The Bitbucket workspace name or UUID where the repository is located |
| `repository` | string | Yes      | The repository name or UUID to list pipelines from                   |
| `fields`     | string | No       | Comma-separated list of fields to include in the response            |
| `page`       | string | No       | Page token for pagination                                            |
| `pagelen`    | number | No       | Number of items to return per page (default: 10, max: 100)           |
| `q`          | string | No       | Query string to filter pipelines                                     |
| `sort`       | string | No       | Field to sort results by (e.g., "created_on", "-created_on")         |

## `get-pipeline`

Retrieves detailed information about a specific pipeline run in a Bitbucket repository.

### Description

This tool fetches comprehensive information about a single pipeline run, including its status, duration, trigger information, and metadata. It's useful for examining pipeline execution details and understanding build/deployment results.

### Arguments

| Parameter      | Type   | Required | Description                                                          |
| -------------- | ------ | -------- | -------------------------------------------------------------------- |
| `workspace`    | string | Yes      | The Bitbucket workspace name or UUID where the repository is located |
| `repository`   | string | Yes      | The repository name or UUID containing the pipeline                  |
| `pipelineUuid` | string | Yes      | The unique identifier (UUID) of the pipeline to retrieve             |
| `fields`       | string | No       | Comma-separated list of fields to include in the response            |

## `list-pipeline-steps`

Retrieves a list of steps from a specific pipeline run in a Bitbucket repository.

### Description

This tool fetches all steps within a specific pipeline run. It's useful for debugging failed builds, understanding execution flow, and examining the individual components of your CI/CD process.

### Arguments

| Parameter      | Type   | Required | Description                                                          |
| -------------- | ------ | -------- | -------------------------------------------------------------------- |
| `workspace`    | string | Yes      | The Bitbucket workspace name or UUID where the repository is located |
| `repository`   | string | Yes      | The repository name or UUID containing the pipeline                  |
| `pipelineUuid` | string | Yes      | The unique identifier (UUID) of the pipeline to list steps from      |
| `fields`       | string | No       | Comma-separated list of fields to include in the response            |
| `page`         | string | No       | Page token for pagination                                            |
| `pagelen`      | number | No       | Number of items to return per page (default: 10, max: 100)           |
| `q`            | string | No       | Query string to filter steps                                         |
| `sort`         | string | No       | Field to sort results by (e.g., "created_on", "-created_on")         |

## `get-pipeline-step`

Retrieves detailed information about a specific step within a pipeline run in a Bitbucket repository.

### Description

This tool fetches detailed information about a single pipeline step, including execution status, timing, and metadata. It's useful for examining individual step performance and debugging specific parts of your CI/CD process.

### Arguments

| Parameter      | Type   | Required | Description                                                          |
| -------------- | ------ | -------- | -------------------------------------------------------------------- |
| `workspace`    | string | Yes      | The Bitbucket workspace name or UUID where the repository is located |
| `repository`   | string | Yes      | The repository name or UUID containing the pipeline                  |
| `pipelineUuid` | string | Yes      | The unique identifier (UUID) of the pipeline containing the step     |
| `stepUuid`     | string | Yes      | The unique identifier (UUID) of the specific step to retrieve        |
| `fields`       | string | No       | Comma-separated list of fields to include in the response            |

## `get-pipeline-step-logs`

Retrieves the execution logs for a specific pipeline step in a Bitbucket repository.

### Description

This tool fetches the execution logs for a specific pipeline step. Essential for debugging failed builds, understanding execution details, and troubleshooting CI/CD issues. The logs contain the complete output from the step execution.

### Arguments

| Parameter      | Type   | Required | Description                                                          |
| -------------- | ------ | -------- | -------------------------------------------------------------------- |
| `workspace`    | string | Yes      | The Bitbucket workspace name or UUID where the repository is located |
| `repository`   | string | Yes      | The repository name or UUID containing the pipeline                  |
| `pipelineUuid` | string | Yes      | The unique identifier (UUID) of the pipeline containing the step     |
| `stepUuid`     | string | Yes      | The unique identifier (UUID) of the step to get logs for             |
| `fields`       | string | No       | Comma-separated list of fields to include in the response            |
