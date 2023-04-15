# Shared libraries in Go

## Initialize the workspace

### Initialize the root module

```bash
go mod init github.com/mateothegreat/go-demo-shared-libraries
```

```
module github.com/mateothegreat/go-demo-shared-libraries

go 1.20
```

## Create the libraries

```bash
mkdir -p libraries/{common,models,utilities}
```

```
.
├── README.md
├── go.mod
└── libraries
    ├── common
    ├── models
    └── utilities

5 directories, 2 files
```

### Initialize the libraries

```shell
cd libraries/common
go mod init github.com/mateothegreat/go-demo-shared-libraries/common

cd ../models
go mod init github.com/mateothegreat/go-demo-shared-libraries/models

cd ../utilities
go mod init github.com/mateothegreat/go-demo-shared-libraries/utilities
```

### Initialize the workspace

```shell
go work init libraries/common libraries/models libraries/utilities
```

```shell
.
├── README.md
├── go.mod
├── go.work
└── libraries
    ├── common
    │   └── go.mod
    ├── models
    │   └── go.mod
    └── utilities
        └── go.mod

5 directories, 6 files
```

```go
go 1.20

use (
./libraries/common
./libraries/models
./libraries/utilities
)
```