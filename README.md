How to
------

### Prepare
##### wasm-pack
To build the package, we need an additional tool, wasm-pack. This helps compile the code to WebAssembly, as well as produce the right packaging for use in the browser.
```cargo install wasm-pack```
### Compile
compile rust code to WebAssembly.

    ```wasm-pack build --target web```.
### Proof Generate by Web
1. Serve the root directory of the project with a local web server, 

    ```python3 -m http.server```.
2. Load index.html from the web browser.

    ```http://localhost:8000```
3. generate proof step by step.
    setup circuit -> rock test -> generate key -> generate proof.

### Verify by CLI
run wasm-pack test with headless and the log output is like below:

```
❯ wasm-pack test --headless --firefox --release
running 1 test

test zkmove_wasm::wasm::tests::test_js ... ok

test result: ok. 1 passed; 0 failed; 0 ignored
console.log div contained:
    setup circuit start
    vm default creating
    vm default done
    setup circuit successfully!
    Test circuit start
    Test circuit successfully!
    generate vk start
    generate vk successfully
    generate pk start
    generate pk successfully
    proof generate start
    proof generate successfully
```

### Notice
there is a relative reference to zkmove-vm. so please the source code of zkmove-vm and zkmove-wasm MUST be placed at same folder.