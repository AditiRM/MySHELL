# Custom C Shell
## Aditi Medhane | 111803177
---
## Requirements

- GCC compiler
- Linux OS (preferably Ubuntu)

## Installation &  Running Shell

```bash
# Use Makefile to Build the program
> make

# Run the Shell
> ./shell
```
## Files & Functions
###### Files containing functions required for proper functioning of the shell. 

- `shell.c`

  - Run Shell Loop
  - Extract Arguments from command
  - Bind functions from different files together

- `basic_setup.c`

  - For setting up User, Base Directory, Prompt
  - Sets signal handler, pgid

- `built_ins.c`

  - For implementing built-in commands
  - cd   : For changing current working directory.
  - echo : Prints user input after removing excess spaces/tabs
  - pwd  : To display the present working directory.
  - fg   : Brings a process to foreground and changes it state to Running.
  - bg :   Changes status of background process from Stopped to Running.
- `io_redirection.c`

  - For input output redirection 
  - Open input_file /output_file

- `parse.c`
    - For parsing command line and commands 

- `pinfo.c`
    - For implementing pinfo command

- `run_command.c`
    - For running a command using fork and exec

### Other Implementations

###### Commands/functions which don't have a separate file.

- Signals

  - `Ctrl+Z` Sends current foreground process to background.
  - `Ctrl+C` Stops current foreground process.

- Background Processes Manipulations

  - Implementation of background processes list, removing/adding them from/to the list is done in `shell.c` & `built_ins.c`.

- Exit Codes

  - Depending on whether last command was successful or not, or will appear before the prompt.
  - A background process will ONLY fail if the forking fails. All other situations will result in command success.

- Exiting from the Shell
  - `quit` command.    

