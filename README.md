![PEDSnet Animated Logo](images/PEDSnetLogo.gif)
# PEDSnet Reusable Code Repo Template

PEDSnet Reusable Code Repo Template is a blank GitHub repository and README template for reusable code submitted to [PEDSpace](https://pedsnet.org/metadata/home) for ingestion. The [BLANK_README](BLANK_README.md) template is stripped-down fork of the [Best-README-Template](https://github.com/othneildrew/Best-README-Template). We ask that you minimally include the information outlined in this document. 

## How To Use This Template
1. "Use this Template" in GitHub under the PEDSnet organization[^1].
2. Open [`BLANK_README.md`](BLANK_README.md).
3. Change or add any images that best describe your project[^2].
4. Find and replace the following words `repo_name`, `project_title`, `project_description`, `project_license`.
5. Update [`LICENSE.txt`](LICENSE.txt) to reflect your submission's copyright license.
6. Follow the instructions under <a href="#reproducibility">Reproducibility</a>.
7. Delete this `README.md` and rename `BLANK_README.md` to `README.md`.
8. Commit and push to `origin/main`.

### Reproducibility

If you are doing ongoing R development work, I strongly encourage that you do so using [`renv`](https://rstudio.github.io/renv/index.html) e.g. `renv::init()` and `renv::snapshot()`. This will make not only documentation easier but can also improve your development workflow in the long run by ensuring version consistency and improving reproducibility. 

In general, **we require that all code repositories archived to PEDSpace must contain an `renv.lock` file generated from the most up-to-date R environment known to work**. Whether you want to go the full way and also actually use an [renv project library](https://rstudio.github.io/renv/reference/init.html) is up to you[^3], but we *at least* need a list of dependencies, their versions, and the version of R used to execute the script or pipeline. If submitting a package, an `renv.lock` is optional, but we do still need documentation of the R version and key dependency versions used for development (this can be provided via `sessionInfo()` output or similar). You can manually insert those within [README.md](BLANK_README.md#built-with).

To generate the `renv.lock` file, call the following line within your project directory after confirming that your environment can successfully execute the code being deposited:

```R
renv::snapshot()
```

This repo contains a GitHub workflow that will produce a top-level summary of the libraries used and insert it into the [README.md](BLANK_README.md#built-with) as a list of bullet points.

To restore the R environment:

```R
renv::restore()
```


[^1]: Click on the "Use this Template" button in the corner of the window to create a repository using this template, and then clone this repository locally to edit. I recommend [VSCode](https://code.visualstudio.com/) with the [Markdown Preview Enanched extension](https://marketplace.visualstudio.com/items?itemName=shd101wyy.markdown-preview-enhanced), but you can also use a plaintext text editor.

[^2]: Swap out `images/screenshot.png` with a relevant image for your deposit (optional) and uncomment and edit lines 25 and 26 in to display it.

[^3]: Just remember to `.gitignore` your library (e.g. `echo renv/ >> .gitignore`). This repo already has an extensive coverage of ignored files and directories.