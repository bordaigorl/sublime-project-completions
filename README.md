# Project Completions plugin

This plugin lets you add project-specific completion snippets to your `.sublime-project` files.

Install the plugin via [Package Control][] and you can add project-specific completions via the `completions` key in your `.sublime-project` file.

Completions can be specified in two formats. 

### Simple list

Just a list of `[trigger, completion]` items:

```
{
    "folders": ...
    "completions": [
        [trigger, completion],
        ...
        [trigger, completion]
    ]
}
```

where `trigger` is the prefix that triggers the completion (and can contain a caption separated by `\t`) and `completion` is a snippet.
For more information about the syntax of completions see the [Unofficial Documentation][docs].
Using this syntax, the completions will always be available in the project.

### By Scope

A dictionary with scopes as keys and lists of completions as values:

```
{
    "folders": ...
    "completions": {
        selector: [
            [trigger, completion],
            ...
            [trigger, completion]
        ],
        ...
        selector: [
            [trigger, completion],
            ...
            [trigger, completion]
        ]
}
```

In this case only the completions associated with selectors matching the current scope will be suggested.
For more info about scope selectors see the [Unofficial Documentation][selectors].

### Thanks

Thanks to [Amina](http://superuser.com/users/185370/amina) for [inspiring](http://superuser.com/q/965658/496621) this plugin.

[Package Control]: https://sublime.wbond.net/
[docs]: https://sublime-text-unofficial-documentation.readthedocs.org/en/latest/reference/api.html#sublime_plugin.EventListener.on_query_completions
[selectors]: https://sublime-text-unofficial-documentation.readthedocs.org/en/latest/extensibility/syntaxdefs.html#scopes-and-scope-selectors
