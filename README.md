# SAS_LISA_V694_Mon
V694 Mon Sample dataset taken with a Shelyak LISA  spectrograph.
SIMBAD reports the target spectrum as a M4ep+Beq D -- this has a quality rating of "D"
on a A (good) to E (bad) scale. The report is from 
Bidleman and MacConnell 1973AJ.....78..687B.  VSX reports 	M5.5III+WD no citation.

VSX (AAVSO Variable Star Index Search)
https://www.aavso.org/vsx/index.php?view=detail.top&oid=19522

V0694 Mon	 AAVSO UID	000-BBN-085 (55458 observations)	 
Constellation	Monoceros
J2000.0	07 25 51.28 -07 44 08.2  (111.46367 -7.73561)

Proper motion	RA: 1.529 +/- 0.959 mas/y	Dec: 1.191 +/- 0.823 mas/y	Source: Gaia DR1
Galactic coord.	223.760 +4.046

Variability type	ZAND	
Spectral type	M5.5III+WD
Mag. range	8.88 - 12.7 V	Get description for the passbands
Discoverer	--
Epoch	07 Jul 1990 (HJD 2448080)	 Ephemeris
Outburst	-- Period	1943 d  (5.32 y)

ZAND Symbiotic variables of the Z Andromedae type. They are close
binaries consisting of a hot star, a star of late type, and an
extended envelope excited by the hot star's radiation. The combined
brightness displays irregular variations with amplitudes up to 4
mag. in V. A very inhomogeneous group of objects.

It was the subject of a AAVSO special notice:
https://www.aavso.org/aavso-special-notice-429


TEST DATA SUITE PROCESSING NOTES

Readme notes for processing the V694 Mon sample spectrum data on GitHub

The data is located at the following URL.

https://github.com/dxwayne/SAS_LISA_V694_Mon

This test dataset is based on data acquired with a Shelyak LISA.  So, you will see spectral data that spans the full visual range from about 3725Å to about 7275Å.  Almost all the processing steps for this data would be the same if you had a Shelyak ALPY.  The major difference if you have an ALPY is that you would have to in addition, determine the “Smile” on the Calibration tab.  If you have a Shelyak LHIRESIII, you certainly would not use the “LISA-argon-15.lst” file I have provided and would probably instead use one of the Predefined modes under Spectral calibration on the General Tab.

Specific information you will need to enter into ISIS to process this data is as follows:

Note do not enter the quotes.

Settings Tab

Spectrograph model” “LISA”

Longitude: “111.802777”

Latitude: “33.3672222”

Altitude: “380”

Spectral domain for profile scaling “6690” – “6705”

General Tab

Under General parameters: set the following values:

Pixel size: “6.45”

Cosmetic file: “cosm”

Under Spectral calibration, choose File mode and enter the file name: “Lisa-argon-15”

Under File name prefix and suffix, use the following values:

Object suffix:		 “-“	

Calibration suffix:	“_NeAr-“

Calibration prefix:  	Leave it blank

Calibration Tab

For the X coordinate of line at wavelength: “5944.834”

Masters Tab

There is nothing much you have to do here as I have provided a Master Dark named Dark900-10C.fit and Master bias which is named zero-10C.fit

However, you will need to enter the following values into the fields below the section for Compute a flat-field image.

Generic name; “Flat-“

Dark image: “Dark900-10C”

Offset image: “zero-10C”

Result: “Flat”

Additional notes:

I have included a file in the GitHub named “Flat.fit” which actually is the Master flat but it is instructive to go to the Master tab and produce a new one yourself from the 10 raw Flat fits files.

I have also included a file named “ISIS-rename.ps1”.  This is a Microsoft Powershell script that you can use if you acquire your spectral data using MaximDL.  What it basically does is to strip off the leading zeros in the MaximDL file sequence such that “0001” is written “1” which is the sequence number format that ISIS demands.

You will see a folder named “Calib”.  In it you will find the cosmetic file, Master Dark, Wavelength Calibration file named LISA-argon-15.lst and the Master Bias or as I have named it Zero file.  ISIS is friendly in this way regarding organizing your files in your working directory.  Since these files are often used for days or weeks, It is handy to be able to just copy this “Calib” subfolder into the working directory for your next acquired spectrum data.

