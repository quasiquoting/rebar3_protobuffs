rebar3 protobuffs provider
==========================

Provider to compile [Protocol Buffers][] files using [erlang_protobuffs][].
[Protocol Buffers]: https://developers.google.com/protocol-buffers
[erlang_protobuffs]: https://github.com/basho/erlang_protobuffs

Place your `.proto` files in the `src` directory and they will be automatically
built.

Alternatively, specify a `proto_dir` [configuration parameter][1] in your
[application resource file][2].
[1]: http://www.erlang.org/doc/design_principles/applications.html#id76014
[2]: http://www.erlang.org/doc/design_principles/applications.html#id75484

Usage
-----

Add the plugin to your rebar config:

```erlang
{plugins, [rebar3_protobuffs]}.
```

The compile function is in the protobuffs namespace. To automatically compile
`.proto` files before the Erlang compiler, add a `pre_hook` to your
rebar.config:

```erlang
{provider_hooks, [{pre, [{compile, {protobuffs, compile}}]}]}.
```
