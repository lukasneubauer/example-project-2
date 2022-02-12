# Split

The goal of this project is to create the `split` script which can split-out portion of Git repository and thus provide
ability to push this portion into its own Git remote.

For example, let's imagine the following repository structure:

```
repository-directory
`- bin
   `- file-a
`- lib
   `- file-b
`- standalone-script
   `- file-c
```

This repository sits on its own remote as is, but if there is a need to separate the `standalone-script` directory into
its own Git repository, the `split` script can do exactly that.

## Usage

First, create new Git remote, e.g. `split-origin`:

```
git remote add split-origin <remote-url>
```

Then make sure that the `split` script is in your `PATH` and call:

```
split -r split-origin -m standalone-script
```

## Explanation

Options:

* the `-r` option stands for remote (Git remote into which the split-out content will be pushed)
* the `-m` option stands for module (directory which is a subject to the split and will be pushed into said remote)

After this operation this repository will remain the same as it was before the call of the `split` script
(directory `standalone-script` will not be removed and history will be preserved), but on the new `split-origin` remote
there will be only the contents of the `standalone-script` directory.

The split will be done on the current Git branch so the split-out portion will be pushed into branch with the same name
on the `split-origin` remote.

Also, only commits referring to changes in the `standalone-script` directory will be included.
