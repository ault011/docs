# `:claw, $@, "bucpat", {$claw p/moss q/moss}`

Type: either an atom or a cell.

Product: a mold which applies `p` if its sample is an atom, 
`q` if its sample is a cell.

Regular form: *2-fixed*.

Example:
```
~zod:dojo> =a :claw($foo :bank(p/$bar q/@ud))

~zod:dojo> (a %foo)
%foo

~zod:dojo> `a`[%bar 99]
[p=%bar q=99]

~zod:dojo> $:a
[%foo p=0 q=0]
```
