# makerelease

*This quick start guide is based on the guide found on GoReleaser.com, and modified brevity and relevance.*

## Quick Start

1. Run `brew install goreleaser/tap/goreleaser` to install Goreleaser.

2. Create a [new GitHub repository](https://github.com/new) named `homebrew-hellohomebrew` **exactly**.

3. [Import a GitHub repository](https://github.com/new/import) and match this screenshot **exactly**:

   <p align="center"><img src="import.png" width="550"></p>

4. Clone your repository locally and `cd makerelease`:

   ```bash
   git clone https://github.com/TODO_GITHUB_USERNAME/makerelease
   ```

5. Create a new module by running:

   ```bash
   go mod init github.com/TODO_GITHUB_USERNAME/makerelease
   ```

6. Open `.goreleaser.yml` and change `TODO_GITHUB_USERNAME` to your GitHub username.

> GoReleaser will build the binaries for your app for Windows, Linux and macOS, both amd64 and i386 architectures. You can customize that by changing the `builds` section. Check the [documentation](https://goreleaser.com/build) for more information.

> After building the binaries, GoReleaser will create an archive for each OS/Arch pair into a separate file. You can customize several things by changing the `archive` section, including releasing only the binaries and not creating archives at all. Check the [documentation](https://goreleaser.com/archive) for more information.

7. You’ll need to export a `GITHUB_TOKEN` environment variable, which should contain a valid GitHub token with the `repo` scope or GitLab token with `api` scope. It will be used to deploy releases to your GitHub/GitLab repository. You can create a token [here](https://github.com/settings/tokens/new) for GitHub.

   ```sh
   $ export GITHUB_TOKEN=`YOUR_GH_TOKEN`
   ```

8. GoReleaser will use the latest [Git tag](https://git-scm.com/book/en/v2/Git-Basics-Tagging) of your repository. Create a tag and push it to GitHub:

   ```bash
   $ git tag -a v0.1.0 -m "First release"
   $ git push origin v0.1.0
   ```

9. Test everything before doing a release “for real."
   This command only builds and packages your code:

   ```bash
   $ goreleaser release --skip-publish
   ```

10. If it worked, run GoReleaser at the root of your repository:

   ```bash
   $ goreleaser
   ```

11. That’s all! Check your GitHub project’s release page to see your latest release!
