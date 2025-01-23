
## Classes

### Pyboard class inside pyboard.py

- This is the class that is shared between the pyboard and the main script.
- Handles core functionality of the using the pyboard from the main program.
- Pyboard error the normal error in functionality, however tells use the error is coming from the pyboard class
-

### Access control class(Pyboard)

- Class that is in the main script. However acts as an interface between the access control module and the main computer.
- contruction requires:
  - Serial_port (print function definition & datalogger)
  - This is the port that is used to read and write information from.
- It inherits from the Pyboard class
- This class has functions such as
    def loadcell_tare(self):
        self.exec('access_control.loadcell.tare()')
- This runs the code to reset the loadcell back to 0.
  - Done by using the self.exec.
  - This uses the serial.write() function.
  - Serial.write, is a function that writes data to a USB port.
- self.exec is defined in the Pyboard class
- There are also methods for:
  - loadcell_tare; loadcell_calibrate; loadcell_weigh; rfid_read_tag.

- The access control framework that has been written as well as the pyControl framework are uploaded to the board using the Access_control.load_framework() function.
  - This is the thing that is currently raising an error
- Access_control.process_data()
  - This is a function that reads all data that is in the serial ports input buffer
  - The data from the serial port is wrapped in the `'start_'` `'_end'`. htere is code that check for these things

### Data_logger

- Description:
  - Class for logging data from pyControl setups to disk
- Constructor:
  - data_filepath
- Data consumers: are things that get data (from data producers). These are added to a list that can then be processed.
- Access Control Setups (dataproducer) -> Homecage Software (dataconsumers -> data producer)  -> Database (Dataconumers)
  - This is the example flow of data from the hardware setup to behavioural results that are written to disk then analyised.
  - In my codebase the data_logger.process_data(new_data) is a function processes this consumer list similar to an event queue

- What does flush do? <https://stackoverflow.com/questions/7127075/what-exactly-is-file-flush-doing>
  - It basically handles the emptying of buffers from the data that is being written to disk. this must be because sometimes all the data is not handled in the way that you would want.

### System_handler(Data_logger)

- description: This is a class that sits on top of access control and pycboard classes
        and controls data storage for the system as well as setting tasks when
        mice enter/exit the training apparatus. There is one system controller
        for each homecage system.
  - This function tells the GUI / datastructures what to do once it gets a command from the microcontroller
  - And updates the states of various databases appropriately.
  -
- `system_controller.process_ac_stat`
  This is a function that handles the current state of the of the access control (this signal comes from the
  `access_control/mainscript for microcontroller`).
  Each of these states needs to have a different types of handling
  This is done by the system handler class.
    Example handling:
      s
      A new mouse enters: this resets the dict of attributes that is associated with the handler.

Most of the handling involves calling a function that writes appropriate data to the `database` dataframes
e.g. `_update_database_on_entry` writes which mouse (identified from an RFID) is `in_training`, its `weight`

- this is the `mouse_df` and the `setup_df`

- `process_data_AC`
- This processes the state data that is being returned from the pyb.
-

### Pycboard

description: inherits from the PyBoard class

- Adds functionality that is specific for the pycontrol board:
  - e.g. File transfer / Load pycontrol framework

### Pycontrol

- Framwork file
- state machines
- hardware files

- Things are uploaded onto the board (what the state machine that is running on the board is)
- What the hardware in the state machine.
