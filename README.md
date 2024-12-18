# ticket_304069

RT ticket 304069

- [communication](communication.md)

## Meeting 2024-12-18 9:00-10:00

- Progress
    - Asked colleagues about `-bash`
- User shows complete process after starting a minimal interactive node
  using `interactive -A sens2023036 -n 2 -t 1:00:00`
    - Collect exact error messages
    - Try to run core file using `gdb rstudio core.something`: expected to
      fail
    - Do `killall -bash` and run again
- Check if Richel is added to the project, the meeting was rushed at the end
- Misc
    - [Paper on predicting Slurm waiting time](https://github.com/mila-iqia/slurm-queue-time-pred)
- [x] Richel: Ask why getting an interactive node is slow,
    
![Question on Matrix](20241218_matrix.png)

- [ ] Richel: make timings on:
    - [x] `interactive -A sens2017625 -n 2 -t 1:00:00`: added to [the UPPMAX documentation](https://docs.uppmax.uu.se/cluster_guides/cluster_speeds/)
    - [x] `interactive -A sens2017625 --partition devcore -n 2 -t 1:00:00`: added to [the UPPMAX documentation](https://docs.uppmax.uu.se/cluster_guides/cluster_speeds/)
    - [ ] `interactive -A sens2023036 -n 2 -t 1:00:00`
    - [ ] `interactive -A sens2023036 --partition devcore -n 2 -t 1:00:00`

Attempt|You waited for `x` seconds|Complete time (secs)
-------|--------------------------|--------------------
1      |.                         |.
2      |.                         |.
3      |.                         |.
4      |.                         |.
5      |.                         |.

    - `interactive -A sens2023036 --partition devcore -n 2 -t 1:00:00`: .

Attempt|You waited for `x` seconds|Complete time (secs)
-------|--------------------------|--------------------
1      |.                         |.
2      |.                         |.
3      |.                         |.
4      |.                         |.
5      |.                         |.

## Observations

- RStudio works fine without `R_packages`

## Hypotheses

Most likely at the top

- [?] [H6. The process `-bash` is relevant to the problem](hypothesis_6.md)
- [?] [H7. The RStudio startup messages are relevant to the problem](hypothesis_7.md)
- [POSSIBLE] H2. When trying out another Bianca project, a different setup was used.
  Doing exactly the same script will result in the same results.
- [UNLIKELY] [H4. The `core.` files will be helpful in finding the answer](hypothesis_4.md)
  [UNLIKELY] [H5. The way the user opens RStudio is relevant](hypothesis_5.md)
- [DOES NOT APPLY ANYMORE] [H3. The problem is not in RStudio at all. It is in lmod, as loading modules is slow on Bianca](hypothesis_3.md)
- [REJECTED] [H1. The R version loaded by default is not compatible with the `R_Packages` or `RStudio` module loaded](hypothesis_1.md)
