# Word Condition Study

Memory task. Presents words, either with sensations or for retrieval of past sensations.

## Usage

Note that the practice experiments have been removed. To run a practice experiment, run the normal Encoding or Retrieval experiment and enter "0" for the Session Number.

There are two versions of the Encoding task script
- `EncodingBNC`: NI-DAQ only, doesn't control temperatures from the script. The sequence of temperatures must be programmed on the QST TCS II. TTL pulses are sent from the NI-DAQ to trigger the QST/Digitimer.
- `EncodingSerial`: NI-DAQ and USB to QST, sends temperatures directly from the script.

To abort in the middle of a session: `Ctrl + Alt + Backspace`

### Session/Subject Settings

The stimulus temperatures are set in the `EncodingSerial.startupInfo3` file. All measurements are in Celsius. This only works for the `EncodingSerial` version.

Please also ensure the correct COM port is chosen in the `EncodingSerial.startupInfo3` file, under `Serial.CommPort`. You can check this using CoolTerm.

See the following:
- [CoolTerm](https://freeware.the-meiers.org/): lets you find the COM port #
- [Serial Device](https://support.pstnet.com/hc/en-us/articles/229359687-DEVICE-Serial-Device-17355-)
- [How do I verify the port number?](https://support.pstnet.com/hc/en-us/articles/115000899908)
- [Programming reference](https://pstnet.com/ecr/#t=E-Objects/SerialDevice-Object.htm)

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