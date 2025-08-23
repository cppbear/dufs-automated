# Dufs (Automated Builds)

This is a synchronized fork of the [dufs](https://github.com/sigoden/dufs) repository.

The primary purpose of this repository is to automatically build the latest code from the upstream `main` branch and publish the compiled artifacts to GitHub Releases. This allows users to easily access and test the latest features.

## How It Works

1. A scheduled GitHub Actions workflow, based on the implementation from the [lobe-chat](https://github.com/lobehub/lobe-chat) project, periodically checks the upstream repository's `main` branch for new commits.
2. When new commits are detected, they are synced to the `upstream-main` branch in this repository.
3. A push to the `upstream-main` branch triggers the build and release workflow, which compiles binaries for all supported platforms.
4. Once the build is successful, a new release is automatically created with the compiled artifacts.

## Key Differences from the Original Project

Compared to the official releases, this repository provides an additional binary for the `*-win7-windows-msvc` target in its GitHub Releases. This build is compiled using the **Nightly** Rust toolchain to enable support for this specific target.

## ⚠️ Important Notices

Before using any files published in this repository, please be aware of the following:

* **Builds are from a development branch**: All builds are based directly on the upstream repository's `main` branch. This means you are downloading a version that may contain new features or potential bugs that have not been thoroughly tested. **Please use with caution in production environments.**

* **Risks associated with the `*-win7-windows-msvc` build**:

  > Please be aware that `*-win7-windows-msvc` is a Tier 3 target, which means it is not officially supported by the Rust team and may not be guaranteed to work. Additionally, using a nightly toolchain comes with its own risks, as it can be unstable and introduce breaking changes at any time.

## Downloads

You can find all automated builds on the **[Releases page](https://github.com/cppbear/dufs-automated/releases)** of this repository.

## Acknowledgments

All source code is from the [dufs](https://github.com/sigoden/dufs) repository. Full credit goes to its original author(s) and contributors.

The GitHub Actions workflow for syncing with the upstream repository is adapted from the excellent work done by the [lobe-chat](https://github.com/lobehub/lobe-chat) project.
