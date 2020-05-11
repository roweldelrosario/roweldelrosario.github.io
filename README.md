## About

Just another [Jekyll](https://jekyllrb.com) theme for personal blog.

In addition to the base Hyde theme, it includes the following feature without using a plugin.

- Post grouped by tag
- Share buttons
- Twitter/Open Graph(Facebook) meta tags

The only plugin being used is `jekyll-paginate` for pagination.

### Notes

If you are using a static site generator that allows you to specify the build commands (like Netlify) then use the following to automatically generate tag pages.

``` bash
python _tag_generator.py && jekyll build
```

Otherwise, you MUST locally run `python _tag_generator.py` and commit/push the generated tag pages (files under the /tag directory).

## Project Inspiration

This site incorporates components from the projects listed below.

- Jekyll theme forked from [Hyde](https://github.com/poole/hyde)
- Tagging mechanism is from [qian256.github.io](https://github.com/qian256/qian256.github.io)
- Some other cool stuff from [Jekyll Codex](https://github.com/jhvanderschee/jekyllcodex)

## License

Released under [MIT license](LICENSE.md).
