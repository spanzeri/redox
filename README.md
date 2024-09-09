# Build procedure

NOTE: This is meant to be a guide for myself and the specific keyboard I built.

The difference compared to the original build and instructions are:
 * The keymap is slightly different;
 * There is no RGB underglow;
 * I2C is used (instead of serial) and the keyboard is flashed as to allow both halves to be connected as master interchangeably;
 * Support for VIA;

# Getting started

Follow the qmk setup for your OS: https://beta.docs.qmk.fm/tutorial/newbs_getting_started

Replace the redox directory with this one.

It is localed in `<qmk_home>/keyboards/redox/`.

## Compilation

Set the default:
```
qmk config user.keyboard=redox/rev1
qmk config user.keymap=via
```

Compile:
```
qmk compile
```

## Flashing

Connect the left half of the keyboard.

```
qmk flash -kb redox/rev1 -km via -bl avrdude-split-left
```

When prompted, press the reset button on the left half of the keyboard.

Now connect the right half of the keyboard, and repeat the process with the command:

```
qmk flash -kb redox/rev1 -km via -bl avrdude-split-right
```
