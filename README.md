# pnpm list bug

A project to demonstrate that `pnpm list --only-projects` does not work if `shared-workspace-lockfile = false` is
specified in .npmrc.

To see the issue, run `pnpm list --only-projects --depth Infinity` and notice that the output is empty.

Expected result:

```
Legend: production dependency, optional only, dev only

root@1.0.0 <path to project>

dependencies:
@scope/a link:lib/a
└─┬ @scope/b link:lib/b
  └── @scope/c link:lib/c

```

Note: This project is a copy of PNPM's [workspace-with-nested-workspace-deps test fixture][], with the only changes
being the addition of this README.md file, and an .npmrc file.

[workspace-with-nested-workspace-deps test fixture]: https://github.com/pnpm/pnpm/tree/b0afd78339af0daf171474182e02de0096daf529/__fixtures__/workspace-with-nested-workspace-deps
