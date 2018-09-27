load("//tools:cpplint.bzl", "cpplint")

package(default_visibility = ["//visibility:public"])

cc_library(
    name = "chi_squared_cdf",
    hdrs = [
        "chi_squared_cdf_1_0.0500_0.999900.h",
        "chi_squared_cdf_2_0.0500_0.999900.h",
    ],
)

cc_library(
    name = "hm_tracks_objects_match",
    srcs = [
        "hm_tracks_objects_match.cc",
    ],
    hdrs = [
        "hm_tracks_objects_match.h",
    ],
    deps = [
        "//modules/perception/common/graph:gated_hungarian_bigraph_matcher",
        ":track_object_distance",
        "//modules/perception/fusion/lib/interface:interface",
        "//modules/perception/common/graph:secure_matrix",
        "//modules/perception/fusion/base:scene",
    ],
)

cc_library(
    name = "probabilities",
    srcs = [
        "probabilities.cc",
    ],
    hdrs = [
        "probabilities.h",
    ],
)

cc_library(
    name = "projection_cache",
    hdrs = [
        "projection_cache.h",
    ],
)

cc_library(
    name = "track_object_distance",
    srcs = [
        "track_object_distance.cc",
    ],
    hdrs = [
        "track_object_distance.h",
    ],
    deps = [
        "//modules/perception/common/sensor_manager:sensor_manager",
        "//modules/perception/fusion/base:fusion_log",
        "//modules/perception/fusion/base:sensor_data_manager",
        "//modules/perception/fusion/base:sensor",
        "//modules/perception/fusion/base:track",
        "//modules/perception/fusion/common:camera_util",
        "//modules/perception/base:point_cloud",
        ":probabilities",
        ":projection_cache",
        ":track_object_similarity",
        "//modules/perception/base:camera",
        "//modules/perception/base:base_type",
        "//modules/perception/common/geometry:camera_homography",
        ":chi_squared_cdf",
    ],
)

cc_library(
    name = "track_object_similarity",
    srcs = [
        "track_object_similarity.cc",
    ],
    hdrs = [
        "track_object_similarity.h",
    ],
    deps = [
        ":chi_squared_cdf",
        "//modules/perception/fusion/base:fusion_log",
        "//modules/perception/fusion/common:camera_util",
        "//modules/perception/fusion/base:sensor",
        ":probabilities",
        ":projection_cache",
    ],
)

cpplint()