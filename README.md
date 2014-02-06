# Hop

The simplest Haskell program as a Cabal package.

This is meant to be a simple but complete Cabal package. It provides a library,
an executable, a test suite, and some benchmarks. None of them really do
anything.

The name comes from *H*askell n*op*.

## Setup

``` sh
sudo apt-get -y install haskell-platform
cabal update
cabal install cabal-install
cabal install hsenv
echo 'PATH="$HOME/.cabal/bin"' > ~/.bash_profile
source ~/.bash_profile
hsenv
source .hsenv/bin/activate
cabal install --enable-benchmarks --enable-tests .
cabal install hscolour # TODO: This sucks!
cabal configure --enable-benchmarks --enable-tests
cabal build
cabal haddock --hyperlink-source
cabal test
cabal bench
cabal install
hop
# ...
deactivate_hsenv

```

## Development

``` sh
find . -name '*.hs' -not -path './dist/*' -not -path './.hsenv/*' \
  -print \
  -execdir scan --inplace-modify --multiple-blanks=0 -- '{}' \; \
  -execdir stylish-haskell --inplace -- '{}' \; \
  -execdir hlint --color -- '{}' \;
```

## Links

- <http://www.haskell.org/haskellwiki/How_to_write_a_Haskell_program>
  project layout, recommended libraries and tutorial
- <http://www.haskell.org/haskellwiki/Structure_of_a_Haskell_project>
  project layout and recommended libraries
- <http://semantic.org/hnop/>
  inspiration for this project
- <https://github.com/skogsbaer/HTF/>
  testing framework with links to documentation and tutorial
- <http://book.realworldhaskell.org/read/testing-and-quality-assurance.html>
  quickcheck tutorial
- <http://www.haskell.org/ghc/docs/latest/html/users_guide/hpc.html>
  code coverage
- <http://www.haskell.org/cabal/users-guide/developing-packages.html>
  cabal packaging
- <http://stackoverflow.com/q/9662806/1274282>
  not much by itself, but lots of other good links
  this project aims to solve the question it poses
- <https://github.com/sol/hspec-example>
  example hspec and cabal
