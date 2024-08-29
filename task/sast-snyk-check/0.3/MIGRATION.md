# Migration from 0.2 to 0.3

Version 0.3:

- The `--severity-threshold` argument has been introduced and enabled by default with "high" value. Only high or superior vulnerabilities will be shown. Possible values for this argument are: `low`, `medium` and `high`.
- The results are parsed using `csgrep` and they are uploaded as results with a generated fingerprint.
- There are no default arguments as "--all-projects --exclude=test*,vendor,deps" are ignored by Snyk Code
- The results are uploaded as SARIF files to the registry
- SARIF produced by Snyk Code is not included in the CI log.

## Action from users

Renovate bot PR will be created with warning icon for a sast-snyk-check which is expected, no action from users are required.
