---
title: "Banking apps project"
date: 2022-10-13T03:39:13-07:00
draft: false
tags: ["Banking apps project", "SafetyNet", "Compatibility", "GrapheneOS", "Play Integrity API"]
author: "akc3n"
TocOpen: false
hidemeta: false
description: "Compatibility list of banking apps that work on GrapheneOS"
canonicalURL: "https://akc3n.page/posts/bankings-apps-project/"
weight: 1
---

[The banking apps project](https://privsec.dev/banking) is a maintained list of tested banking apps that do not enforce [SafetyNet](https://grapheneos.org/articles/attestation-compatibility-guide) and work with [GrapheneOS](https://grapheneos.org/)'s [compatibility layer](https://grapheneos.org/usage#sandboxed-google-play).

Users are able to view the [list](https://privsec.dev/banking) of currently submitted [reports](https://github.com/PrivSec-dev/banking-apps-compat-report/issues?q=is%3Aissue+is%3Aclosed) for banking apps that work on [GrapheneOS](https://grapheneos.org/).    

## Prerequisites

This section covers how to submit or update a banking app report.

### Submit a new app report 

There are several methods for GrapheneOS users to contribute their banking app report:

| Method | Description | Action |
| :--- | :--- | :---: |
| **GitHub** | Fill out form on [issue-tracker](https://github.com/PrivSec-dev/banking-apps-compat-report/issues) using your GitHub account | [`SUBMIT REPORT`](https://github.com/PrivSec-dev/banking-apps-compat-report/issues/new?assignees=&labels=&template=app_report.yml) |
| **Non-GitHub** | View gist → Raw → Save template markdown file to fill out. | [`Gist`](https://gist.github.com/akc3n/e845078ddbbb28ada0dd055c51ec45af) |
| Curl | Terminal → `curl -O` → paste copied url (gist form `.md` template) ⟶ | [`Copy link address`](https://gist.githubusercontent.com/akc3n/e845078ddbbb28ada0dd055c51ec45af/raw/5fdacb267aad5fa95ebf576cdcbd319f80bf9d12/banking-app-report-issue-form.md) |
| Google Form | N/A at the moment | N/A |
| [OhMyForm](https://github.com/ohmyform/ohmyform) | N/A at the moment, need to test | N/A |

Alternatively, curl and pipe output directly into vi/vim/neovim for editing:

```bash
curl https://gist.githubusercontent.com/akc3n/e845078ddbbb28ada0dd055c51ec45af/raw/5fdacb267aad5fa95ebf576cdcbd319f80bf9d12/banking-app-report-issue-form.md\?T | nvim -
```

### Update status of app report

Please do not open a new issue to update the status of a banking app report!

Use the [issue tracker to search](https://github.com/PrivSec-dev/banking-apps-compat-report/issues) for the banking app name listed above in the [International banking apps](#international-banking-apps) section and add a comment to _that_ report. 

If you are a non-github user and have tried every combination suggested for [possible solutions](https://akc3n.page/banking-issues) without being unable to resolving your specific banking app compatibiliity issue, then [`contact me`](https://privsec.dev/about#akc3n) afterwards please.
