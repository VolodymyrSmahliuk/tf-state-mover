## Preamble

The original `tfmv` tool: [kozzztya/tf-state-mover](https://github.com/kozzztya/tf-state-mover).

The original **fix** for Terraform version `>= 0.12.0`: [seboudry/tf-state-mover](https://github.com/seboudry/tf-state-mover)

My fork extends the tool functionality to provide additional options and upgrade interaction with CLI interface. Check the [CHANGELOG.md](./CHANGELOG.md) for details about current features and [TODO.md](./TODO.md) for the future enhancements.

# Terraform state move helper

Interactive CLI for moving resources in a Terraform state.

## Motivation

Sometimes you need to refactor your config. Move resources to the separate module, rename a resource, etc.
Terraform will plan to recreate resources in this case. You can use command `terraform state mv` to prevent this.
But it can be pretty routine. This tool helps you easily do this. Just select from the list source resource, then destination, press enter, repeat.

## Installation

> I don't have the access to the original [npm project repository](https://www.npmjs.com/package/tfmv?activeTab=readme, so we need to build the tool from source code.

### Install as a global binary

1. Clone the repo

```shell
git clone https://github.com/VolodymyrSmahliuk/tf-state-mover.git
```

2. Build the application package from source code by `npm`

```shell
npm pack
```

3. Install the application from the package created on the previous step

```shell
npm install --global tfmv-<app-version>.tgz
```

### Run from the repo as a script

1. Clone the repo

```shell
git clone https://github.com/VolodymyrSmahliuk/tf-state-mover.git
```

2. Install required packages

```shell
npm install
```

3. Run the `index.js` from the **root module** of your Terraform code

```shell
node <path-to-this-repo>/index.js
```

## Usage

Run state move for the whole Terraform code

```
ftmv
```

Or use `-target` option

```
ftmv -target=module.meaningful_name -target=module.meaningful_name_new
```

![Example of working](docs/gifs/example.gif)

