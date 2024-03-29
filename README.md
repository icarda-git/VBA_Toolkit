# ICARDA VBA Toolkit for Excel

**_Copyright:_** 2019-2022, ICARDA

**_Author:_** Khaled Al-Shamaa <k.el-shamaa@cgiar.org>

**_Version:_** 3.0

**_License:_** This program is free software: you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version.

**_Disclaimer:_** This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License for more details.

**_Citation:_** Khaled Al-Shamaa (2022). ICARDA VBA Toolkit. ICARDA, Cairo, Egypt. URL https://github.com/icarda-git/VBA_Toolkit

## Function Description

### DMS2DD
Convert Degrees Minutes Seconds (DMS) coordinates to Decimal Degrees (DD) format.

`dms2dd(string)`

### DD2DMS
Convert Decimal Degrees (DD) coordinates to Degrees Minutes Seconds (DMS) format.

`dd2dms(double)`

### DDM2DD
Convert Degrees Decimal Minutes (DDM) coordinates to Decimal Degrees (DD) format.

`ddm2dd(string)`

### DD2DDM
Convert Decimal Degrees (DD) coordinates to Degrees Decimal Minutes (DDM) format.

`dd2ddm(double)`

### DD2OLC
Encode a location coordinates in decimal degrees (latitude and longitude in [WGS84](https://en.wikipedia.org/wiki/World_Geodetic_System)) into [Open Location Code](https://github.com/google/open-location-code/blob/master/docs/specification.md) string.

`dd2olc(latitude, longitude [, codeLength])`

* `codeLength`: Default value is 10. This provides an area that is 1/8000 x 1/8000 degree in size, roughly 14x14 meters.

### OLC2DD
Decode an [Open Location Code](https://github.com/google/open-location-code/blob/master/docs/specification.md) string into its location coordinates in decimal degrees (latitude and longitude in [WGS84](https://en.wikipedia.org/wiki/World_Geodetic_System)).

`olc2dd(string [, coordinates, codeLength])`

* `coordinates`: Default value is 0 (i.e., both latitude and longitude in decimal degrees as a string with comma separator). Other options includes 1 to return latitude and 2 for longitude (both in decimal degrees).
* `codeLength`: Default value is 10. This provides an area that is 1/8000 x 1/8000 degree in size, roughly 14x14 meters.

### VOLC
Determine if an Open Location Code is valid.

`volc(string [,codeLength])`

* `codeLength`: Default value is 10. This provides an area that is 1/8000 x 1/8000 degree in size, roughly 14x14 meters.

### Barcode
Generate the Code 128 Barcode, including the checksum. [Output font is Libre Barcode 128](https://fonts.google.com/specimen/Libre+Barcode+128).

`barcode(string)`

## List of Examples				
|Function|Example Call|Example Input|Example Output|
|---|---|---|---|
|DMS2DD|=dms2dd(C3)|6° 42' 56.88'' W|-6.7158|
|DD2DMS|=dd2dms(C4)|-6.7158|6°42'56.88"|
|DD2OLC|=dd2olc(C5, C6)|33.810558|8G5QRX6R+65|
| | |35.990411|[https://plus.codes/8G5QRX6R+65](https://plus.codes/8G5QRX6R+65)|
|OLC2DD|=olc2dd(C7)|8G5QRX6R+65|33.8105, 35.990375|
|OLC2DD|=olc2dd(C7, 1)|8G5QRX6R+65|33.8105|
|OLC2DD|=olc2dd(C7, 2)|8G5QRX6R+65|35.990375|
|Barcode|=barcode(C10)|C0M2Pe1AzUn4R|ÌC0M2Pe1AzUn4RjÎ|
|DDM2DD|=ddm2dd(C11)|31 41.592|31.68333333|
|DD2DDM|=dd2ddm(C12)|31.4159|31°24.954'|

## Loading into Excel

1. Download the ZIP file of this VBA toolkit > unzip it somewhere on your computer.
2. Start Excel > right-click on the worksheet name tab > click "View Code". 
   
   _This will open the "Microsoft Visual Basic for Application" editor window._
3. In the "Microsoft Visual Basic for Applications" window > File menu > click "Import File...".
4. Browse to the "ICARDA_VBA_Toolkit.bas" file and import it, then close this MS VBA window.
   
That's it. Save the Excel file. You can now use this toolkit functions in that spreadsheet!

## Loading into OpenOffice/LibreOffice

To add the library to a OpenOffice or LibreOffice spreadsheet, follow these steps (this example uses LibreOffice):

1. Select the menu option Tools > Macros > Organize Macros > LibreOffice Basic
2. In the Macro From panel, select the spreadsheet to add the library to.
3. Click New, enter a name for the module (e.g. ICARDA_Toolkit), and press OK. It will then display the macro editor.
4. Paste the full file into the editor, replacing the existing contents.
5. Uncomment the line to enable VBA compatibility:

`Option VBASupport 1`

That's it. Save the file. You can now use the functions above in your spreadsheet!

