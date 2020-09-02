cd cargo

cargo generate-lockfile

cargo vendor --versioned-dirs --locked

cargo raze

bazel build //lib