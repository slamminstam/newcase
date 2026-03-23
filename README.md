# newcase.sh
A lightweight Bash utility for creating standardized case directories and notes files based on date and case number.

Installing this in a file specified by your .bashrc file will allow you to run this without specifying the path.

## Overview
`newcase.sh` was designed to reduce friction during technical investigation workflows by automating the repetitive setup of case folders and notes files.
Instead of manually creating directories, naming files, and organizing artifacts, the script generates a consistent structure instantly—allowing focus to stay on troubleshooting and analysis.

## What it does
- Ensures a base `~/Documents/cases` directory exists
- Organizes cases by date using the format:
  - **Year-Month-MonthName** (e.g., `2026-03-Mar`)
- Creates a case-specific folder using the provided case number
- Generates a `notes.txt` file inside the case directory (if it doesn’t already exist)
- Offers to open the notes file after creation (or if it already exists)

## Workflow
When executed, the script:
1. Checks for a `cases` directory in `~/Documents` and creates it if needed  
2. Determines the current date and formats it as `YYYY-MM-Mon`  
3. Creates a date-based folder if it does not already exist  
4. Creates a case-number folder within that date directory  
5. Creates `notes.txt` if missing. Will not overwrite existing notes.txt file.  
6. Prompts to open the notes file:
   - Uses the system default editor  
   - Or a specified editor if a flag is provided  

### Example
```bash
./newcase.sh 1234567
```
creates
```
/cases/2026-03-Mar/1234567/
├── notes.txt
```
#### Usage
```bash
newcase  [OPTION1] ... [OPTION2]...
```
###### Options
* `-h` Help — Display usage information
* `-c` Case — Specify case number
* `-e` Editor — Set preferred editor
* `-f` Notes File — Specify notes filename
* `-o` Open Notes — Automatically open notes file
* `-v` Version — Display version information

## Why it exists
In high-volume support environments, small inefficiencies compound quickly.
This tool removes setup overhead and enforces consistent structure, making it easier to:
* Locate past work
* Maintain organized case artifacts
* Transition between active investigations

## Notes
* Designed for UNIX-based systems
* Assumes a predefined base directory (can be modified in script)
* Built for speed, simplicity, and repeatable workflows

### Some further updates I have considered:
- Create “cleanup” flag that checks the current date and removes anything older than 1 month (typically, cases aren’t open for longer that this).
  - Could make this flag configurable by time, defaulting to 1 month.
- Package to include a “config” file for the script, allowing users to specify preferences like preferred editor, instead of having to use a flag every time.

## License
MIT
