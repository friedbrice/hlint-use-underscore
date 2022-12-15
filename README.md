# hlint-use-underscore

This project is a minimal demonstration that Hlint doesn't issue the `"Use underscore"` hint unless the `NumericUnderscores` pragma appears in the file in question.

## Steps

1. `cabal build`

   This demonstrates that the language extensions are set up correctly.

2. `hlint .`

   This uses `.hlint.yaml`, which includes `"Use underscore"` at error level and includes `-XNumericUnderscores` as an argument.

## Expected

`hlint` should report an error in each of `src/NoPragma.hs` and `src/WithPragma.hs`.

## Actual

`hlint` ignores errors in `src/NoPragma.hs` and only reports errors in `src/WithPragma.hs`.
