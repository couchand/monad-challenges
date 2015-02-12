# Chains of Failing Computations

In MCPrelude we have defined the following type alias for you.

    type GreekData = [(String, [Integer])]

We also provide a data structure `ex09Data :: GreekData` that has some sample
data.

Write a function to query the above data structure.  Your function should have
the following type signature:

    ex09 :: GreekData -> String -> Maybe Double

Your implementation of this function should use the five functions you wrote
in exercise #8 to do the following.  First query the GreekData that is passed
in, look up the string passed in the second argument, and retrieve the
corresponding list of Integers.  Call this list xs.  Next calculate the
maximum of the tail of xs.  Take the maximum and divide it by the head of the
list.  If any of these operations along the way return Nothing, then your
function should return Nothing.  But if everything succeeds, then return the
final quotient.  One hint...you'll need to use the fromIntegral function to convert your two integers to Doubles for the final call to divMay.

If you thought maximumMay from the previous exercise was annoying, then you'll
think this is REALLY annoying.  Stick with us though...there is a point.

Your function should generate the following results:

    ex09 ex09DataA "alpha" == Just 2.0
    ex09 ex09DataA "beta" == Nothing
    ex09 ex09DataA "gamma" == Just 156.66666666666666
    ex09 ex09DataA "delta" == Nothing
    ex09 ex09DataA "zeta" == Nothing

    ex09 ex09DataB "rho" == Nothing
    ex09 ex09DataB "phi" == Just 0.24528301886792453
    ex09 ex09DataB "chi" == Just 72.76190476190476
    ex09 ex09DataB "psi" == Nothing
    ex09 ex09DataB "omega" == Just 1968.0
    
If your function threw any kind of exception on any of those inputs, then your
implementation is wrong.  Make sure your function always returns a Nothing or
a Just in every case.
