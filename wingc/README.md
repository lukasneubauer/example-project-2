# Wingc

The goal of this project is to provide ability to clean up debris files and directories left behind by various systems and applications such as Windows, Mega etc.

## Configuration

The configuration consists of directives listed bellow which can appear multiple times. Each directive accepts single value.

### Directive: BASE_DIR

Directory in which to search for files or directories mentioned in **STOP_IF_EXISTS** and **DELETE**.

### Directive: BASE_DIR_MULTI

Directory which contains subdirectories in which to search for files or directories mentioned in **STOP_IF_EXISTS** and **DELETE**.

### Directive: STOP_IF_EXISTS

File or directory which, if present causes the search to stop.

### Directive: DELETE

File or directory to delete.
