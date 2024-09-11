# nextjs-trace-to-tree

Next.js trace to tree CLI

This tools is just a package version of [trace-to-tree.mjs](https://github.com/vercel/next.js/blob/canary/scripts/trace-to-tree.mjs) in Next.js repository.

## Usage

1. Generate trace file via `next build` command
2. Run `nextjs-trace-to-tree` command with trace file path

```bash
rm -rf .next && npm run build # next build
npx nextjs-trace-to-tree ./.next/trace # specify trace file path as 1st argument
```

## Explanation

```bash
Explanation:
module /Users/next-user/src/magic-ui/pages/index.js 24 s (total 33 s, self 163 ms) [read-resource 873 µs, next-babel-turbo-loader 135 ms]
       ════════╤═══════════════════════════════════ ═╤═        ═╤═       ═╤════   ═══════════╤════════════════════════════════════════
               └─ name of the processed module       │          │         │                  └─ timings of nested steps
                                                     │          │         └─ building the module itself (including overlapping parallel actions)
                                                     │          └─ total build time of this modules and all nested ones (including overlapping parallel actions)
                                                     └─ how long until the module and all nested modules took compiling (wall time, without overlapping actions)

module lodash (lodash/camelCase.js + 281) 295 ms (self 958 ms) [read-resource 936 ms]
       ═╤════  ══════╤════════════   ═╤═
        │            │                └─ number of modules that are merged into that line
        │            └─ first module that is imported
        └─ npm package name
```

## Details

- https://github.com/vercel/next.js/blob/canary/scripts/trace-to-tree.mjs
- [trace-to-treeでNext.jsの起動タイムをトレースする #パフォーマンス - Qiita](https://qiita.com/BRSF/items/bc13324404ecd7387ec8)
- [Next.jsでtraceの解析結果を表示する](https://zenn.dev/s_takashi/scraps/d13e6300993233)
- [Next.js製アプリケーションのコンパイルを約100倍高速化した話](https://zenn.dev/mkt/articles/543669021d9a1e)

## Contributing

1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request :D

## License

MIT

MIT Vercel

- https://github.com/vercel/next.js/blob/canary/scripts/trace-to-tree.mjs
