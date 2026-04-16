# TS2/MAGIC Test Spectrum

This vap was used for sanity checks of initial public MAGIC L2 data.
It is a simple three axis 128 point power spectral density plot of
16 Hz MAGIC Level 2 data, which confirms that there is indeed a 
magnetometer in a 90 minute polar orbit of Earth.

## Source

MAGIC data are pulled from public CDFs. Orbit position data are
supplied by a das2 server at one minute intervals.

## Usage Notes

This VAP is connected to an events list of TRACERS-2 orbit definitions.
Select `Tools > Events List` and single-click on any particular
time to jump to that point.

## Tech contact

This vap was created by C. Piker, though anyone else is welcome to 
maintain it if updates are necessary.
