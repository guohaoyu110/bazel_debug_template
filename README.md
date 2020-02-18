# bazel_debug\_template
- Run this in the root of your workspace to find the target of `bazel-cpp-template` symlink that Bazel creates based. These symlinks are documented [here](https://docs.bazel.build/versions/master/output_directories.html):

```bash
readlink -n bazel-cpp-template
```

- Put the output of that command in [launch.json](.vscode/launch.json)'s sourcemap section:

```json
"sourceMap": {
        "[output of readlink -n bazel-cpp-template]": "${workspaceFolder}/"
 }
```

Example:

```json
"sourceMap": {
        "/private/var/tmp/_bazel_ari/asdfasdfasdfasdfasdfgadfgasdg/execroot/__main__": "${workspaceFolder}/"
 }
```