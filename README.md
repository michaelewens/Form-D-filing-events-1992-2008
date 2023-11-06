# Form D filings events 1992 - 2008
The [data on Form D filings](https://github.com/michaelewens/formD_filings_1992_2008/blob/master/rawFormD_clean.csv) was made available from a FOIA request with the Securities and Exchange Commission (SEC) in 2018.  The data is used in the paper "[The Deregulation of the Private Equity Markets and the Decline in IPOs](https://academic.oup.com/rfs/article/33/12/5463/5835291)" by Ewens and Farre-Mensa (2020) to study the impact of regulatory changes to Regulation D and was originally part of an analysis (Figure 2, page 10) done by the SEC ["Capital Raising in the U.S.: An Analysis of the Market for
Unregistered Securities Offerings, 2009-2014"](https://www.sec.gov/files/unregistered-offering10-2015.pdf)(pdf).  Vladimir Ivanov was instrumental in helping us acquire the data. 

The data has the following structure:

* `cik`: Central Index Key (CIK) 
* `Sub_Type`: filing type (e.g. REGDEX or D)
* `File_No`: internal SEC number for filing
* `Exemps`: comma separated list of Reg D exemption codes [see this description for 2019](https://www.sec.gov/fast-answers/answers-regdhtm.html)
* `year`: filing year
* `issuer`: company or fund name
* `file_date`: filing date
* `exemption`: the main exemption used (6 = "06"). The 'exemps' column may list multiple, but this column takes the "max" where 6 subsumes 5 and 5 subsumes 4.

## Notes on usage 

Users of the data should be aware that many of the filers are funds or investment companies.  These are not indicated with a variable, so some string searches are required to remove or flag them (e.g. "funds", "credit", "investments", "iii", "ix", etc.). 

If you use this data, please cite:

 ```Latex
@article{ewens2020deregulation,
  title={The deregulation of the private equity markets and the decline in IPOs},
  author={Ewens, Michael and Farre-Mensa, Joan},
  journal={The Review of Financial Studies},
  volume={33},
  number={12},
  pages={5463--5509},
  year={2020},
  publisher={Oxford University Press}
}
 ```
  
Ewens, Michael, and Joan Farre-Mensa. "[The deregulation of the private equity markets and the decline in IPOs](https://academic.oup.com/rfs/article/33/12/5463/5835291?login=true&casa_token=Dcqgi_N7QI8AAAAA:ZWcgop_X7TsC4JVLUwv8vPQynQrWkrVYYY-M1I1PruFgwJoq3GMGH-m9cwOmPPupZfwK1vLDynM)." The Review of Financial Studies 33, no. 12 (2020): 5463-5509.

## Example analysis from Ewens and Farre-Mensa (2020)

The following figure reports the number of non-fund filings by exemption 506 vs other exemption types around the passage of NSMIA:

![Ewens and Farre-Mensa (2020, Figure 1)](https://github.com/michaelewens/formD_filings_1992_2008/blob/master/formDfilings_nsmia.png)
