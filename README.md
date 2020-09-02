cd cargo

cargo generate-lockfile

cargo vendor --versioned-dirs --locked

cargo raze

bazel build //lib


`
ERROR: /Users/pholley/projects/cargobug/cargo/vendor/openssl-sys-0.9.58/BUILD.bazel:31:19: CargoBuildScriptRun cargo/vendor/openssl-sys-0.9.58/openssl_sys_build_script.out_dir failed (Exit 1) cargo_build_script_runner failed: error executing command bazel-out/host/bin/external/io_bazel_rules_rust/cargo/cargo_build_script_runner/cargo_build_script_runner bazel-out/host/bin/cargo/vendor/openssl-sys-0.9.58/openssl_sys_build_script_script_ openssl-sys ... (remaining 5 argument(s) skipped)

Use --sandbox_debug to see verbose messages from the sandbox
thread 'main' panicked at '
Header expansion error:
Error { kind: ToolExecError, message: "Command \"/private/var/tmp/_bazel_pholley/9f9e605bd7d2f0565508e2cf43bf7f1a/sandbox/darwin-sandbox/298/execroot/__main__/external/local_config_cc/cc_wrapper.sh\" \"-O3\" \"-ffunction-sections\" \"-fdata-sections\" \"-fPIC\" \"-m64\" \"-arch\" \"x86_64\" \"-I\" \"/usr/local/opt/openssl@1.1/include\" \"-Wall\" \"-Wextra\" \"-E\" \"build/expando.c\" with args \"cc_wrapper.sh\" did not execute successfully (status code exit code: 1)." }

Failed to find OpenSSL development headers.

You can try fixing this setting the `OPENSSL_DIR` environment variable
pointing to your OpenSSL installation or installing OpenSSL headers package
specific to your distribution:

    # On Ubuntu
    sudo apt-get install libssl-dev
    # On Arch Linux
    sudo pacman -S openssl
    # On Fedora
    sudo dnf install openssl-devel

See rust-openssl README for more information:

    https://github.com/sfackler/rust-openssl#linux
', cargo/vendor/openssl-sys-0.9.58/build/main.rs:140:13
stack backtrace:
   0:        0x106e6f83f - <std::sys_common::backtrace::_print::DisplayBacktrace as core::fmt::Display>::fmt::h83d53b696ac99295
   1:        0x106e9184e - core::fmt::write::hf81c429634e1f3ed
   2:        0x106e6c5a7 - std::io::Write::write_fmt::had2a3b01a2c037b5
   3:        0x106e7194a - std::panicking::default_hook::{{closure}}::ha991e4eca34b4afa
   4:        0x106e7168c - std::panicking::default_hook::h722aa3f5c1c31788
   5:        0x106e71f18 - std::panicking::rust_panic_with_hook::h2cd47f71d6d55501
   6:        0x106e71ae2 - rust_begin_unwind
   7:        0x106e984ab - std::panicking::begin_panic_fmt::h769fb8929973777e
   8:        0x106e3857e - openssl_sys_build_script_script_::validate_headers::h0d53bbb17460b273
   9:        0x106e360eb - openssl_sys_build_script_script_::main::hde7c910b4d45dc77
  10:        0x106e3bb16 - std::rt::lang_start::{{closure}}::hc67ed21eb2616b1e
  11:        0x106e72279 - std::rt::lang_start_internal::h1069bf3e81ece2dd
  12:        0x106e388f9 - main
Build Script Warning: clang: error: no such file or directory: 'build/expando.c'

Build Script Warning: clang: error: no input files

Error: "Build script process failed with exit code 101"
X86_64_APPLE_DARWIN_OPENSSL_LIB_DIR unset
OPENSSL_LIB_DIR unset
X86_64_APPLE_DARWIN_OPENSSL_INCLUDE_DIR unset
OPENSSL_INCLUDE_DIR unset
X86_64_APPLE_DARWIN_OPENSSL_DIR unset
OPENSSL_DIR unset
OPT_LEVEL = Some("3")
TARGET = Some("x86_64-apple-darwin")
HOST = Some("x86_64-apple-darwin")
CC_x86_64-apple-darwin = None
CC_x86_64_apple_darwin = None
HOST_CC = None
CC = Some("/private/var/tmp/_bazel_pholley/9f9e605bd7d2f0565508e2cf43bf7f1a/sandbox/darwin-sandbox/298/execroot/__main__/external/local_config_cc/cc_wrapper.sh")
CFLAGS_x86_64-apple-darwin = None
CFLAGS_x86_64_apple_darwin = None
HOST_CFLAGS = None
CFLAGS = None
CRATE_CC_NO_DEFAULTS = None
DEBUG = None
CARGO_CFG_TARGET_FEATURE = None
running: "/private/var/tmp/_bazel_pholley/9f9e605bd7d2f0565508e2cf43bf7f1a/sandbox/darwin-sandbox/298/execroot/__main__/external/local_config_cc/cc_wrapper.sh" "-O3" "-ffunction-sections" "-fdata-sections" "-fPIC" "-m64" "-arch" "x86_64" "-I" "/usr/local/opt/openssl@1.1/include" "-Wall" "-Wextra" "-E" "build/expando.c"
exit code: 1
Target //lib:lib failed to build
Use --verbose_failures to see the command lines of failed build steps.
ERROR: /Users/pholley/projects/cargobug/lib/BUILD:3:13 CargoBuildScriptRun cargo/vendor/openssl-sys-0.9.58/openssl_sys_build_script.out_dir failed (Exit 1) cargo_build_script_runner failed: error executing command bazel-out/host/bin/external/io_bazel_rules_rust/cargo/cargo_build_script_runner/cargo_build_script_runner bazel-out/host/bin/cargo/vendor/openssl-sys-0.9.58/openssl_sys_build_script_script_ openssl-sys ... (remaining 5 argument(s) skipped)

Use --sandbox_debug to see verbose messages from the sandbox
`