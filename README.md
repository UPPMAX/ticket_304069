# ticket_304069

RT ticket 304069

## Hypothesis

- H1. The R version loaded by default is not compatible with the `R_Packages` or `RStudio` module loaded

## Open questions

- What is the content of the `core.[number]` files?
- Does the same happen when using `bianca.uppmax.uu.se`?

## Nov 18 15:20:47 2024

> I have been having problems with my interactive RStudio sessions on bianca
> since last Friday. 

Which is Friday 15th November 2024, which is way after
the [maintenance on November 3rd](https://status.uppmax.uu.se/2024-11-03/november-maintenance/)
and before
[a next system status message (regarding Rackham) on 22nd November](https://status.uppmax.uu.se/2024-11-22/rackham-failed-jobs/)

> The RStudio interface is quite sluggish and gets stuck either just loading or in doing a simple task like loading an R package (for example limma). I wonder if there is something that has gone awry with my project or what has changed to cause this. I encounter this even when bianca is not particularly busy. I have tried shutting down my virtual session and logging in again several times, as well as restarting my browser, and still encounter a sluggish session. Below are the commands I use:

```text
## start an interactive session with a whole node ( I also tried variations of this with a few cores)
interactive -A sens2023036 -p node -t 2-10

## load R_packages module
module load R_packages/4.3.1

## load RStudio module
module load RStudio/2023.12.1-402

## start RStudio
rstudio
```

> The attached screenshots show the unchanged state of the session after several
> hours. 


![Session at 10:55](image001.png)

Session at 10:55

![Session at 11:44](image002.png)

Session at 11:44

> I also noticed “core” files appearing in my home path.
> I am attaching a screenshot of those as well.

![](image003.png)

> Could there be an issue with my project specifically
> or what do you think could be explaining the lag?

