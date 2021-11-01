# Crocus
A GreatFET Neighbor for the 2.4 GHz wireless band.

Required KiCad dependency:

https://github.com/greatscottgadgets/gsg-kicad-lib

If you are using git, the preferred way to install gsg-kicad-lib is to use the
submodule:

```
git submodule init && git submodule update
```

# Background

Crocus is based on the Nordic RF nRF24L01+ and was inspired by [The Next Hope Badge](http://goodfet.sourceforge.net/hardware/nhb12/).

A notable capability of nRF24L01+ is 2 Mbps FSK.  Many 2.4 GHz wireless transceiver ICs (including the CC2400 on Ubertooth One) only support FSK up to 1 Mbps.  See [Promiscuity is the nRF24L01+'s Duty](http://travisgoodspeed.blogspot.com/2011/02/promiscuity-is-nrf24l01s-duty.html) for an excellent trick that can be done with Crocus.

## Usage Instructions

FIXME: We don't have any firmware yet, but we should implement capabilities similar to goodfet.nrf.

## Pin Usage

signal  | pin     | alt1  | alt2
--------|---------|-------|-----
SCK     | J1.38   | J2.32 |
COPI    | J1.39   | J2.30 |
CIPO    | J1.40   | J2.38 |
CSN     | via I2C | J1.37 | J1.29
CE      | via I2C | J2.9  | J2.21
SDA     | J2.39   |       |
SCL     | J2.40   |       |
INT     | J2.4    | J2.34 | J1.36

Alternative pins may be selected with solder jumpers.

## I2C Address

The default I2C address is 0x27.  Alternative addresses in the ranges 0x10-0x2F, 0x50-0x67, or 0x70-0x77 may be selected with solder jumpers.  Refer to the Crocus schematic and to the PCA9674 data sheet for details.
