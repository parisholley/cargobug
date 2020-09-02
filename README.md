cd cargo
cargo generate-lockfile
cargo vendor --versioned-dirs --locked
cargo raze
cd ..
bazel build //lib