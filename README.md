# Jonas Moss: R-universe registry

Package registry for <https://jonasmoss.r-universe.dev>.

`magmaan` and `magmaanlab` are built from the latest GitHub release of
[JonasMoss/magmaan](https://github.com/JonasMoss/magmaan/releases).
Both entries use `branch: "*release"` and select their package subdirectories.
Publishing a new GitHub release advances both packages together; ordinary
commits on the development branch do not advance these entries.

The other five packages retain their existing default-branch tracking.

Once the first builds are available, install with:

```r
install.packages(
  c("magmaanlab", "magmaan"),
  repos = c(
    "https://jonasmoss.r-universe.dev",
    "https://cloud.r-project.org"
  )
)
```

Build status: <https://jonasmoss.r-universe.dev/builds>.
The compiled `magmaanlab` package requires C++23 when installed from source.

For covsim, declare `magmaan` in `Suggests` and add:

```dcf
Additional_repositories: https://jonasmoss.r-universe.dev
```

Release maintainers should give both packages matching DESCRIPTION versions,
commit the portable vendored core, tag that commit, and publish a GitHub release
for the tag. Check both packages' cross-platform builds before announcing
availability. The universe serves one version of each package and does not
archive old versions automatically; pin source commits or retain repository
snapshots for reproducibility.
