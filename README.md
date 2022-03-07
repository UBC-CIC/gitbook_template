# GitBook Template

This repo is a template for handover documentation for CIC Challenges using GitBook.

### Notes

- GitBook automatically uses the /README.md file as the index page of your documentation. This file should be changed to be similar to INTRO.md.
- SUMMARY.md is a GitBook file that generates the sidebar automatically.
- gitbook-cli is not compatible with the newest version of node. Node 12.18.1 is a suggested version that works with the package.

### Getting Started

1. (If not installed) Install Node Version Manager.

   Install nvm, a package that manages which node version you use and allows for switching between versions.

- Run either of the following commands to install nvm
  > ```console
  > curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash
  > ```
  >
  > or
  >
  > ```console
  > wget -qO- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash
  > ```

If this worked, `nvm -v` should succeed and print a version number.

2. Install Node@12.18.1

- To switch back to your current node version, install and use the

```console
 nvm install 12.18.1
 nvm use 12.18.1
```

3. Install gitbook-cli

```console
 npm install -g gitbook-cli@2.3.0
```

4.  From the root directory, serve this project:

```console
  gitbook serve
```

5. To publish your document, run the gulpfile via the gulp cli:

```console
  npx gulp publish
```
