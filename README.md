Awesome Web Server
==================

**Awesome Web Server** is a repository dedicated to a functional and secure web server
configuration with the following capabilities:

+ FTP
+ SSH
+ Postfix
+ WWW
  + Nginx
  + Apache
  + PHP5
  + Puma
    + Rails
  + Nodejs
+ MySQL

These configurations are tested with Ubuntu 12.04 and 12.10, the x64 variety. It probably
won't work with other versions. If anyone is interested in maintaining a branch for another
implementation, we'd love to have you as a contributor.

Directory Structure
-------------------

`./bin` Directly executable scripts.
`./bin/install` Scripts which perform install tasks.
`./bin/configure` Scripts which perform configuration tasks.
`./doc` Documentation for tasks, written in Markdown.
`./etc` Example configuration files. Should match local `/etc` path and filename.
`./lib` Libraries used by other scripts.
`./lib/tests` System test scripts. Called by `./bin/test.rb`.

Tests
-----

Ruby, Rubygems, and any other dependencies must be installed in order to run tests.

Once Ruby and Rubygems are installed, run bundler from the
home directory of the repository to make sure Ruby dependencies are
met.

```bash
bundle
```

To perform tests run the test script with the following command:

```bash
./bin/test.rb
```

Tests are a great way to work through a checklist making sure all the basics are
in place for a healthy web server.

Tests are a work in progress ... many have yet to be written. Would you contribute?

### How To Write A Test

A test can be written in any language. The `test.rb` script will run each script in the
`/lib/tests` directory, passing the local configuration as a string of JSON. Take a look
at `config.sample.yml` to see what configuration variables are availale and will be passed
to a test when it is called.

All tests must return two result attributes: result and message.

+ Result can be pass, fail, or warn.
+ Message expectes a string of text which will be displayed if the result is not pass.
+ Return results by printing JSON output.

```json
{
  "result": "pass",
  "message": "Hello world"
}
```

If the new test requires options, don't forget to update `config.sample.yml`.
Update dependecies via Gemfile,
package.json, or wherever it is neccessary for your additions.

Version History
---------------

+ 0.1.0 2013-12-14
  + Initial development version

License and Warranty
--------------------

This repository is licensed under GPL3. Use at your own risk.