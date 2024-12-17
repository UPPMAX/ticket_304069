# ticket_304069

RT ticket 304069

- [communication](communication.md)

## Hypotheses

Most likely at the top

- H4. The `core.` files wll be helpful in finding the answer.
  See 'Open question 2: reading the `core.` files.
- [NEED USER] H2. When trying out another Bianca project, a different setup was used.
  Doing exactly the same script will result in the same results.
- [NEED ANSWER FROM COLLEAGUES] H3. The problem is not in RStudio at all. It is in lmod, as loading
  modules is slow on Bianca
  See 'Open question 1: loading `R_packages/4.3.1`' for details
- [UNLIKELY: works fine without `R_packages`]
  H5. The way the user opens RStudio is relevant
- [REJECTED] H1. The R version loaded by default is not compatible with the `R_Packages`
  or `RStudio` module loaded.
  Rejected by 'Open question 1: loading `R_packages/4.3.1`'.

## Open questions

- What is the content of the `core.[number]` files?
  See 'Open question 2: reading the `core.` files'.
- [IRRELEVANT: RStudio works fine without `R_packages`]
  How does the user start RStudio: `rstudio` or `rstudio &`?
  See 'Open question 3: how is RStudio started?'.
- [ANSWERED: YES] Does the same happen when using `bianca.uppmax.uu.se`?

## Open question 1: loading `R_packages/4.3.1`

- Does loading R_packages/4.3.1 load R?
    - Yes
- Which version?
    - 4.3.1
- Is it allways the same version?
    - Yes
- Does it always take around the same time?
    - Yes

For details, see [module_load.md](module_load.md)

## 'Open question 2: reading the `core.` files

They are in the `core_files` folder

Do:

```bash
cd core_files
interactive -A sens2017625 -n 2 -t 2:00:00
module load R_packages/4.3.1
module load RStudio/2023.12.1-402
gdb rstudio core.7641
```

## [IRRELEVANT] Open question 3: how is RStudio started?

- How does the user start RStudio? `rstudio` or `rstudio &`?
- Do I see a difference when I do it?

On the meeting of 2024-12-06 the user stated that
running RStudio without `R_packages` works fine.
Hence, it seems irrelevant how RStudio is started exactly

Use `richel-sens2017625`, then:

```
time interactive -A sens2017625 -n 2 -t 2:00:00
time module load R_packages/4.3.1
time module load RStudio/2023.12.1-402
time rstudio
time rstudio &
```

