# TRACERS L2 ACI Tandem Crossing

An initial two-spacecraft plot using data from published Level 2
TRACERS science CDF files.  This vap should work for anyone, though
see the usage note below about supported time ranges.

At present only ACE, ACI and MSC have released public L2 datasets.

## Usage Notes

This VAP is connected to an events list of Tandem ROI crossings.
Select `Tools > Events List` and single-click on any particular
time to jump to that point.

Location data are requested from a das2 server at a 30-second cadence.
Under magnification at high **MLT** values you may need to increase
the cadence of SPICE model data requests in order to receive 
publication quality values.

The spacecraft location data source annotating the bottom of the
lower panel only provides data that is at least one month old.
If you change the time range of the plot to any point within
the last 31 days you may recieve a prompt for a password.  Ignore
this.  It indicates that you are trying to access data this is
not yet public.

Calculating the sum over all look directions for ACE runs slowly.
This is a known issue.

## Requires

Autoplot v2026a_3 or newer

## Tech Contact

This vap was created by C. Piker.  If you encounter any problems 
please open an issue in this repository.
