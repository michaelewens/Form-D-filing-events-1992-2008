# Form D filings events 1992 - 2008
The [data on Form D filings](https://github.com/michaelewens/formD_filings_1992_2008/blob/master/rawFormD_clean.csv) was made available from a FOIA request with the Securities and Exchange Commission (SEC) in 2018.  The data is used in the paper "[The Deregulation of the Private Equity Markets and the Decline in IPOs](https://papers.ssrn.com/abstract=3017610)" by Ewens and Farre-Mensa (2019).   The data was originally part of an analysis (Figure 2, page 10) done by the SEC ["Capital Raising in the U.S.: An Analysis of the Market for
Unregistered Securities Offerings, 2009-2014"](https://www.sec.gov/files/unregistered-offering10-2015.pdf)(pdf).

The data has the following structure:

* `cik`: Central Index Key (CIK) 
* `Sub_Type`: filing type (e.g. REGDEX or D)
* `File_No`: internal SEC number for filing
* `Exemps`: comma separated list of Reg D exemption codes [see this description for 2019](https://www.sec.gov/fast-answers/answers-regdhtm.html)
* `year`: filing year
* `issuer`: company or fund name
* `file_date`: filing date
* `exemption`: the main exemption used (6 = "06"). The 'exemps' column may list multiple, but this column takes the "max" where 6 subsumes 5 and 5 subsumes 4.

## Example analysis from Ewens and Farre-Mensa (2019)

The following figure reports the number of non-fund filings by exemption 506 vs other exemption types around the passage of NSMIA:
