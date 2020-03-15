# cacheDependencyLoader
cacheDependencyLoader for webpack

```
{
  module: {
    rules: [
      {
        test: /[\\/]src[\\/]assets[\\/]index\.html$/,
        use: [
          {
            loader: Path.resolve("./src/tools/cacheDependencyLoader.js"),
            options: {
              dependencies: [Path.resolve("./src/indexPrerender")]
            }
          },
          {
            loader: "prerender-loader",
            options: {
              string: true
            }
          }
        ]
      }
    ]
  },
  plugins: [
    new HtmlWebpackPlugin({
      filename: "../index.html",
      template: "./src/assets/index.html",
      minify: {
        html5: true,
        removeComments: true,
        collapseWhitespace: true
      }
    })
  ]
};
```
