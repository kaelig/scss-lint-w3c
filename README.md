# SCSS-Lint W3C-style configuration file

This configuration file overrides the [default scss-lint config][defaultconfig]
to enforce a coding style very similar to the way authors of the CSS
specification write code in the W3C standards and drafts.

Authors of the specification write in various coding styles
but some trends emerge out of the numerous code examples available.

I tried to formalize these trends and document them in this repository.
Although the resulting configuration file can be used as a good base for your
project, you should aim to override it with stricter linting rules to improve
code quality.

Each linter rule is documented, mentionning when the W3C style hinders
maintanability, grep-ability or readability, so you can make educated changes
into your own configuration file.

Thanks to the authors of the spec and [@sds](https://github.com/sds) for scss-lint.  
http://www.w3.org/TR/CSS/  
https://github.com/causes/scss-lint

Feel free to contribute if you see any errors or improvements.

## Installation

First, you need scss-lint:

```
gem install scss-lint
```

To run scss-lint on your project, follow the instructions on:
https://github.com/causes/scss-lint

I wrote an article detailing [how we improved Sass code quality using
scss-lint on theguardian.com][guardian-scss-lint]. It details installation steps
and how to automate linting with a Grunt task.

### With bower

```
bower install scss-lint-w3c --save-dev
```

Add this line to your `.scss-lint.yml` configuration file:

```yaml
inherit_from: 'bower_components/scss-lint-w3c/scss-lint-w3c.yml'
```

### Manually

Download [scss-lint-w3c.yml](scss-lint-w3c.yml) into your project or clone this repository.

Add this line to your `.scss-lint.yml` configuration file:

```yaml
inherit_from: 'path/to/scss-lint-w3c.yml'
```

Your `.scss-lint.yml` configuration file should now look something like this:

```yaml
# .scss-lint.yml

inherit_from: 'bower_components/scss-lint-w3c/scss-lint-w3c.yml'

# scss_files: 'app/assets/stylesheets/**/*.css.scss'

# exclude: 'app/assets/stylesheets/plugins/**'

# Your own linter configuration:
linters:
  BorderZero:
    enabled: false

  Indentation:
    exclude:
      - 'path/to/file.scss'
      - 'path/to/directory/**'
    severity: warning
    width: 2
```

[defaultconfig]: https://github.com/causes/scss-lint/blob/master/config/default.yml]
[guardian-scss-lint]: http://www.theguardian.com/info/developer-blog/2014/may/13/improving-sass-code-quality-on-theguardiancom
