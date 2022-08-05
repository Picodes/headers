# headers

Generate perfect code headers every time.

## Build

You need Rust and Cargo installed on your machine. See the installation guide
[here](https://doc.rust-lang.org/cargo/getting-started/installation.html).

Then clone the repo and install the CLI globally like this:

```sh
cargo install --path .
```

## Usage

```sh
λ ./headers "testing 123"
```

```sh
// ================================ TESTING 123 ================================
```

It will also copy the header to your clipboard automatically.

### With VSCode

If not done locally in the repo, in your [`tasks.json`](https://stackoverflow.com/questions/41046494/making-global-tasks-in-vs-code) add the command as task:

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

Add a keybind for the task in [`keybindings.json`](https://code.visualstudio.com/docs/getstarted/keybindings):

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
