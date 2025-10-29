# *******************************************************************************
# Copyright (c) 2024 Contributors to the Eclipse Foundation
#
# See the NOTICE file(s) distributed with this work for additional
# information regarding copyright ownership.
#
# This program and the accompanying materials are made available under the
# terms of the Apache License Version 2.0 which is available at
# https://www.apache.org/licenses/LICENSE-2.0
#
# SPDX-License-Identifier: Apache-2.0
# *******************************************************************************

load("@rules_rpm//rpm:defs.bzl", "rpm_package")

rpm_package(
    name = "lola_devel_rpm",
    libraries = [
        "//score/mw/com:com",
        "//score/mw/com:config_schema",
    ],
    binaries = [
        "//score/mw/com/example/ipc_bridge:ipc_bridge_cpp",
        "//score/mw/com/example/ipc_bridge:ipc_bridge_rs",
    ],
    data = [
        "//score/mw/com/example/ipc_bridge:etc/mw_com_config.json",
    ],
    config_dir = "/etc/lola",
    data_dir = "/usr/share/lola/examples",
    version = "1.0.0",
    summary = "LOLA Development Libraries",
    description = "LOLA middleware communication libraries for development including core communication, configuration components, and example client/server binaries for testing",
)

rpm_package(
    name = "lola_test_rpm",
    testonly = True,
    binaries = [
        "//score/message_passing/non_allocating_future:non_allocating_future_test",
    ],
    version = "1.0.0",
    summary = "LOLA Test Utilities",
    description = "Test binaries and utilities for validating LOLA middleware installation and integration",
    requires = ["lola-devel"],
)
