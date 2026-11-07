# Py.Bench

A tiny Python playground that runs **entirely in your browser**. Write code, hit **Run**, see the output. No installs, no accounts, no backend.

Built on [Pyodide](https://pyodide.org) (real CPython compiled to WebAssembly) and [CodeMirror](https://codemirror.net).

## What it's for

- Trying out a snippet without opening a terminal or setting up an environment
- Teaching and learning Python, since there is nothing to install
- Embedding a runnable demo next to a blog post or tutorial
- Quick experiments with `numpy`, `pandas`, `scikit-learn` and friends

## What it can do

- **Run real Python** in the browser. Your code never leaves your machine.
- **Auto-install packages.** Just `import numpy` and it's fetched on first use, with a fallback to PyPI (pure-Python packages) via `micropip`.
- **Interactive `input()`.** Programs can ask for input and wait for your answer.
- **Code editor** with syntax highlighting, line numbers, bracket matching, auto-close brackets and 4-space indentation.
- **Output panel** showing stdout, errors, return values and run time.
- **Copy and clear** buttons for both the code and the output.
- **Resizable split view** that stacks on mobile.
- **Keyboard shortcut:** `Cmd/Ctrl + Enter` to run.

## Usage

It's a single static file. No build step and no server code.

1. Download [`index.html`](index.html).
2. Open it in a browser, or host it anywhere that serves static files (GitHub Pages, Netlify, any web server).

The first load downloads the Python runtime (a few MB); after that it's cached by the browser.

To change the starting code, edit `DEFAULT_CODE` near the top of the `<script>` block.

## Limitations

- Needs an internet connection to load Pyodide and CodeMirror from CDNs.
- Only packages that Pyodide ships, or pure-Python packages from PyPI, will work. Packages with native extensions that Pyodide doesn't include can't be installed.
- Runs on the browser's main thread, so very long or heavy loops will freeze the page until they finish.
- Nothing is saved. Reloading resets the editor.

## Contributing

Open source and free for everyone. Issues and pull requests are welcome.

## License

MIT. Free to use, copy, modify and share, including commercially.
