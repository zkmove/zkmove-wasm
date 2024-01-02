`https://developer.mozilla.org/en-US/docs/WebAssembly/Rust_to_wasm`
### prepare
##### wasm-pack
To build the package, we need an additional tool, wasm-pack. This helps compile the code to WebAssembly, as well as produce the right packaging for use in the browser.
```cargo install wasm-pack```
### Process
1. compile rust code to WebAssembly. 
    ```wasm-pack build --target web```.
2. Serve the root directory of the project with a local web server, 
    ```python3 -m http.server```.
3. Load index.html from the web browser.
    ```http://localhost:8000```

