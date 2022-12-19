
## Task List
<details>
  <summary>Unsorted Goals</summary>
  
- [ ] `notify-send` command to vnc user when using VNC in addition to console out
- [ ] Different screen resolutions:
  - https://superuser.com/questions/184338/how-to-change-screen-resolution-of-vnc-server-without-restarting-it
- [ ] Global setting to set ssh open directory to either the home folder or the itacs root directory
- [ ] Tool to change configuration values across multiple testbeds
- [ ] Check reservation before running a test to alert if not on reservation
- [ ] RDP Support
  - https://stackoverflow.com/questions/14481882/login-to-remote-using-mstsc-admin-with-password
  
</details>

<details>
  <summary>v0.2 Task List - Regression Update</summary>
  
- [x] VNC button will do the same as open-->New x11vnc session IF vnc is not enabled inside of testbed
- [x] Do size check before installing DB

## Sprint 1:
- [x] Centralize Report Location
  - [x] ICL1 
    - [x] Manual
    - [x] Server
  - [ ] ICL2
    - [ ] Manual
    - [ ] Server
- [ ] Auto-Start ICl2 Autonomous Scripts
- [x] Localize Option for Reports
  - [x] REDUNDANT because if you can see it to display it is local
- [ ] Increase Robust Automation for ICL1
- [ ] 

## GUI Dashboard Fixes
- [ ] Make New WinSCP Connection via button
- [ ] Select new VNC window when new display is made
- [ ] fix putty buttons
- [ ] closing vnc window also closes the tab
- [ ] Testbed tab to change settings and update the selected testbed


## Autonomous Execution Server
- [x] Allocate Tests to Testbeds
- [x] See status of tests
- [ ] Abort tests
- [x] See Queue of Tests
- [x] Version Control
  - [x] Save data to local machine
    - [ ] You Pick The Save Location
  - [x] Some sort of version regression control
  - [x] Save taps plot data(?)
  - [x] Save PDF
  - [x] Save Command Reports
  - [x] Save Taps Plots PDF
- [x] State Machine Command Control
  - [x] Reset To Default State
  - [x] Restart iTACS
  - [x] Sync Database
  - [x] GSP/MP
  - [x] Launch iTACS
  - [x] Connect to Spacecraft and set active
  - [x] Launch Test
  - [x] Clean Up
  - [x] Fault Conditions
    - [x] Abort

## Reservations
- [x] Actually fix time sync for reservations
- [x] Reservation Control
  - [x] Create New Reservation
    - Only if your username is included in the description

## Log Manipulation Features
- [x] Copy timestamp of plot and make a new plot of PIDs using that (See other set of TLM over the same time frame)
  - [x] Plot modifier
- [x] button to view report (parses XML file from /taps/data/reports)
  - [x] craft what the script file name without timestamp
  - [x] get xml file dump of all the potential scripts
  - [x] Parse through the <report> </report> until you find the error
  - [x] Return that <report> and parse the message/input lines
  - [x] present that to the user
  - [x] error control if it can't find the error in the reports
- [ ] GRMON release button (kills all ssh consoles server-side to release GRMON)
- [x] Centralize Report Location
- [x] Unify log locations when generating reports

## Regression Testing Features
- [x] Log completed tests
- [x] Use test times in error logs to track # errors per run of test
- [x] Use test time in error logs to sort by test groups / tests
- [x] Export tests (taps, command reports, taps reports) to local file folder
  - [x] Option to add testbed configs used to run tests
- [ ] Export Plots and Report as PDF to select location

</details>

<details>
  <summary>v0.19 Task List - Creature Comfort Update</summary>

## Final Checklist Before Release
- [x] Excel Repackager
- [x] fix stopping other scripts when running new test on different testbed
- [x] fix ICl1 X11 automation
  - [x] Testbed specific automation.status
- [x] choose to ignore or to update when DB mismatch
- [x] Run ICL2 File Check if Line #'s are correct (or incrementing)
- [x] Run ICL1 File In Automated Mode to Check that Error Handling is working correctly
- [x] Source Errors and Scripts and Try to get that to break
  - [x] Fix crashing when opening command reports / pdfs
- [x] Test that prompts are accurate and none are missing
- [x] Repackage excel databases
  - [x] Add button to repackage from main page

## New Features
- [x] All the open --> tabs will auto-launch into x11vnc if session is open
- [x] fix error when deleting local x11vnc connections
- [x] remove slightly worse awe event viewer
- [x] Allow table editing to copy errors
- [x] Recording errors only calculates SC time once for each source
- [x] snvops update selection
- [x] Test default use-cases of ICL1 scripted automation to make sure it is rock solid
- [x] Sort errors
  - [x] source script sorting by errors
  - [x] source script sorting by script
  - [x] source script sorting by keyword
- [x] Notify User when finishing sourcing errors
- [x] Use terminal command to kill hypervisor when main window exits (prevent hanging or background processes sticking)


## Running Tests
- [x] Error tracking always on
  - [x] ICL1
  - [x] ICL2
