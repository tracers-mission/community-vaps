# Community VAPs

[Autoplot](https://autoplot.org) saves it's state in files that end in the extension `.vap`.
Opening a .vap file in Autoplot quickly returns it to a previous state so that you can pickup
where you left off.  These files contain plot configuration and data source locations, but
don't usually contain the data themselves.  Thus `vap` files are small and easy to send
in messages, orstore in a code repository... like this one.

Offical Autoplot vap files provided by the TRACERS Science Operations Center (SOC) are stored on
the University of Iowa [gitlab server](https://research-git.uiowa.edu/space-physics/tracers/autoplot).
That's all well and good, but SOC is just the beginning of TRACERS data visualization, not the end.  

This repository provides Autoplot setup files created by you to preform specific tasks 
useful to your research. You can share these vaps with others by commiting them here, to the 
community vap repository.

## Root Locations

Autoplot is famously flexible and will read data from many sources.  One of the most common
ways is to simply give it a URL pattern, called a file aggregation, that ties the time axis
to filenames.  There are two root locations for CDF URL patterns.

|Purpose         | URL    |
|----------------|--------|
|Public          |https://tracers-portal.physics.uiowa.edu/ | 
|Team Pre-release|https://tracers-portal.physics.uiowa.edu/teams/flight/SOT/prerelease/ |

<img width="1438" height="476" alt="public_vs_prerel" src="https://github.com/user-attachments/assets/5cc20885-6c58-4df0-af8a-decb3458f785" />

The team pre-release area requires authentication.  Under each area are three top level directories.
Prior to release data will appear in the Science Team's pre-release directory.  Upon public
release data will appear in the same relative sub-directory structure, but under the *Public*
URL above.  Note that files will appear in **one** of the two locations, but **not both**.

## Sub-directory organization

MAGIC data are in thier own area and are not subject to same release latency requirements
as the Level 2 and Level 3 science instrument CDFs.

| Sub Directory | Content                   | Organization                        | Publication Latency   |
|---------------|---------------------------|-------------------------------------|-----------------------|
| L2            | Level 2 CDFs by spacecraft| {spacecraft}/{year}/{month}/{day}   | 31 days after reciept |
| L3            | Level 2 CDFs by spacecraft| {spacecraft}/{year}/{month}/{day}   | 62 days after reciept |
| MAGIC         | All MAGIC CDFs            | {spacecraft}/{level}/{year}/{month} | - |

## Filename tokens

Each file on the public site uses the following underscore-separated filename pattern:

  `{craft} "_" {level} "_" {instrument} "_" {dataset} "_" {date} "_v" {version} ".cdf"`

Note that sub-fields are separated by a minus sign `-`.  Values for each section appear below.

| Section | Purpose | Values |
| :-------| :------ | :------|
| {craft} | Spacecraft that supplied data | **ts1 ts2 tdm** | 
| {level} | The data processing level     | **lv2 lv3** |
| {instrument} | The associated instrument | **ace aci efi mag msc magic** |
| {dataset} | The mission dataset         | **bac bdc-16sps eac edc ehf def ipd pitch-angle-dist vac vdc** |
| {date}  | UTC start time of daily data file coverage | **yyyymmdd** |
| {version} | A three section version | **major.minor.revision** |

A breakdown of each dataset follows.

| Dataset | Description |
| :-------| :---------- |
| bac | Magnetic waves @ 1024 Hz |
| bdc-16sps | Magnetic fields @ 16 Hz |
| eac | Electric waves @ 1024 Hz |
| edc | Electric fields @ 16 and 128 Hz |
| ehf | Electric waves @ 20 MHz |
| def | Differential Electron Flux |
| ipd | Differential Ion Flux |
| pitch-angle-dist | Pitch angle distribution |
| vac | Voltage differential @ 1024 Hz |
| vdc | Voltage differential @ 16 and 128 Hz |

## Versions

Only the highest version of each file is available on either the Public or Pre-Release URLs.
Old versions are kept and can be supplied, but do not live at the URLs above.  The breakdown
for the version numbers is roughly:

| Version Field | Changes if |
| :------------ | :----------|
| major         | The structure of the data file has changed in a backwards incompatable manner, client software updates are likely |
| minor         | Additional features have been added but old software should still work. May also be use to indicate a calibration change |
| revision      | Additional data have been added to the file |



