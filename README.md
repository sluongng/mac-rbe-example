# Example Bazel RBE with BuildBuddy MacOS executor

This example uses the cc toolchain configured automatically based on the local setup.
It assumes that the local host machine (which runs the Bazel JVM) is a MacOS machine
and have the identical Xcode version as the BuildBuddy MacOS executor.

# Usage

First, create a `user.bazelrc` file in the root of the repository with your BuildBuddy API key:

```bash
common --remote_header=x-buildbuddy-api-key=aaaabbbbbxxxxcccc
```

Then, ensure that you have identical Xcode version as the BuildBuddy MacOS executor.
For example, if your Executors have Xcode 16.0 installed at `/Applications/Xcode_16.0.app`,
then you would also want to have the same Xcode version installed on your local machine at the same path.

Visit https://xcodereleases.com/ to download relevant Xcode versions.

Then, set your DEVELOPER_DIR to the Xcode path:

```bash
export DEVELOPER_DIR='/Applications/Xcode_16.0.app/Contents/Developer'
```

Then, run the following command to build the example:

```bash
bazel build --config=remote --config=mac //:main
```
