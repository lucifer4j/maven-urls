# maven-urls

Small reproducer to test behavior of `child.scm.url.inherit.append.path` and related parameters. The project consists
of a parent module `maven-urls` which sets to `child.scm.url.inherit.append.path` to false. The `child-project` module
inherits from it, overwrites scm block but does not specify the attribute explicitly. Finally, the `child-inside-child`
module inherits from `child-project` and does not specify `scm` at all.

As evident from the `effective-pom.log` file, the `scm` url of the `child-inside-child` project is same as that of the
`child-project` which yields the desired behavior in this case.
