# NMR Dataset - Test

This repository contains NMR exercises used for student exams. When pushed to `main`, the data is automatically deployed to GitHub Pages and can be accessed via NMRium.

## How it works

Each test folder (e.g., `test_01_BTzvD97I`) contains numbered exercise subfolders. Each exercise folder contains:

- `1h.jdx` — the proton (1H) NMR spectrum
- `structure.mol` — the molecular structure

The folder name includes a random base62 key (e.g., `BTzvD97I`) to prevent students from guessing the URL of other tests.

## Creating a new test

1. Create a new folder with the naming convention `test_XX_<base62key>`, where `XX` is the test number and `<base62key>` is a random 8-character base62 string. You can generate one with:

   ```bash
   node -e "const c='0123456789ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz'; let r=''; for(let i=0;i<8;i++) r+=c[Math.floor(Math.random()*62)]; console.log(r)"
   ```

2. Inside the test folder, create numbered exercise subfolders following the pattern `10_Exercise 1`, `20_Exercise 2`, etc. The numeric prefix controls the display order.

3. Place the `1h.jdx` and `structure.mol` files in each exercise folder.

4. Commit and push to `main`. The GitHub Actions workflow will automatically build and deploy the site.

## Sending the link to students

Once deployed, the test is accessible at:

```
https://app.nmrium.com/teaching/exercises#?toc=https://lpatiny.github.io/nmr-data-test/toc_<folder_name>.json
```

For example, for `test_01_BTzvD97I`:

https://app.nmrium.com/teaching/exercises#?toc=https%3A%2F%2Flpatiny.github.io%2Fnmr-data-test%2Ftoc_test_01_BTzvD97I.json

## Training exercises

The repository also contains training series (not tests):

- `10_solvent` — NMR of organic solvents
- `20_simple` — Simple exercises
- `30_medium` — Medium exercises

<-- LINKS -->
