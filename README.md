# ticket_304069

RT ticket 304069

- [communication](communication.md)

## Conclusion

There was a process called `-bash` (yes, a dash/minus before `bash`)
which caused that:
- RStudio never shows the files pane
- RStudio never successfully runs an R command in the interpreter

Killing `-bash` (using `kill -s 1 [PID]`, where `[PID]` is the process ID,
in this case `11723`)(note that `killall -bash` did not work, as `killall`
interpreted `-bash` as a flag :-) ) solved the problem.

## Observations

- RStudio works fine without `R_packages`
- There is a Whisper icon on the desktop

## Hypotheses

Most likely at the top

- [CONFIRMED] [H6. The process `-bash` is relevant to the problem](hypothesis_6.md)
- [REJECTED] [H8: seeing the Whisper icon is relevant to the problem](hypothesis_8.md)
- [REJECTED] [H7. The RStudio startup messages are relevant to the problem](hypothesis_7.md)
- [REJECTED] H2. When trying out another Bianca project, a different setup was used.
  Doing exactly the same script will result in the same results.
- [REJECTED] [H4. The `core.` files will be helpful in finding the answer](hypothesis_4.md)
- [REJECTED] [H5. The way the user opens RStudio is relevant](hypothesis_5.md)
- [REJECTED] [H3. The problem is not in RStudio at all. It is in lmod, as loading modules is slow on Bianca](hypothesis_3.md)
- [REJECTED] [H1. The R version loaded by default is not compatible with the `R_Packages` or `RStudio` module loaded](hypothesis_1.md)
