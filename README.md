# cook – chef-solo with less sit ups

cook wraps the `chef-solo` with saner defaults so you don't have to deal with creating a bunch of configuration files first.

## INSTALL

    curl -sL https://github.com/josh/cook/raw/master/bin/cook > ~/bin/cook
    chmod +x ~/bin/cook
    curl -sL https://github.com/josh/cook/raw/master/example.json > ~/.cook

You don't need to install chef; cook does it automatically on first run.

## CONFIGURATION

This tells Chef which cookbooks and recipes you want applied:

~~~ js
// cat ~/.cook
{
  "cookbooks": ["http://github.com/josh/osx-cookbooks/tarball/master"],

  "run_list": [
    "git",
    "homebrew"
  ]
}
~~~

This is a standard Chef JSON attributes file with some extra magic: you list
your cookbook locations here instead of as command line options. Cookbook
locations can be filesystem paths or tarball URLs.

Checkout [josh/osx-cookbooks][] to get you started.

## USAGE

    sudo cook

Thats it.


  [josh/osx-cookbooks]: https://github.com/josh/osx-cookbooks
