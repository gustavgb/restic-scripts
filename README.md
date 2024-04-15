# restic-scripts

Command line utility to manage restic repository, while not exposing secrets to terminal history or global environment variables.

## Usage

Install restic, clone this repo, add it to your PATH and rename *config-template* to *config*. In this file you must export at least the variables `RESTIC_REPOSITORY` and `RESTIC_PASSWORD`, along with any specific variables needed for your particular remote, such as `AWS_ACCESS_KEY_ID`. Example:

```sh
export RESTIC_REPOSITORY="s3:s3.example.com/mybackup"
export RESTIC_PASSWORD="Pass1"
export AWS_ACCESS_KEY_ID="1234"
export AWS_SECRET_ACCESS_KEY="abcd"
```

After the setup use it like this: `restic-scripts {command}`. Available commands are:

- `backup`
- `prune`
- `mount`
- `snapshots`
- `unlock`
- `restore`

