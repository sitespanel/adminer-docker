# Contributing

Thanks for your interest in improving this Adminer image.

## Report a bug

Open an issue with the image tag or digest, what you ran (with secrets removed), what you expected and what happened. A problem in Adminer itself belongs upstream at [vrana/adminer](https://github.com/vrana/adminer).

Security problems go through private vulnerability reporting instead (see [SECURITY.md](SECURITY.md)).

## Submit a pull request

1. Fork the repository and branch from `main`.
2. To move to a new Adminer release, bump `ADMINER_VERSION` and the base image digest together in the `Dockerfile` (`docker buildx imagetools inspect adminer:<version>-standalone`), and check that `ADMINER-LICENSE` still matches that release's LICENSE file.
3. Build and run it locally:
   ```bash
   docker build -t test-adminer .
   docker run --rm -p 127.0.0.1:8080:8080 test-adminer
   ```
4. Open the pull request against `main` with a clear description. CI lints, builds and scans it (a fixable high or critical vulnerability fails the build); it is published only after the merge.
