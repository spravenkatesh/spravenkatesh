# ModuleNotFound error while importing any custom modules in VSCode  

When running from interated VSCode terminal , if a workspace path is not added to `PYTHONPATH`, module paths could not be resolved while imoorting them, hence VSCode must be configured to append the workspace path from where module must be imported to `PYTHONPATH`.

example: importing resources from a module a

```python
ModuleNotFoundError: No module named 'resources'
```

To add workspace path to `PYTHONPATH`

1. open Command Pallette : View>Commmand Pallete (ctrl+shift+p)
2. type: `Preferences: Open User Settings(JSON)`
3. A JSON file will be opened in VSCode
4. insert below line:

    ```JSON
        "terminal.integrated.env.linux": {
            "PYTHONPATH": "${workspaceFolder}"
        },
    ```

    **do not forget to add `,` after a block(curly braces) `},`**  
    **for windows use `terminal.integraded.env.windows`, for mac use `terminal.integrated.env.osx`**
5. save the file
6. reload the workscpace using command `Developer: Reload Window`
7. run the `code` again , module should be successfully imported and `ModuleNotDoundError` must not be visible anymore.
