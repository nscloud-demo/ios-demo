load("@build_bazel_rules_apple//apple:ios.bzl", "ios_dynamic_framework")
load("@build_bazel_rules_apple//apple:apple.bzl", "apple_dynamic_framework_import")
load("@build_bazel_rules_swift//swift:swift.bzl", "swift_library")

apple_dynamic_framework_import(
    name = "prebuilt",
    framework_imports = glob(["Lottie.framework/**"]),
    dsym_imports = glob(["dSYMs/**"]),
    visibility = ["//visibility:public"],
)

# swift_library(
#     name = "LottieCore",
#     module_name = "Lottie",
#     srcs = glob([
#         "Sources/**/*.swift",
#     ]),
#     visibility = ["//visibility:public"],
# )

# genrule(
#     name = "LottieInfoPlist",
#     outs = ["Lottie-Info.plist"],
#     cmd = """
# cat << 'EOF' > $@
# <?xml version="1.0" encoding="UTF-8"?>
# <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
# <plist version="1.0">
# <dict>
#     <key>CFBundleDevelopmentRegion</key>
#     <string>en</string>
#     <key>CFBundleExecutable</key>
#     <string>$$(EXECUTABLE_NAME)</string>
#     <key>CFBundleIdentifier</key>
#     <string>$$(PRODUCT_BUNDLE_IDENTIFIER)</string>
#     <key>CFBundleInfoDictionaryVersion</key>
#     <string>6.0</string>
#     <key>CFBundleName</key>
#     <string>$$(PRODUCT_NAME)</string>
#     <key>CFBundlePackageType</key>
#     <string>FMWK</string>
#     <key>CFBundleShortVersionString</key>
#     <string>4.3.3</string>
#     <key>CFBundleVersion</key>
#     <string>4.3.3</string>
#     <key>NSPrincipalClass</key>
#     <string></string>
# </dict>
# </plist>
# EOF
#     """,
#     visibility = ["//visibility:public"],
# )

# ios_dynamic_framework(
#     name = "Lottie",
#     bundle_id = "com.airbnb.lottie",
#     families = [
#         "iphone",
#         "ipad",
#     ],
#     infoplists = [":LottieInfoPlist"],
#     minimum_os_version = "11.0",
#     deps = [
#         ":LottieCore",
#     ],
#     visibility = ["//visibility:public"],
#     extension_safe = True,
# )