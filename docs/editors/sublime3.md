# Sublime Text 3

## Setup

Using the _Command Palette_, select `Package Control: Install Package`
and install the `LSP` package.

After that is done, go to:

    Preferences -> Package Settings -> LSP -> Settings

Add an Erlang client by adding the following configuration to the
`LSP.sublime-settings - User` file:

    {
      "clients":
        {
          "erlang-ls":
            {
              "command"   : [ "/path/to/my/erlang_ls", "--transport", "stdio" ],
              "enabled"   : true,
              "languageId": "erlang",
              "scopes"    : [ "source.erlang" ],
              "syntaxes"  : ["Packages/Erlang/Erlang.sublime-syntax"]
            }
        }
    }

That's it. Open a new Erlang project and enjoy Erlang LS.

## Troubleshooting

In case of issues, you can enable extra logging for the `LSP` package
by adding the following configuration to your `LSP.sublime-settings -
User` file:

    {
      // Show verbose debug messages in the sublime console.
      "log_debug": true,

      // Show messages from language servers in the Language Servers output
      // panel.
     "log_server": true,

      // Show language server stderr output in the Language Servers output
      // panel.
      "log_stderr": true,

      // Show full JSON-RPC requests/responses/notifications in the Language
      // Servers output panel.
      "log_payloads": true
    }

The Sublime console can be toggled using the `` Ctrl-` `` shortcut. The
output panel can be toggled from the command palette with the command
`LSP: Toggle Panel: Language Servers`.