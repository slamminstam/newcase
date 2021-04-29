# newcase
Create a New Case Directory and notes file based on current month, year, and Salesforce case number. 

Installing this in a file specified by your .bashrc file will allow you to run this without specifying the path.

This script does the following:
Check ~/Documents for a folder called “cases”. If it does not exist, create it.
Check the current date by YYYY-MonthDate-MonthName (i.e. 2021-04-Apr)
Check ~/Documents/cases for a folder named by the current date in that format, and if it doesn’t exist then create it.
Check ~/Documents/cases/2021-04-Apr/ for a directory matching the case number entered. If it doesn’t exist, create it.
Check ~/Documents/cases/2021-04-Apr/case#/ for a file called “notes.txt”. If it doesn’t exist, create it, then offer to open it. If it does, offer to open it.
If asked to open notes.txt, open in default editor unless a flag is set to pick a specific one.

The following options are available for the script:

		Create a New Case Directory and notes file based on current month, year, and case number.
		Created by: Timothy Stam
		
		Usage: newcase [OPTION1] ... [OPTION2]...

		OPTIONS:
			-h Help		Display this help
			-c Case		Specify your Salesforce case number. Otherwise, you will be asked.
			-e Editor	File editor to use when opening notes. Otherwise, use default editor.
			-f Notes File	Name of the output file for your notes. Defaults to notes.txt.
			-o Open Notes	Automatically open notes file in selected/default editor.
			-V Version	Display version number of this script.
	
		VERSION: 1.4
		Last Updated: 04/29/2021
	
		Suggestions? Bugs? Email tim@slamminstam.com

Some further updates I have considered:
Put in a “cleanup” option that checks the current date and removes anything older than 1 month (typically, cases aren’t open for longer that this).
Put together a package that includes a “config” file for the script, where users could specify preferences like preferred editor instead of having to use a flag every time.
