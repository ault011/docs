### `++tree`

Tree mold generator

A `++tree` can be empty, or contain a node of a type and
left/right sub `++tree` of the same type. Pretty-printed with `{}`.

Source
------

    ++  tree  |*  a/$-(* *)                                 ::  binary tree
              $@($~ {n/a l/(tree a) r/(tree a)})            ::


Examples
--------

    ~zod/try=> `(tree {@ tape})`[[1 "hi"] [[2 "bye"] ~ ~] ~]
    {[2 "bye"] [1 "hi"]}



***
