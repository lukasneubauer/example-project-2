# G3

Pronounced as **Go Git Go**.

The goal of this project is to make it easy to work with multiple remotes inside one single Git repository.

When working with repository which has multiple remotes (for whatever reason), it is tedious to always
run `push` and `pull` commands on each of them manually. This project aims to simplify that by letting
you have every necessary remote in a single configuration file and then calling `push` and / or `pull`
only once.

## Configuration

Start by creating configuration file named `.g3rc` in the root of your repository and place each remote on its own line.

Also make sure not to put `origin` into it (origin is always synced and tracks changes in the upstream).

Example of the configuration file is shown below:

```
github
gitlab
```

## Usage

Make sure that the `g3` script is in your `PATH` and call:

* `g3 push` to push current branch's changes into origin and other remotes
* `g3 push -f` to push current branch's changes into origin and other remotes (using force push)
* `g3 pull` to pull current branch's changes from origin and other remotes
