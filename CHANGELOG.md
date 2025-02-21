# 1.7.0

- Fix definitions of `catch_not_found`, `catch_sys_error`
- Add:
    + `IO_Exceptions.catch_any_exc`
    + in `Stdlib`: `input`, `really_input`, `really_input_string`
    + `IO_Sys.OSys.argv`.

# 1.6.0

- Add `RunIO` command to compile and run executables from a Coq file
- Rename `Pervasives` to `Stdlib` in extracted code (for OCaml >= 4.08)
- Add new definitions from the stdlib:

    + `IO_Stdlib.close_out_noerr`
    + `IO_Stdlib.close_in_noerr`
    + `IO_Stdlib.in_channel_length`
    + `IO_Exceptions.catch_sys_error`
    + `IO_Sys.OSys.command`

# 1.5.0

- Add `IO_MonadFix` with the `MonadFix` instance in its own module.
- Add float arithmeti.
- Add `Bytes.sub`, `Unix.getaddrinfo`, `Sys.time` (and related definitions)

# 1.4.0

- Remove instance `MonadFix_IO` (was causing universe inconsistencies)
- Add in `Unix`:

    + `inet_addr_of_string`, `string_of_inet_addr`
    + `socket_bool_option`, `getsockopt`, setsockopt`
    + `error_message`

# 1.3.0

- Fix the extraction of core `IO` constants with type annotations to avoid
  type errors caused by the value restriction.
- Add `IO_Sys`, based on `Sys` from the OCaml stdlib.
- Add `file_descr_eqb` and `select` in `IO_Unix`.
- Fix extraction of `error` and `catch_error` in `IO_Unix`.
- Update `IO.Notations` to agree with *coq-ext-lib* 0.11.1

# 1.2.1

- Blacklisted `List`

# 1.2.0

- Added module `IO_Float`
- Added `OString.escaped`, `OUnix.setsock_timeout`, `OUnix.error`,
  `OUnix.catch_error`, `OUnix.raise_error`
- Fixed extraction of `OBytes.set`
- Changed `IO_Unix.recv` to no longer return the input buffer
- Changed `OBytes.to_string` and `OBytes.from_string` to be `IO` actions
  instead of pure functions

# 1.1.0

- Added `IO_Stdlib`, `IO_Bytes`, `IO_Random`, `IO_Unix`

# 1.0.0

- Big rewrite

- `IO a` is now `('a -> Obj.t) -> Obj.t` (`forall r. (a -> r) -> r`)
- A single main entry point: `SimpleIO.SimpleIO` (plus optional unsafe modules)
- New functions for strings and exceptions

# 0.2

- Removed ocaml library. `IO` is now defined in OCaml by extraction simply as
  `('a -> unit) -> unit`.
- Add `delay_io`

# 0.1

Initial release
