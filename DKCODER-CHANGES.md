# DkCoder Changes

## No native toploop

In 0.3.0 we'd get:

```text
+  ocamlfind ocamlopt -c -g -bin-annot -safe-string -package compiler-libs.toplevel -I src -I test -o src/down_nattop.cmx src/down_nattop.ml
File "src/down_nattop.ml", line 6, characters 64-74:

6 | let () = if !Sys.interactive then (Down.Private.set_top (module Opttoploop))

                                                                    ^^^^^^^^^^

Error: Unbound module Opttoploop

Command exited with code 2.
```

But DkCoder does not compile with a native compiler.

Solution: <https://github.com/dbuenzli/down/issues/33> is finished so that `ocamlnat` does not need to be detected.
So can mark this section as finished _after_ 0.3.1 or later release.
