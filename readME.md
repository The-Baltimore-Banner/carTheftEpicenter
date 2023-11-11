# Auto Theft Analysis 

## Overview

After an exploit that allows certain Kia and Hyundai models to be stolen with only a scredriver and USB stick was discovered and spread over social media in 2022, cities around the U.S. have experienced an car theft crisis that has given rise to auto theft rates not seen in decades.

Baltimore city has been hit particularly hard compared to neighboring localities in Maryland and other. cities around the country.

Here’s how we identified some of the most victimized neighborhoods and blocks in the city. 

## Methodology 

Our analysis relies on the Baltimore Police’s publicly available Part 1 Crime database to identify auto theft incidents, car thefts or attempted car thefts that can leave cars damaged and inoperable. The analysis includes victims who reported their cars stolen or reported an attempt to steal their car. Part 1 Crimes includes crimes reported as far back as 2011, but our analysis mostly relies on auto thefts from 2021 onward.

We rely on the version of the Part 1 Crimes Database generated on Nov. 7, 2023. 

This analysis spatially joins the geolocation coordinates associated with each auto theft to neighborhood, census tract, and real property polygons to associate each theft with a neighborhood, analyze the demographic and socio-economic characteristics of auto theft victims, and ensure that there is no disrepancy between geolocation and address recorded by BPD.

Auto theft incidents were assigned a neighborhood based on geolocation. To ensure accuracy during this process, we excluded a small number of auto theft incidents when the police listed a neighborhood that did not match the one associated with the incident’s geolocation. This choice excluded 34 auto theft incidents, less than 1% of this year’s total.

To identify most frequently victimized blocks, we matched each auto theft incident block shapes created with Baltimore City's Real Property Database. The reason we did this rather than simply relying on the block address recorded by the police in Part 1 Crimes is to avoid address/geolocation mismatches, which could be far more impactful at block level than at the neighborhood level. 

Our analysis of “top blocks” excludes approximately ~2300 auto thefts that were address/geolocation mismatches. These mismatches occured either when lat/long fell outside of its matching block polygon and a buffer zone of the square root of the area of that polygon, didn’t match any block polygon, or matched with a different block polygon. 

The exclusion of these blocks ultimately did not have any real impact on the “top blocks” for auto theft in the city. Mismatches, for the most part, were distributed pretty evenely among blocks.

## Limitations 

There are known errors in the public Part 1 Crimes Database. The database is also frequently changing. While this is expected of any database assembled by humans, it necessitates the kinds of checks described above. 

Part 1 Crimes also does not provide an easy way to differentiate between successful and unsuccessful auto theft attempts. In the database, auto theft incidents are listed under one of three crime codes:

- 7a: Stolen Auto
- 7b: Stolen Bus/Truck
- 7c Stolen Vehicle/Other

About ~9000 auto thefts in the database were 7a’s, about ~400 7b’s, and the rest were 7c’s. Unfortunately the only way to reliably differentiate between an attempted and successful auto theft is examining each auto theft incident’s police report. 

Geocoded coordinates in Part 1 Crimes may not be exact locations. BPD anonymizes geolocation to protect victims’ privacy. Some shootings may have literally taken place just inside or just outside the ranges where The Banner looked, but have locations in the data that included or excluded them in error.

Our demographic analysis relies on the 2021 5-year American Community Survey conducted by the U.S. Census Bureau. 

## License

Copyright 2023, The Venetoulis Institute for Local Journalism

Redistribution and use in source and binary forms, with or without modification, are permitted provided that the following conditions are met:

   1. Redistributions of source code must retain the above copyright notice, this list of conditions and the following disclaimer.

  2. Redistributions in binary form must reproduce the above copyright notice, this list of conditions and the following disclaimer in the documentation and/or other materials provided with the distribution.

  3. Neither the name of the copyright holder nor the names of its contributors may be used to endorse or promote products derived from this software without specific prior written permission.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT HOLDER OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.