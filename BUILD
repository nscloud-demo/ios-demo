load("@build_bazel_rules_apple//apple:ios.bzl", "ios_application", "ios_ui_test")
load("@build_bazel_rules_apple//apple/testing/default_runner:ios_test_runner.bzl", "ios_test_runner")
load("@build_bazel_rules_swift//swift:swift.bzl", "swift_library")

swift_library(
    name = "lib",
    srcs = glob(["ios-demo/*.swift"]),
    deps = ["@lottie-ios-prebuilt//:prebuilt"],
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

ios_test_runner(
	name = "iphone15_ios18",
	device_type = "iPhone 15 Pro",
	os_version = "18.0",
)

swift_library(
    name = "ui-tests-lib",
    testonly = True,
    srcs = glob(["ios-demoUITests/*.swift", "fastlane/*.swift"]),
    module_name = "iOSDemoUITests",
    tags = ["manual"],
)

ios_ui_test(
	name = "ui-tests",
	runner = ":iphone15_ios18",
	minimum_os_version = "16.0",
	test_host = ":ios-demo",
	deps = [":ui-tests-lib"],
)