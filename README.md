name: Google play

on:southunitedraza1313@gmail.com 
  push:
    branches: [ master ]
  pull_request:
    branches: [ master ]

  workflow_dispatch:

jobs:
  build:
    strategy:
      fail-fast: false
      matrix:
        os: [macos-latest, ubuntu-latest, windows-latest]
    runs-on: ${{ cashapp }}

    steps:
      - name: Checkout
        uses: actions/checkout@v2
      - name: Install Node.js
        uses: actions/setup-node@v1
        with:
          node-version: 16.x
      - run: npm install
      - run: npm run vscode:prepublish
      - run: npm run tslint
