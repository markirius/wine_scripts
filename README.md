## Scripts description

These scripts are intended to simplify packing, launching and distributing
Windows games and programs using Wine. In other words, these scripts are for 
creating portable Wine applications. But they also can be used for other purposes. 
These scripts will work on all Linux distributions with GNU standard utilities and bash 
shell installed.

## start.sh script description

All script settings (variables) are in the settings_start file or in the
settings_SCRIPTNAME file.

To change prefix architecture to 32-bit change PREFIX_ARCH variable
to win32 in settings_SCRIPTNAME file.

Script can be launched with --debug parameter to enable more output. This
helps in finding problems when application not working.

Script automatically uses system Wine if there is no wine directory
near the script or if GLIBC version in the system is older than 2.23.

Script automatically creates new prefix during first run and it uses
files from game_info directory. Script is not inteded to work with
already created prefixes.

Script creates documents directory to store games settings and saves.
And so removing prefix will not affect game saves/settings most of the time.

Script automatically recreates prefix if username or Wine versions changes.

Settings file name and game_info.txt name depends on script name.
For example, if script is named start-addon.sh then it will use
settings_start-addon file and game_info-start-addon.txt file if it exists.
If there is not game_info-scriptname.txt file then script will use standard
game_info.txt file. So you can make copies of start.sh script with different
name and they will use different settings and can launch different exe
files.

## tools.sh script description

Tools.sh script can be launched with these arguments:

	--cfg - run winecfg
	--reg - run regedit
	--tricks - if used without additional arguments then run winetricks GUI.
		It can also be used with additional arguments, like:
		./tools.sh --tricks d3dx9 corefonts.
	--kill - kill all running processes of specific Wine prefix
	--fm - run Wine filemanager
	--clean - remove almost all unneeded files from directory
	--icons - create application icons on Desktop and in applications menu
	-- remove-icons - remove created icons
	--help - show available arguments


---

Description of directories and files of game_info directory are in the
game_info/README.md file.
