# go-pkg-test-client

## Descriptions

[GO_MOD_TIDY.log](GO_MOD_TIDY.log) and some other files show that you can install only necessary dependencies by separating go.mod file into appropriate subdirectories when installing them from the outside git root directory. If you install them from another subdirectory under the same git root directory, Go will resolve the git root and install the entire dependencies of the whole git project. In the same way, putting go.mod in the git root directory leads to full-install, and you should consider that separating go.mod may cause issues with IDEs, ordinarily developing the target packages.

Shown below is the directory structure of the target package: [ebi-yade/go-pkg-test](https://github.com/ebi-yade/go-pkg-test)

```tree
go-pkg-test (git root directory)
├── README.md
├── ex
│   ├── ex.go
│   ├── go.mod
│   └── go.sum
└── target
    ├── go.mod
    ├── go.sum
    └── target.go
```
