#  sf-cli-circleci-pipeline
[![CircleCI](https://circleci.com/gh/nhall97/sf-cli-circleci-monorepo/tree/main.svg?style=svg)](https://circleci.com/gh/nhall97/sf-cli-circleci-monorepo/tree/main)
Using the new Salesforce CLI (Beta) to expirement with CI/CD pipelines
https://github.com/salesforcecli/cli

## Yarn
We're using a yarn workspace to install the new Salesforce CLI.

```yarn add @salesforce/cli```

## Run command
Yarn is installed locally, so we run our commands with yarn.

```yarn sf```

## Enable workspaces
```yarn plugin import workspace-tools```

```yarn install```

## Using workspace/monorepo structure and sf cli
### Verify workspace
Verify packages are all working as expected:

```$yarn workspaces foreach -R run verify-sf```

### Deploy Package
Deploy the source files in a directory:

```$sf deploy metadata --source-dir path/to/source```

Deploy demo package:

```$yarn sf deploy metadata --source-dir packages/demo-package```

Deploy foobar package:

```$yarn sf deploy metadata --source-dir packages/foobar-package```

Deploy all packages located in workspace:

```$yarn workspaces foreach -R run deploy```


#### CircleCI Integration
CircleCI configuration added & trigger added on push to main branch
