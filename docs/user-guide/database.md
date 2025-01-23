
## Queues

- table update queue
  - The following line of code adds the nane of the table that needs to be updated to an 'update queue' that is then handled (and updated) in the `main_gui.py` method (`GUIApp.refresh()` function)
  - database.update_table_queue.append("setup_tab.list_of_setups")

- message_queue
-

- com: communication between the main computer and the microcontrollers (pycontrol and access control)
- access_control_upy: the firmware that goes onto the micropython board
- gui_tabs: the user interface for controlling things
- dialogs: popups for the user
- pyControl: [...]
- tables: see the table information (table widgets that are used to display all the information into the gui).
