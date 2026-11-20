# Import the generated PNG artwork

The GitHub connection can edit text files but cannot directly upload the generated PNG binary assets. To finish switching the GitHub preview from SVG concepts to the generated images:

1. Download `artwork-import.zip` from the ChatGPT response.
2. Open the repository root on GitHub and select **Add file → Upload files**.
3. Upload **the ZIP file itself** with the exact name `artwork-import.zip` to the repository root on `main` (do not unzip it first).
4. Commit the upload. A GitHub Actions workflow named **Import generated Decocraft artwork** runs automatically on that push. When it succeeds, it extracts `assets/<pack>/banner.png` and `assets/<pack>/keyart.png`, updates the hub/README and pack Markdown image paths, and removes the imported ZIP from the repository.
5. Refresh the [hub preview](hub/README.md) and check a [pack page](packs/megapack.md).

The logos in the ZIP are transparent PNG cutouts isolated from the previously generated 16-banner artwork sheet. Because the original images contain scenery behind and around some letters, these are *rough logo cutouts* and may require manual edge cleanup for final publication. The `keyart.png` images are crops from the original generated Minecraft-themed 4×4 artwork sheet. Storefront copy and release dependencies remain drafts pending verification.

If the workflow is blocked by repository permissions, set **Settings → Actions → General → Workflow permissions** to **Read and write permissions** and rerun the workflow. A branch protection policy can also prevent the automated push.
