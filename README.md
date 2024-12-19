# ticket_304069

RT ticket 304069

- [communication](communication.md)

## Postmortem

There was a process called `-bash` (yes, a dash/minus before `bash`)
which caused that:
- RStudio never shows the files pane
- RStudio never successfully runs an R command in the interpreter

Killing `-bash` (using `kill -s 1 [PID]`, where `[PID]` is the process ID,
in this case `11723`)(note that `killall -bash` did not work, as `killall`
interpreted `-bash` as a flag :-) ) solved the problem.

## Meeting of 2024-12-19 13:00

- Progress
    - can log in to user's project
        - Found 'It tends to be a matter of minutes to less than hours before the changes propagate from SUPR to UPPMAX', from https://docs.uppmax.uu.se/getting_started/project_apply
    - can now start interactive nodes in project
    - login nodes should take less than 10 minutes to start
    - added measurements to UPPMAX documentation at
      [https://docs.uppmax.uu.se/cluster_guides/cluster_speeds/#starting-an-interactive-session-with-two-cores-for-one-hour](https://docs.uppmax.uu.se/cluster_guides/cluster_speeds/#starting-an-interactive-session-with-two-cores-for-one-hour)
- User shows complete process after starting a minimal interactive node

```bash
interactive -A sens2017625 -n 2 -t `:00:00
module load R_packages/4.3.1
module load RStudio/2023.12.1-402
gdb rstudio core.7641
rstudio
killall -bash
rstudio
```

    - Collect exact error messages
    - Try to run core file using `gdb rstudio core.something`: expected to
      fail
    - Do `killall -bash` and run again

```
13:00:42 From Richèl 'Rea-shell' Bilderbeek To Everyone:
	module load R_packages/4.3.1
	module load RStudio/2023.12.1-402
	gdb rstudio core.7641
	rstudio
	killall -bash
	rstudio
13:06:18 From Richèl 'Rea-shell' Bilderbeek To Everyone:
	killall -bash
13:08:11 From Richèl 'Rea-shell' Bilderbeek To Everyone:
	kill --signal 15 11723
13:09:43 From Richèl 'Rea-shell' Bilderbeek To Everyone:
	kill -s 1 11723
13:20:07 From Richèl 'Rea-shell' Bilderbeek To Everyone:
	module load R_packages/4.3.1
	module load RStudio/2023.12.1-402
```


## Observations

- RStudio works fine without `R_packages`
- There is a Whisper icon on the desktop

## Hypotheses

Most likely at the top

- [?] [H8: seeing the Whisper icon is relevant to the problem](hypothesis_8.md)
- [?] [H6. The process `-bash` is relevant to the problem](hypothesis_6.md)
- [?] [H7. The RStudio startup messages are relevant to the problem](hypothesis_7.md)
- [POSSIBLE] H2. When trying out another Bianca project, a different setup was used.
  Doing exactly the same script will result in the same results.
- [UNLIKELY] [H4. The `core.` files will be helpful in finding the answer](hypothesis_4.md)
- [UNLIKELY] [H5. The way the user opens RStudio is relevant](hypothesis_5.md)
- [DOES NOT APPLY ANYMORE] [H3. The problem is not in RStudio at all. It is in lmod, as loading modules is slow on Bianca](hypothesis_3.md)
- [REJECTED] [H1. The R version loaded by default is not compatible with the `R_Packages` or `RStudio` module loaded](hypothesis_1.md)
