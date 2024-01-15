### Hi there 👋
![header](https://capsule-render.vercel.app/api?type=waving&color=gradient&height=120&animation=fadeIn&section=footer&text=🚗🚘🚛&fontAlign=70)
<div align="left">
  

name: "Static code analysis workflow (CodeQL)"

on:
  push:
    branches:
      - master
  pull_request:
    branches:
      - master

permissions:
  actions: read
  checks: read
  contents: read
  deployments: read
  issues: read
  discussions: read
  packages: read
  pages: read
  pull-requests: read
  repository-projects: read
  security-events: write
  statuses: read

jobs:
  CodeQL-Build:
    # CodeQL runs on ubuntu-latest, windows-latest, and macos-latest
    runs-on: ubuntu-latest

    steps:
      - name: Checkout repository
        uses: actions/checkout@b4ffde65f46336ab88eb53be808477a3936bae11 # v4.1.1

      # Initializes the CodeQL tools for scanning.
      - name: Initialize CodeQL
        uses: github/codeql-action/init@46a6823b81f2d7c67ddf123851eea88365bc8a67 # v2.13.5
        with:
          languages: javascript

      - name: Perform CodeQL Analysis
        uses: github/codeql-action/analyze@46a6823b81f2d7c67ddf123851eea88365bc8a67 # v2.13.5
