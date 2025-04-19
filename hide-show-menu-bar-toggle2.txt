-- Open Shortcuts App > Open Shortcut > Info > Pin in Menu Bar

tell application "System Settings"
	reveal pane id "com.apple.ControlCenter-Settings.extension"
end tell

delay 0.4

tell application "System Events"
	tell window 1 of application process "System Settings"
		tell pop up button "Automatically hide and show the menu bar" of group 9 of scroll area 1 of group 1 of group 2 of splitter group 1 of group 1
			click
			if value = "Never" then
				click menu item "Always" of menu 1
			else
				click menu item "Never" of menu 1
			end if
			
		end tell
	end tell
end tell

delay 0.4

tell application "System Settings" to quit