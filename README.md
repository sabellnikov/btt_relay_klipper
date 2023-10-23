# Thanks [talv2010](https://github.com/talv2010) and [sobieh](https://github.com/sobieh)

BTT Relay Firmware mod for Klipper

## Upload
1. Install [python 3.x](https://www.python.org/downloads/)

2. PowerShell command
```bash
pip install stcgal
```

3. Connect your board to any USB to Serial adapter

4. Put on Reset jumper

5. PowerShell command
```bash
upload.bat COM#
```
 where # is your COM port number

6. Erase Reset jumper


## Klipper printer.cfg
Add this lines to your printer.cfg config file:

```bash
  [output_pin RELAY_ON_OFF]
  pin: YOUR_MOTHERBOARD_PIN
  value: 1
```
Now after Klipper starts it should set HIGH level on pin

Emergency Stop set LOW level, so printer will lost power

You can use G-code to remove power:

```python
  SET_PIN PIN=RELAY_ON_OFF VALUE=0 ; immediately shut down the printer
```

## Modify by your own
Microcontroller: STC15W204S

[Keil C51 uVision](https://www.keil.com/demo/eval/c51.htm)

[STC ISP programming software (v6.91)](https://www.stcmicro.com/rar/stc-isp6.91.rar)

For uVision compiler setup use that [video](https://youtu.be/nHCjFw2TS4M?feature=shared)
