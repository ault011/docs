### `++hard`

Demands that a specific type be produced, crashing the program is it is
not.

Source
------

    ++  cury                                                ::  curry left
      |*  {a/_|=(^ **) b/*}
      |*  c/_+<+.a
      (a b c)
    ::

Examples
--------

    ~zod/try=> ((hard (list)) (limo [1 2 3 ~]))
    ~[1 2 3]
    ~zod/try=> ((hard @) (add 2 2))
    4
    ~zod/try=> ((hard @t) (crip "Tape to cord, bro!"))
    'Tape to cord, bro'
    ~zod/try=> ((hard tape) (crip "...Tape to cord, bro?..."))
    ! hard
    ! exit



***
