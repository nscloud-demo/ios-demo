load("@build_bazel_rules_apple//apple:ios.bzl", "ios_application")
load("@build_bazel_rules_swift//swift:swift.bzl", "swift_library")

swift_library(
    name = "lib",
    srcs = glob(["ios-demo/*.swift"]),
)

ios_application(
    name = "ios-demo",
    bundle_id = "so.namespace.ios-demo",
    families = ["iphone"],
    infoplists = ["ios-demo/Resources/Info.plist"],
	app_icons = glob(["ios-demo/Assets.xcassets/AppIcon.appiconset/*"]),
    minimum_os_version = "16.0",
    visibility = ["//visibility:public"],
    deps = [":lib"],
)