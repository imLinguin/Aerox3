# [Aerox 3](https://steelseries.com/gaming-mice/aerox-3) Reverse Engineering Results


# Zones Scheme
This is the way I numbered them in [Colors](#colors) below

![](zone-scheme.png)

# Colors
### Zone 1
`21 01 rr gg bb 00 00 00 00 00 00`
### Zone 2
`21 02 00 00 00 rr gg bb 00 00 00`
### Zone 3
`21 04 00 00 00 00 00 00 rr gg bb`

# LED Brightness
### Ilumination Disabled - 0
`23 00`
### 1/4
`23 0c`
### 2/4
`23 19`
### 3/4
`23 32`
### Full - 4/4
`23 64`

# Reactive Effect
This is the reaction for any mouse button clicked. (Wave looking color comming from top to bottom.)
It can be enabled or disabled

`26 01 00 rr gg bb`

## Effect Disabled
`26 00 00 00 00 00`

# Pooling Rate
### 1000Hz
`2b 01 00 00 00 00 00 00 00 00 00 00 00 00 00 00`
### 500Hz
`2b 02 00 00 00 00 00 00 00 00 00 00 00 00 00 00`
### 250Hz
`2b 03 00 00 00 00 00 00 00 00 00 00 00 00 00 00`
### 125Hz
`2b 04 00 00 00 00 00 00 00 00 00 00 00 00 00 00`

# DPI
Maximum 5 profiles are supported

DPI must be between 200-8500

### Example of setting 5 profiles, first mode is current
![](dpi-example.png)

`2d 05 00 04 12 1b 34 c5 00 00 00 00 00 00 00 00`

### Anatomy of data sent

`2d NUMBER_OF_PROFILES CURRENT_PROFILE`

There must be at least one profile

CURRENT_PROFILE starts from 00 to 04


# Save (Surely)
It's being sent always after changing DPI, Pooling Rate etc. and clicking `Save` in engine

`11 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00`
