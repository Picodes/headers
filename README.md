# headers

Generate perfect code headers every time.

## Build

You need Rust and Cargo installed on your machine. See the installation guide
[here](https://doc.rust-lang.org/cargo/getting-started/installation.html).

Then clone the repo and install the CLI globally like this:

```sh
cargo install --path .
```

### Setup with VSCode

If not done locally in the repo (done already in `savings-rate`), in your [`tasks.json`](https://stackoverflow.com/questions/41046494/making-global-tasks-in-vs-code) add the command as task:

```json
{
  "version": "2.0.0",
  "tasks": [
    {
      "label": "Generate Header",
      "type": "shell",
      "command": "headers ${input:header}",
      "presentation": {
        "reveal": "never"
      }
    }
  ],
  "inputs": [
    {
      "id": "header",
      "description": "Header",
      "type": "promptString"
    }
  ]
}
```

Add a keybind for the task in [`keybindings.json`](https://code.visualstudio.com/docs/getstarted/keybindings) (can be found by entering vsCode command control via cmd+shift+p and the searching for keyboard shortcuts):

```json
[
  {
    "key": "cmd+h",
    "command": "workbench.action.tasks.runTask",
    "args": "Generate Header"
  }
]
```

This will copy the generated header to your clipboard.
