---
sort: 3
---

# `:trap. |., "bardot", {$trap p/twig}`

Trap: `|=` with no argument; expression not evaluated automatically.

Produces: a core with a single arm `$` that it takes no arguments and is not automatically
called (you must activate it with the irregular wideform of `%-`, which is
`()`).

Regular form: *1-fixed*

Examples
--------

    /~zod/try=> 
    =a  |.(42)
    changed %a
    /~zod/try=> 
    a
    < 1.yln
      [   a
        < 2.yqy
          [   a
            < 3.kii
              [   a
                < 2.wvx
                  [ a=<2.kqf 2.hng 250.qyy 41.raw 414.hhh 100.xkc 1.ypj %164>
                    <2.hng 250.qyy 41.raw 414.hhh 100.xkc 1.ypj %164>
                  ]
                >
                <2.hng 250.qyy 41.raw 414.hhh 100.xkc 1.ypj %164>
              ]
            >
            <2.hng 250.qyy 41.raw 414.hhh 100.xkc 1.ypj %164>
          ]
        >
        <2.hng 250.qyy 41.raw 414.hhh 100.xkc 1.ypj %164>
      ]
    >
    /~zod/try=> 
    (a)
    42
    /~zod/try=> 
    $:a
    42

This is a simple example. We assign a shell variable `a` to be a trap
that simply produces the atom `42`. Printing `a` prints the core and its
context. Calling `a` using `(`, the irregular form of `%-`, produces
its value. As does pulling the arm `$` from inside it using `$:a`.

    /~zod/try=> 
    =a  10
    changed %a
    /~zod/try=> 
    =b  |.  (add a 2)
    changed %b
    /~zod/try=> 
    (b)
    12

In this case we assign a variable `a` to be `10`, and create a trap `b`
to add `2` to it. This is a trivial example, but is meant to show that
traps are useful when you need a gate that only operates on values that
are already in its context.

    /~zod/try=> 
    =loop  =+  reps=10
           =+  step=0
           =+  outp=0
           |.
           ?:  =(step reps)
             outp
           $(outp (add outp 2), step +(step))
    changed %loop
    /~zod/try=> (loop)
    20

Expanding on our previous example, we create a trap with three local
variables, `reps`, `step`, and `outp`. We use a trap to create a loop,
testing each time if `step` is equal to `reps`, if so producing `outp`
otherwise calling our trap again with `outp` replaced with `outp+2`, and
`step` incremented.
