# restic-scripts

Command line utility to manage restic repository, while not exposing secrets to terminal history or global environment variables.

## Prerequisites

Install [restic (>=1.6)](https://restic.readthedocs.io/en/stable/020_installation.html), clone this repo and add it to your PATH.

## Setup

In the folder that you want to backup, add a file named `.restic-config`. In this file you must export at least the variables `RESTIC_REPOSITORY` and `RESTIC_PASSWORD`, along with any specific variables needed for your particular remote, such as `AWS_ACCESS_KEY_ID`. See [these docs](https://restic.readthedocs.io/en/stable/030_preparing_a_new_repo.html) for more info regarding environment variables used in Restic.

Example:

```sh
export RESTIC_REPOSITORY="s3:s3.example.com/mybackup"
export RESTIC_PASSWORD="Pass1"
export AWS_ACCESS_KEY_ID="1234"
export AWS_SECRET_ACCESS_KEY="abcd"
```

Optionally create a file named `.restic-excludes` and write any glob patterns that you wish to be excluded from the backup. See [this page](https://restic.readthedocs.io/en/stable/040_backup.html#excluding-files) for more info regarding exclude files.

## Usage

After the setup use it like this: `restic-scripts {command}`. Available commands are:

- `backup`
- `prune`
- `mount`
- `snapshots`
- `unlock`
- `restore`

