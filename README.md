# nextjs-trace-to-tree

Next.js trace to tree CLI

## Usage

1. Generate trace file via `next build` command
2. Run `nextjs-trace-to-tree` command with trace file path

```bash
npm run build # next build
npx nextjs-trace-to-tree ./.next/trace # specify trace file path as 1st argument
```

## Details

- https://github.com/vercel/next.js/blob/canary/scripts/trace-to-tree.mjs
- [trace-to-treeでNext.jsの起動タイムをトレースする #パフォーマンス - Qiita](https://qiita.com/BRSF/items/bc13324404ecd7387ec8)
- [Next.jsでtraceの解析結果を表示する](https://zenn.dev/s_takashi/scraps/d13e6300993233)

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
