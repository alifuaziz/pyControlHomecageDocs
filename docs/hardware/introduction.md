

# Pyboards

- To do debugging use thonny as the IDE for intefacing with the micropython board. This is useful for sending commands outside of the program's automated ways of sending commands. 

- I had some problems right at the start with controlling the files that were on the pyboard. This can be remedied by reseting the pyboard using the USR and RST button on the board. 

- A limitation (?) of serial boards is that only one com port can connect between the host computer and the pyboard at a time. This causes the `access denied` error happening when the REPL or pyControlHomecage tried to connect. 