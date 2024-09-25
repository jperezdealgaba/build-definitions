# sast-coverity-check task

## Description:

The sast-coverity-check task uses Coverity tool to perform Static Application Security Testing (SAST). In this task, we use the buildless mode, where Coverity has the ability to capture source code without the need of building the product.

The documentation for this mode can be found here: https://sig-product-docs.synopsys.com/bundle/coverity-docs/page/commands/topics/coverity_capture.html

The characteristics of these tasks are:

- Perform buildless scanning with Coverity
- The whole source code is scanned (by scanning `$(workspaces.source.path)` )
- Only important findings are reported by default.  A parameter ( `SEVERITY_THRESHOLD`) is provided to override this configuration.
- The csdiff/v1 SARIF fingerprints are provided for all findings
- [Known false positives](https://gitlab.cee.redhat.com/osh/known-false-positives/) are eliminated by default.  A parameter ( `KFP_GIT_URL`) is provided to disable this feature or to configure a custom known false positives repository.

> NOTE: This task is executed only if there is a Coverity license set up in the environment. Please check coverity-availability-check task for more information.

## Params:

| name                | description                                                                                                                           |
|---------------------|---------------------------------------------------------------------------------------------------------------------------------------|
| COV_CAPTURE_ARGS    | Append arguments to the Coverity Capture CLI command                                                                                  |
| COV_ANALYZE_ARGS    | Append arguments to the cov-analyze CLI command                                                                                       |
| COV_LICENSE         | Name of secret which contains the Coverity license                                                                                    |
| IMP_FINDINGS_ONLY   | Report only important findings. Default is true. To report all findings, specify "false"                                              |
| KFP_GIT_URL         | Known False Positives git URL, optionally taking a revision delimited by #; If empty, filtering of known false positives is disabled. |
| PROJECT_NVR         | Name-Version-Release (NVR) of the scanned project, used to find path exclusions (it is optional)                                      |
| RECORD_EXCLUDED     | File to store all excluded findings to (it is optional)                                                                               |

## Results:

| name              | description              |
|-------------------|--------------------------|
| TEST_OUTPUT       | Tekton task test output. |

## Source repository for image:

// TODO: Add reference to private repo for the container image once the task is migrated to repo


## Additional links:

* https://sig-product-docs.synopsys.com/bundle/coverity-docs/page/commands/topics/coverity_capture.html
* https://scan.coverity.com/
* https://sig-product-docs.synopsys.com/bundle/coverity-docs/page/cli/topics/options_reference.html
