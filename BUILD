platform(
    name = "macos",
    constraint_values = [
        "@platforms//os:macos",
        "@platforms//cpu:aarch64",
    ],
    exec_properties = {
        "OsFamily": "Darwin",
        "Arch": "arm64",
        "use-self-hosted-executors": "true",
    },
)

cc_binary(
    name = "main",
    srcs = ["main.cc"],
)
