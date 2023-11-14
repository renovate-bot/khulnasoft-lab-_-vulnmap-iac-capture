# Vulnmap IaC Capture CLI Extension

## Overview

This module implements the Vulnmap CLI Extension to capture a Terraform state, filter it and send it to Vulnmap API.


## Filtering

We use an allowlist to ensure we only send expected and non-sensitive information to the Vulnmap API.

You can find the expected fields in [state.go](internal/terraform/state.go) and [statefilter.go](internal/filtering/statefilter.go).

## Usage

This repository produces a standalone binary for debugging purposes. We advise to use this command as part of [Vulnmap CLI](https://github.com/khulnasoft-lab/cli).

This is the usage for the standalone binary:
```
Usage of vulnmap-iac-capture:
      --api-rest-token string   Auth token for the API Usage (Required)
      --api-rest-url string     Url for Vulnmap REST API (default "https://api.vulnmap.khulnasoft.com")
  -d, --debug                   Show debug information (Optional default false)
      --org string              Organization public id (Required)
      --path string             Path to look for Terraform state files (can be a file, a directory or a glob pattern) (Optional default ".")
      --stdin                   Read Terraform state from the standard input instead of path (Optional)
```

