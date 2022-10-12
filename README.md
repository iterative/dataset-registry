# DVC Dataset Registry

This _[DVC Data Registry]_ is a centralized place to manage raw data files for
use in other example DVC projects, such as
https://github.com/iterative/example-get-started.

[dvc data registry]: https://dvc.org/doc/use-cases/data-registry

## Installation

Start by cloning the project:

```console
$ git clone https://github.com/iterative/dataset-registry
$ cd dataset-registry
```

This DVC project comes with a preconfigured DVC
[remote storage](https://man.dvc.org/remote) to hold all of the datasets. This
is a read-only HTTP remote.

```console
$ dvc remote list
storage https://remote.dvc.org/dataset-registry
```

**Important**: To be able to push to the default remote, overwrite it with:

```console
$ dvc remote add -d --local storage s3://dvc-public/remote/dataset-registry
```

> This requires having configured corresponding S3 credentials locally.

## Testing data synchronization locally

If you'd like to test commands like [`dvc push`](https://man.dvc.org/push),
that require write access to the remote storage, the easiest way would be to set
up a "local remote" on your file system:

> This kind of remote is located in the local file system, but is external to
> the DVC project.

```console
$ mkdir -P /tmp/dvc-storage
$ dvc remote add local /tmp/dvc-storage
```

You should now be able to run:

```console
$ dvc push -r local
```

## Datasets

The folder structure of this project groups datasets corresponding to the
external projects they pertain to.
After cloning and using [`dvc pull`](https://man.dvc.org/pull) to download data
under DVC control, the workspace should look like this:


```console
$ tree
.
├── README.md
├── get-started
│   └── data.xml.dvc  # Dataset used in iterative/example-get-started
├── mnist
│   └── raw.dvc       # Dataset used in iterative/dvc-get-started
├── fashion-mnist
    └── raw.dvc       # Dataset used in iterative/dvc-get-started
```
