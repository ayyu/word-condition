# Word Condition Study

There are two versions of the Encoding task script
- **BNC**: NI-DAQ only, doesn't control temperatures from the script. The sequence of temperatures must be programmed on the QST TCS II. TTL pulses are sent from the NI-DAQ to trigger the QST/Digitimer.
- **Serial**: NI-DAQ and USB to QST, sends temperatures directly from the script.

## Usage

Note that the practice experiments have been removed. To run a practice experiment, run the normal Encoding or Retrieval experiment and enter "0" for the Session Number.

To abort in the middle of a session: `Ctrl + Alt + Backspace`

### Setting Temperatures

The stimulus temperatures are set in the `EncodingSerial.startupInfo3` file. All measurements are in Celsius.


## Equipment

- One National Instruments USB-6341
- Two Digitimer DG2A Train Generators
	- One of each INPUT connected to BNC ports P1.0 and P1.1
	- Both MODE should be set to GATED
- Two Digitimer DS7A Stimulators, set to the correct thresholds per subject
	- Connected to OUTPUT of respective DG2A
- One QST Thermal Cutaneous Stimulator (TCS II), with two possible connections
	- **BNC**: can't control temperatures and QST must be programmed with trial temperature sequence
	- **USB**: connect using USB B to A cable to "COMPUTER IN/OUT", temperatures controlled directly from E-Prime

### Connections on National Instruments NI USB 6341 (BNC)

- P1.0 = Electric 1 = Low
- P1.1 = Electric 2 = High
- P1.2 = Thermode (if using BNC to trigger)