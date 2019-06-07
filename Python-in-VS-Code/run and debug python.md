from [python-tutorial](https://code.visualstudio.com/docs/python/python-tutorial)

# Run a and debug a program:

`$ python hello.py`
![run-python-file-in-terminal](https://code.visualstudio.com/assets/docs/python/tutorial/run-python-file-in-terminal.png)


## Configure and run the debugger
open up debuggger, add config.
```JSON
{
    "version": "0.2.0",
    "configurations": [
        {
            "name": "Python: Current File",
            "type": "python",
            "request": "launch",
            "program": "${file}",
            "console": "integratedTerminal",
            "stopOnEntry": true
        }
    ]
}

```
![py debugg](https://code.visualstudio.com/assets/docs/python/tutorial/debug-configurations.png)
Tip: If you need to specify the exact folder containing the interpreter to use for debugging, include an entry for pythonPath in the configuration, such as "pythonPath": "${workspaceFolder}" or "pythonPath": "${workspaceFolder}/.venv".

## stopOnEntry
### debug step 1
A debug toolbar left to right: continue (F5), step over (F10), step into (F11), step out (⇧F11), restart (⇧⌘F5), and stop (⇧F5).
![debug-step-01](https://code.visualstudio.com/assets/docs/python/tutorial/debug-step-01.png)

### debug step 2
![debug-step-02](https://code.visualstudio.com/assets/docs/python/tutorial/debug-step-02.png)
For full details, see [Debugging configurations](https://code.visualstudio.com/docs/python/debugging), which includes notes on how to use a specific Python interpreter for debugging.

Tip: Use Logpoints instead of print statements: Developers often litter source code with print statements to quickly inspect variables without necessarily stepping through each line of code in a debugger. In VS Code, you can instead use Logpoints. A Logpoint is like a breakpoint except that it logs a message to the console and doesn't stop the program. For more information, see [Logpoints](https://code.visualstudio.com/docs/editor/debugging#_logpoints) in the main VS Code debugging article.