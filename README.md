# Haskell unfoldr Space Leak

This repository demonstrates a space leak in Haskell that can occur when using the `unfoldr` function to generate large lists.  The problem stems from lazy evaluation;  `unfoldr` creates thunks, which consume memory, even if the generated list isn't fully evaluated. This can lead to OutOfMemory errors when processing extensive datasets.

The `unfoldrBug.hs` file contains the problematic code. The `unfoldrSolution.hs` shows a solution to mitigate the space leak.