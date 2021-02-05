# Official Lucky Framework Heroku Buildpack

You can create an app in Heroku with:

```bash
$ heroku create myapp --buildpack lucky-framework/lucky
```

The default behaviour is to use the [latest crystal release](https://github.com/crystal-lang/crystal/releases/latest).
If you need to use a specific version create a `.crystal-version` file in your
application root directory with the version that should be used (e.g. `0.17.1`).

## Requirements

The stock generated lucky config will run as expected.

If your application was generated with `lucky` before 2021-Feb, you may need to add a shard target to your shard.yml file:

```diff
name: project_name
version: 0.1.0

targets:
# replace project_name with the name of your project
+  project_name:
+    main: src/project_name.cr

crystal: 0.35.1
```

## Testing

To test a change to this buildpack, write a unit test in `tests/run` that asserts your change and
run `make test` to ensure the change works as intended and does not break backwards compatibility.

## More info

- [Luckyframework.org](https://luckyframework.org) has a guide on [Deploying to Heroku](https://luckyframework.org/guides/deploying/heroku)
- Lucky is written in [crystal](https://crystal-lang.org/)
