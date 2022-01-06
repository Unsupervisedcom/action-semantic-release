<!-- start title -->

# GitHub Action:Semantic Release

<!-- end title -->
<!-- start description -->

Perform a semantic release. Includes an option to toggle `include administrators` on branch protection, and then run semantic-release with a given release config

<!-- end description -->
<!-- start contents -->
<!-- end contents -->
<!-- start usage -->

```yaml
- uses: Unsupervisedcom/action-semantic-release@undefined
  with:
    # git token to use for the run
    token: ""

    # If true, this action will disable the `include administrators` setting in branch
    # protection for this branch, and re-enable it after release. Re-enabling is run
    # using always()
    # Default: false
    toggle-admins: ""

    # The release configuration to use for the release. Set this to
    # `@unsupervised/release-config-javascript-actions` for javascript actions
    # Default: @unsupervised/release-config-general
    release-config: ""
```

<!-- end usage -->
   <!-- start inputs -->

| **Input**            | **Description**                                                                                                                                                                |              **Default**               | **Required** |
| :------------------- | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :------------------------------------: | :----------: |
| **`token`**          | git token to use for the run                                                                                                                                                   |                                        |   **true**   |
| **`toggle-admins`**  | If true, this action will disable the `include administrators` setting in branch protection for this branch, and re-enable it after release. Re-enabling is run using always() |                                        |  **false**   |
| **`release-config`** | The release configuration to use for the release. Set this to `@unsupervised/release-config-javascript-actions` for javascript actions                                         | `@unsupervised/release-config-general` |  **false**   |

<!-- end inputs -->
   <!-- start outputs -->

| **Output**      | **Description** | **Default** | **Required** |
| :-------------- | :-------------- | ----------- | ------------ |
| `random-number` | Random number   |             |              |

<!-- end outputs -->
   <!-- start examples -->

### Example usage

```yaml
name: Release
on:
  pull_request:
    types:
      - closed
    branches:
      - main
jobs:
  release:
    runs-on: ubuntu-latest
    name: Release
    steps:
      - uses: Unsupervisedcom/action-semantic-release@v1
        with:
          token: ${{ secrets.DEPLOYER_CI_TOKEN }}
```

<!-- end examples -->
<!-- start [.github/ghdocs/examples/] -->
<!-- end [.github/ghdocs/examples/] -->