- [x] copy back the framework file once the test is completed to 
- [x] Log Just Errors in .err file for that specific test
- [x] STAAR Reports Should Just be 'TAPS Reports'
- [x] Ability to edit scripts (only if they have errors)
  - Alert user if it can't find the file
- [x] Stamp Spacecraft Time and System Time in reports
  - [x] import test data
  - [x] export test data
- [x] Export
  - [x] Tests
    - [x] Exporting Tests will also export the associated testbeds
  - [x] Plots
  - [x] Testbeds
- [x] TLM check for downlink rate for ICL2
  - [x] Downlink rate not mapped to TLM so we can't do a check
- [x] Make sure to kill all the icl1 backend threads before starting new icl1 thread
- [x] Put in autokill function to terminate iff:
  - [x] some file in the automation/ directory tells them to do so
  - [x] automatically send the script termination for everything before running any script
  - [x] Alert user that this will kill any actively running ICL1 tests on that SWT/HWT

## User Experience
- [x] Display Vehicle name in main display
- [x] 'Email Scripts' Change to 'Email Scripts To Self'
- [x] Fix weird SED error when launching ICL1 script
- [x] Fix strange issue with starting live plots
- [x] When launching automated scripts on the 'press ok to launch ' include the hostname
- [x] Move nautlius items to new thread so they don't crash when opening files
  - [x] remove nautilus button (don't ever use it)
- [x] Error tracking defaults to currently active testbed for sourcing
- [x] Running tests automatically defaults to currently selected testbed

</details>

<details>
  <summary>v0.18 - Task List</summary>

## Test Before Push
- [x] Update Default Testbeds with HWT/SWT Information
- [x] Run ICl1 and ICL2 Test non-Automated
- [x] Run ICL1 and ICL2 Test Automated
- Test Every new feature
  - [x] Logging
  - [x] Serial Ports in X11vnc
  - [x] Itacs DB Change
  - [x] Launching w/o errors into x11vnc from automation
  - [x] Update Defaults to include HWT/SWT selection
  - [x] Testbed selection persists through restarts
  - [x] Confirm X11vnc Session Manipulation


## New Features
- [x] Prevent Automation check for icl2 on SWT
- [x] prevent SCON selection for SWT
- [x] Console logging for every session
- [x] Submit bug report (with log file as an attachment)
- [x] Add script error proc in icl2 automated
- [x] Add drop down when running test
  - [x] Do Not Run SCON
  - [x] Run SCON at the beginning
  - [x] Run SCON before every script
  - [x] Integrate for ICL1/ICL2
- [x] 'LATEST' keyword integrated when launching serial ports
- [x] Add Reservation Link under Edit--> Reservations
- [x] About popup button for forwarding to explain what that setting does

## Polishing / Frontend
- [x] Launch GSP/MP ports inside x11vnc
- [x] Killing server side xvnc will wipe the saved config files
- [x] All powerful commands have an additional prompt to confirm before executing (killing sessions, etc)
- [x] 'Logging' setting to turn on/off creation of log files for bug reports
- [x] Go through GUIs and to make everything more understandable (explain / expand upon more so easier to understand)
- [x] Add extra prompt to confirm running test on testbed
- [x] Confirm VNC session RFB and VNCserver are set up correctly
- [x] Fix Live PIDS not working
- [x] Remove ask to kill VNC sessions when exiting
- [x] Triple Check ICl1 Reports
- [X] Prompt When Launching MP/GSP Serial ports
- [x] Testbed configuration closes on save
- [x] Tell user where it put the file when it generated the test
- [x] Prompt the user AFTER starting automated test.
  - [x] If ICL2, note that the user must start it
  - [x] If ICL1, alert the user that the script has auto-started
- Fix ghost entries in x11vnc session manager ## HOLD this until very end to see if it fixed itself
- [x] Remove adding timestamp to automated file.. it fills a lot of space FAST
- [x] Kill the console no matter what if we exit out of the main window
- [x] Prompt to open a new vnc window if that is enabled?
- [x] Remove launch SWT option if on a HWT
  - [x] HWT/SWT combo box in testbed configuration, default to SWT because that has more features
- [x] Initialization testbed boot checks to auto-add any missing pieces in the testbeds
- [x] Auto-refresh data when saving any kind of file
- [x] Testbed persists on restarts (keeps last selected)
- [x] Can't email unless email address is legitimate

</details>

<details>
  <summary>v0.17 Task List</summary>

- [x] Read global vnc ports in from files on startup (and fix weird newlines)
- [x] File -> Import all the .ini files
  - [x] Plots
  - [x] Tests
  - [x] Testbeds
- [x] Restart iTACS still not working (FIX IT)
- [x] Kill all vncservers running on testbed (server-side kill regardless of stored sessions)
- [X] 'Latest' iTACS DB keyword to always use the latest iTACS DB Version

</details>

<details>
  <summary>v0.16 Task List</summary>

## Automation
- [x] ICL1 Automation
  - [x] Get Log Files / Serial out Of ScriptViewer into Python

</details>

<details>
  <summary>v0.15 Task List</summary>

## General
- [x] Sort Testbeds in Combo Box by name and not date added
- [x] Close all stored VNC sessions
- [x] Change command report button in test to be '/taps/data/reports/'
- [x] X11VNC Session Manager
  - [x] Option to join existing x11vnc session (asks for port and then off to the races)
  - [x] Lists tracked sessions to rejoin or kill
- [x] VNC Sessions Persist Across Hypervisor sessions

## Collaboration
- [x] More of a multiscripter feature but auto-generate a taps plot from associated TLM from a file (uses tlmdDeriver)
  - [x] Add 'Dynamic Plots' as a check for running a test so each plot is different and relevant
  - [x] This feature will ADD ON TO EXISTING PIDS and will NOT OVERWRITE ANY PIDS LISTED // EDIT THIS IS CRAP just make a dynamic one
  - [x] Must be ran before timestamps are included
  - [x] Add 'Only Dynamics' Button to only generate dynamic plots
- [x] 'Set Packet Cluster to 4, CFV Packet Enable' button
- [x] 8K/144k Downlink rate combo box
- [x] Add in FDIR Default PIDS as a check to add in a default list
- [x] 'Monitor Remotely' button to remotely monitor a currently running test in ICL1 (must be prompted with port number)
## Remote Script Management / Execution
- [x] Create Command Report PDF's in the `multiScripter/Reports/` directory
  - As much as it sucks to do, we need to use the `multiscripter.sh` to do this and it will be super easy with the framework file
- [x] 'Command Report' button which opens nautilus on the `multiScripter/Reports/` directory
- [x] Renamer.sh portion only renames the os.getlogin() and test name, keep the time code
- [x] 'Live Plots' button to auto-generate a plot starting from now until 1 hour into the future of the currently selected plot template
- [x] 'TAPS' button to bring up the existing TAPS plot for that test (any test ran will append to this file)
- [x] 'Simple' Check to open a single script with no fancy additions
  - Only if a single file is in the test
  - UPDATE: Actually just make it so you can check/mark the scripts you want to run in the test-set. Can select only 1 to just run that
- [x] Generate Test Via Run Test Button
- [x] have a 'Test Framework' that looks like<br>
beginTime=X<br>
endTime=X<br>
Name=X<br>
template=X<br>etc...
- [x] And source that from multiscripter to build out a taps plot or anything else for the future
- [x] FIX Selecting cancell on x11 prompt for scripted command gui and icl2 
- [x] ICL1 and ICL2 Compatability
  - [x] Fix ICL2 GUI not launching
- [x] Move ScriptViewer to new thread so it will continue even if Hypervisor crashes / exits
- [x] In special environment edit do a label with the find and replace in ICL1/ICL2 so you can see the expected output
- [x] Automated check for ICL2 to run without user interaction (Once started)
- [x] Change add taps plot file dialog to the windows default one used to send files over email
- [x] Option to Generate and Run or just Generate
- [x] X11vnc forward command to x display? Bring up script in that session?
- [x] Detect and view taps plots made by that test
- [x] 'Automated' to run scripts without any interaction after starting
- [x] Global settings(?) Or default test setting(?) for plot template and script directories on remote machines
  - UPDATE: Just uses default multiscripter/ location
- [x] Function which forces the multiScripter to check for any plot frameworks to covert to plots.
  - This will run any time the user hit the 'TAPS' button when viewing a test
## Plot Templates
- [x] fix plot templates always being the wrong vehicle
- [x] Add plot templates (edit, add, remove, etc)
- [x] <b>CONVERT EXISTING TAPS PLOT TO HYPERVISOR TEMPLATE</b>
  - Able to select test to convert from within multi-plot taps xml

</details>

<details>
  <summary>v0.14 Task List</summary>

## general
- [x] Check Function to create empty config file for global config if there is none
- [x] Add 'Both' option for X11/X11vnc forwarding
- [x] VNCviewer support
- [x] Auto detect PuttY, WinSCP, Xming and VNCviewer to allow/block access to things
- [x] Display if it found ---^ and errors associated with it in the settings window
- [x] VNC Configuration in testbed config
- [x] move all .txt command files to seperate folder so the root directory is very clean
- [x] clean up the .txt files not used any more --^ on boot
- [x] FSW Build Check Box for iTACS DB revisions to load FSW local builds
- [x] Status bar at the bottom of main screen for diagnostic information
- [x] Buttons not off/on with configuration changes, fix getting stuck off
- [x] Extra prompt before restarting iTACS, VNC, or both together
## x11vnc
- [x] vncserver setup
- [x] x11vnc setup
- [x] only makes one vncserver per session, auto-reconnects x11vnc
- [x] prompt to kill all active vncservers on exit (might want them up in case of quick hypervisor restart or something)
- [x] button to make new vncserver session to have multiple vnc windows
- [x] Alert user if vncviewer is not installed and they have selected x11vnc
</details>
