# Connected Mobility Solution on AWS Public Assets

<!-- markdownlint-disable-next-line -->

## Table of Contents

- [Connected Mobility Solution on AWS Public Assets](#connected-mobility-solution-on-aws-public-assets)
  - [Table of Contents](#table-of-contents)
  - [Solution Overview](#solution-overview)
  - [Deployment Prerequisites](#deployment-prerequisites)
    - [Required Tools](#required-tools)
    - [Required Tool Versions](#required-tool-versions)
    - [Install Required Tools (OSX/Linux)](#install-required-tools-osxlinux)
      - [NVM](#nvm)
      - [Node / NPM](#node--npm)
      - [Pyenv](#pyenv)
      - [Python / Pip](#python--pip)
      - [Pipenv](#pipenv)
      - [AWS CLI](#aws-cli)
      - [Verify Required Tool Installations](#verify-required-tool-installations)
    - [Install Dependencies](#install-dependencies)
    - [Setup Environment Variables](#setup-environment-variables)
    - [Build](#build)
    - [Upload Assets to S3](#upload-assets-to-s3)
  - [License](#license)

## Solution Overview

These are public assets used by the Automotive Cloud Development Portal (backstage)

## Deployment Prerequisites

### Required Tools

To deploy CMS on AWS, a variety of tools are required. These deploy instructions will install the following to your machine:

- [NVM](https://github.com/nvm-sh/nvm)
- [Node](https://nodejs.org/en)
- [NPM](https://www.npmjs.com/)
- [Pyenv](https://github.com/pyenv/pyenv)
- [Python](https://www.python.org/)
- [Pip](https://pypi.org/project/pip/)
- [Pipenv](https://pipenv.pypa.io/en/latest/installation.html)
- [AWS CLI](https://docs.aws.amazon.com/cli/)

### Required Tool Versions

Certain tools also require specific versions. See the table below for the appropriate versions. Following the
provided install instructions will install the correct versions.

For tools not listed here, stable versions should work appropriately.

| Dependency | Version  |
|------------|----------|
| [NodeJS](https://docs.npmjs.com/downloading-and-installing-node-js-and-npm)   | 18.17.*    |
| [Python](https://www.python.org)                                              | 3.12.*     |

### Install Required Tools (OSX/Linux)

Install the following tools in the order instructed here. Where appropriate, a script has been provided to aid in install.
Otherwise, please visit the installation guide provided by the tool's publisher to ensure a correct installation.

> **WARNING:** If after a successful installation, a command is not found, you may need to restart your terminal.

#### NVM

Follow the [nvm installation guide](https://github.com/nvm-sh/nvm#installing-and-updating) to install NVM.
Ensure your installation properly set your path by running the script below.

```bash
nvm --version
# Expected Output: x.xx.x
```

#### Node / NPM

```bash
nvm install
nvm use
```

For more information see the [nvm usage guide](https://github.com/nvm-sh/nvm#usage) for installing the correct
version of Node. Manually installing Node without the use of nvm is not recommended.

#### Pyenv

Follow the [pyenv installation guide](https://github.com/pyenv/pyenv#automatic-installer) to install Pyenv.
You will likely need to manually add Pyenv to your PATH by following the provided instructions. Ensure your
installation properly set your path by running the script below.

```bash
pyenv --version
# Expected Output: pyenv x.x.xx
```

#### Python / Pip

```bash
pyenv install -s
```

For more information see the [pyenv usage guide](https://github.com/pyenv/pyenv#usage) for installing the
correct version of Python. Manually installing Python without the use of pyenv is not recommended.

#### Pipenv

Follow the [pipenv installation guide](https://pipenv.pypa.io/en/latest/installation.html) to install Pipenv.
You will likely need to manually add Pipenv to your PATH by following the provided instructions. Ensure your
installation properly set your PATH by running the script below.

```bash
pipenv --version
# Expected Output: pipenv, version xxxx.xx.x
```

#### AWS CLI

Follow the installation instructions laid out in the
[AWS CLI install page](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html).
This install is OS specific, and includes multiple options for both a system wide, and user specific
install. Follow the install instructions most appropriate to you. Ensure your installation properly
set your PATH by running the script below.

```bash
aws --version
# Expected Output: aws-cli/x.xx.xx ...
```

#### Verify Required Tool Installations

Run the following command to verify the proper installation of all of the tools listed above. If
any errors are displayed, attempt to reinstall that tool.

```bash
make verify-required-tools
```

### Install Dependencies

Now that you have the correct tools, you can install the dependencies used by the solution using `make install`.
After installing, activate the environment which contains the dependencies.

```bash
make install
```

### Setup Environment Variables

Set the AWS profile and region as required

```bash
export AWS_PROFILE=default
export AWS_REGION=us-east-1
```

### Build

Stage the public assets

```bash
make build
```

### Upload Assets to S3

The upload target creates the necessary bucket and uploads the global and regional assets.

```bash
make upload
```

## License

Copyright Amazon.com, Inc. or its affiliates. All Rights Reserved.

Licensed under the Apache License, Version 2.0 (the "License").
You may not use this file except in compliance with the License.
You may obtain a copy of the License at <http://www.apache.org/licenses/LICENSE-2.0>

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
