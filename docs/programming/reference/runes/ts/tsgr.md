# `:per`, `=>`, "tisgar" `{$per p/twig q/twig}`

`p` as subject of `q`.

Uses the product of `p` as the subject of formula `q`. For code readability,
use `=>` when your `p` isn't as long as `q`, and `=<` when `q` is longer than
`p`.

Regular form: *2-fixed*

Examples:

    ~zod/try=> =>([a=1 b=2 c=3] b)
    2
    ~zod/try=> =>((add 2 4) [. .])
    [6 6]

In this simple example we first produce `b` from the tuple
`[a=1 b=2 c=3]` using the wide form of `=>`. Then we use `.` to produce
our context from the computation `(add 2 4)` as a cell, `[6 6]`.

    ~zod/try=> 
    =cor  |=  a=@
          =+  b=0
          =>  .(b (add 2 b))
          =>  .(a (add a b))
          [a b]
    new var %cor
    /~zod/try=> 
    (cor 4)
    [6 2]

Here we see a common pattern for using `=>` to conduct procedural
changes to values in our subject. First we replace `b` with `b+2` using
the irregular form of `%-`, then we replace `a` with the sum of `a` and
`b` the same way.
