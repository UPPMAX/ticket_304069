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

Does loading R_packages/4.3.1 load R?
Which version?
Is it allways the same version?
Does it always take around the same time?

Project    |Setting                     |R module version|Real loading time
-----------|----------------------------|----------------|-----------------
Rackham    |SSH                         |4.3.1           |0m0.758s
sens2016001|SSH                         |Unknown         |Unknown
sens2023598|SSH                         |4.3.1           |6m1.265s
sens2023598|Website                     |4.3.1           |6m20.234s
sens2017625|SSH                         |4.3.1           |6m4.584s
sens2017625|Website, interactive session|4.3.1           |7m41.433s
sens2017625|SSH, interactive session    |4.3.1           |7m13.111s

This rejects H1.

For details, see [module_load.md](module_load.md)

I created this post at 2024-12-06 11:06:

![Matrix post](module_load_r_packages_matrix.png)

> When I do time module load R_packages/4.3.1 I get load times that differ by
> a factor of >100x between Rackham (less then 1 second) and Bianca 
> (more then 6 minutes). Is there a reason for this? Exact timings and what I
> did can be found at
> https://github.com/UPPMAX/ticket_304069/blob/master/module_load.md#answers

This timing is indeed off! The sysexperts are working on it.

## 'Open question 2: reading the `core.` files

They are in the `core_files` folder

Do:

```bash
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

