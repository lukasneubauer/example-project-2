# Saves

The goal or this project is to provide script for creation of save game backups.

## Configuration

Each line of the configuration file needs to be formatted as follows:

```
Game name[ (Operating system:Game store)];Path to game saves directory;Path to game saves backup directory
```

## Usage

Make sure that the `saves` script is in your `PATH` and call:

* `saves -b` to create save game backup
* `saves -b -s <suffix>` to create save game backup with suffix
* `saves -r` to revert save game backup
