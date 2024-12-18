# ticket_304069

RT ticket 304069

- [communication](communication.md)

## Observations

- RStudio works fine without `R_packages`
- Getting an interactive node takes more than two hours
- There is a Whisper icon on the desktop

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
