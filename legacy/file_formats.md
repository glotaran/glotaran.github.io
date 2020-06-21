---
layout: default
permalink: /legacy/file_formats
title: File formats
---
[← Back to start](/legacy)
<!-- markdownlint-disable MD031 MD033 -->
## Supported File Formats <!-- omit in toc -->

- [Overview](#overview)
- [Plaint text files](#plaint-text-files)
  - [Time explicit format](#time-explicit-format)
  - [Wavelength explicit format](#wavelength-explicit-format)
  - [RAW format](#raw-format)
  - [AVG format {#avg_format}](#avg-format-avg_format)
- [Binary files](#binary-files)

### Overview

Several file formats for reading in data are supported by Glotaran. Two
types of files can be distinguished:

- Plain text or ASCII encoded files, which includes the Time explicit ascii format and the Wavelength explicit ascii format which both have extension `.ascii`, the RAW format which has the extension `.raw`, the AVG format which has the extension `.avg` and `.csv` files wich contain tab or comma separated matrices with or without labels.
- Binary encoded files including `.img` files available from Streak Cameras of [Hamamatsu Photonics](http://www.hamamatsu.com), `.sdt` files with FLIM images from [Becker & Hickl Gmbh](http://www.becker-hickl.de) and `.pt3` image files from [PicoQuant](http://www.picoquant.com) photon counting instrumentation "PicoHarp 300" version 2.

Read more about the various file formats and how to convert your data
into a format that is readable by Glotaran below. Please note that
support for some file format is not enabled by default, but can be enabeled by means of (optional) plugins which you can find in Glotaran under the menu button Tools - Plugins.

### Plaint text files

#### Time explicit format

Time-gated spectrum represents measurements taken simultaneously at a
great number of wavelengths and at a certain time delay with respect to
the exciting pulse t. A time-gated spectrum may be represented as a
vector of length n, where n is the number of wavelengths at which
measurements were made at time delay t. A set of time-gated spectrum
taken at distinct times t<sub>1</sub>, t<sub>3</sub>,\..., t<sub>m</sub>, may be collected into a
matrix of dimensions n by m. Such a matrix is termed a time-resolved
spectrum. The `time explicit` data format allows input of data in the
following form.

The format of the input ﬁle is as follows.

- line 1: reserved for comments, not read
- line 2: reserved for comments, not read
- line 3: the character string “Time explicit”
- line 4: the character string “Intervalnr” and number of recorded timepoints in each timetrace
- line 5: list of the Intervalnr distinct times at which decay traces were recorded
- line 6 and follows: the wavelength (single number) and list of time points at this wavelength \`

Note that each column represents a time-gated spectrum, and each row
represents a decay trace. For an example input file in `Time explicit`
format, see [Example of time explicit data
file](http://glotaran.org/samples/fileformats/te_data_file.ascii "wikilink").
All entries above are space delimited. `Heading line 1` and `Heading
line 2` are two lines that may be filled as the user likes (e.g., with
a data file title). The line containing `Time explicit` indicates the
format that the input data is to take. The line containing
`Intervalnr` and a scalar m indicates the number of distinct time
points m at which measurements were taken, (note that the number of
wavelengths n need not be specified). The following line contains the
real-valued times t1,\..., tm at which measurements were taken. The
first value of each of the remaining lines represent the wavelength at
which the decay trace contained on that row was taken. The rest of each
remaining row represents a (space-delimited) decay trace
Ψ(t<sub>1</sub>,λ),Ψ(t<sub>2</sub>,λ),\...,Ψ(t<sub>m</sub>,λ). After all datapoints are specified
the file can contain line `Integrated fluorescence` followed by tab or
space delimited vector containing total fluorescence for each timestep.
Note that for real experiments the number of data points Ψ(t,λ) is on
the order of 10,000-100,000.

#### Wavelength explicit format

Decay traces represent measurements taken at a great number of times at
some particular wavelength λ. A decay trace may be represented as a
vector of length m, where m is the number of time points at which
measurements were made. A set of decay traces taken at distinct
wavelengths λ<sub>1</sub>, λ<sub>2</sub>, \..., λ<sub>n</sub>, may be collected into a matrix of
dimensions m by n. Such a matrix is again termed a time-resolved
spectrum. The `Wavelength explicit` data format allows input of data
to TIM in the following format.

The format of the input ﬁle is as follows.

- line 1: reserved for comments, not read
- line 2: reserved for comments, not read
- line 3: the character string “Wavelength explicit”
- line 4: the character string “Intervalnr” and number of recorded wavelengths in each timetrace
- line 5: list of the Intervalnr distinct wavelengths at which time traces were recorded
- line 6+: the time point (single number) and list of spectra data points at this time

Note that each column represents a decay trace, and each row represents
a time-gated spectrum.

For an example input file in `Wavelength explicit` format, see an [example time explicit data file](./resources/fileformats/te_data_file.ascii). In this file, all entries are space delimited.

**Line 1-2**: `Heading line 1` and `Heading line 2` are two lines that may be anything (e.g. a reference to the original filename or author).

**Line 3**: The line containing `Wavelength explicit` indicates the format that the input data is to take.

**Line 4**: The line containing `Intervalnr` and a scalar n indicates the number of distinct wavelengths n at which measurements were taken, (note that the number of time points m need not be specified).

**Line 5**: The following line contains the real-valued wavelengths λ<sub>1</sub>, λ<sub>2</sub>, \..., λ<sub>n</sub> at which measurements were taken. The first value of each of the remaining lines represent the time at which the time-gated spectrum contained on that row was taken.

**Line 6+**: The rest of each remaining row represents a (space-delimited) time-gated spectrum Ψ(t,λ<sub>1</sub>),Ψ(t,λ<sub>2</sub>),\...,Ψ(t,λ<sub>m</sub>). After all datapoints are specified the file can contain line `Integrated fluorescence` followed by tab or space delimited vector containing total fluorescence for each timestep. Note that for real experiments the number of data points Ψ(t,λ) is on the order of 10,000 to 100,000.

#### RAW format

RAW format was developed in the Laboratoire d`Optique et Biosciences,
Ecole Polytechnique, to store pump-probe data. The header of the file
contain following information:

- Comment line
- version : Version f the file
- nzone : N - number of timezones that used during during experiment
- full time zone #i : t<sub>i</sub> - N lines with end times of the timezones (i = 1:N)
- start pixel : m - starting pixel on the CCD
- pixel width : Δm - width in pixels of the active CCD zone
- number of calibration points : l - number of the calibration points of the spectrometer
- pixel calibration point j : m<sub>j</sub> - number of calibrated pixel (j = 0:l-1)
- lambda calibration point j : λ<sub>j</sub> - corresponding wavelength to pixel m<sub>j</sub> (j = 0:l-1)
- number of time steps zone #i : n<sub>i</sub> - number of timesteps in corresponding timezone
- number of performed scans : k - number of scans used for averaging`

after header all data points (transmition of the sample) saved in the
column, starting from first time point. Example of a data file:
[HB180301.RAW](./resources/fileformats/HB180301.RAW "HB180301.RAW").

#### AVG format

The AVG format is commonly used to hold averaged transient spectra data.
In this format for every recorded wavelength (in rows) and at every
probe delay (columns) two values are specified. The first values is the
actual measured (average) value, and the second is the corresponding
error (due to fluctuation in the laser light). Currently nothing is done
with the error value for each data point but just ignored in order to
successfully read in the file. The probe delay used for each data point
is included in the header of the file (the lines starting with the
\"\#\" symbol).

Typical file structure is as follows:
<pre>
# Comments
# etc.
#
# Delay:    -1000.000                   -100.000

1579.06     1.0039832 0.00062804847     1.0049483 0.00060386888
1575.69     1.0044705 0.00064121636     1.0053659 0.00062344205
1572.33     1.0048679 0.0007405209      1.0058121 0.00072175045
etc
</pre>

which corresponds to:
|  Wavelength |  avg-value |  error-value | avg-value |  error-value |
| --- | --- | --- | --- | --- |
| wavelength1 | avg-val1-at-time1 | error-value1-at-time1 | avg-val1-at-time2 | error-value1-at-time2|
| wavelength2 | avg-val2-at-time1 | error-value2-at-time1 | avg-val2-at-time2 | error-value2-at-time2|
| wavelength3 | avg-val3-at-time1 | error-value3-at-time1 | avg-val3-at-time2 | error-value3-at-time2|
| etc |  |  |  |  |

### Binary files

For more information on supported binary encoded files, refer to the manufacturer's website:

- `.img`; [Hamamatsu Photonics](http://www.hamamatsu.com)
- `.sdt`; [Becker & Hickl Gmbh](http://www.becker-hickl.de)
- `.pt3`; [PicoQuant](http://www.picoquant.com)
