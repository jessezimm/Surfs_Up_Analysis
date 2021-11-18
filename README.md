# Surfs Up Analysis

## Overview
The purpose of this analysis is to compare the temperatues in June and December in Hawaii. Summary statistics are collected for both months to aid in this analysis. Weather-related statistics can help the investor decide if it appears profitable to set up an icecream shop in Hawaii.

## Analysis
The three key takeaways from this analysis are listed below.

* The mean temperature in December is 71 degrees while in June it is 75 degrees. This is not a huge difference in terms of comfortable icecream-eating weather.
* The interquartile range for December is 5 degrees (69 to 74 degrees) and the interquartile range for June is 4 degrees (73 to 77 degrees). This shows that there is minimal dispersion in temperatures throughout these months and the temperature is relatively consistent.
* There are 1517 temperature observations in December and 1700 observations for June. This is an adequate sample size for means of comparison between the two months.
<img width="176" alt="Dec_temps" src="https://user-images.githubusercontent.com/88340176/142460517-03483246-fcc5-4d4a-ad7c-6a22aaf6164e.PNG">
<img width="180" alt="June_temps" src="https://user-images.githubusercontent.com/88340176/142460531-9c0b1ff7-8cbb-462f-b188-afc5afcdbdb9.PNG">

## Summary
Given a sufficient number of observations, the warm mean temperature, and the limited dispersion around the mean, the investor should feel comfortable investing in the icecream shop. Other variables such as precipitation and population could further inform the investor's decision. These additional queries below can be used to collect the summary statistics of precipitation for the months of December and June.

December Precipitation:  
def prcp_monthly():  
    results = session.query(Measurement.tobs).\  
      filter(extract('month', Measurement.prcp) == 12).all()  
    prcps = list(np.ravel(results))  
    print(prcps)  
    return prcps  
prcps = list(np.ravel(prcp_monthly()))  
Dec_prcps = {'Dec_prcps': list(prcps)}  
Dec_df = pd.DataFrame(data=Dec_prcps)  
Dec_df.describe()  
  
June Precipitation:  
def prcp_monthly():  
    results = session.query(Measurement.tobs).\  
      filter(extract('month', Measurement.prcp) == 6).all()  
    prcps = list(np.ravel(results))  
    print(prcps)  
    return prcps  
prcps = list(np.ravel(prcp_monthly()))  
June_prcps = {'June_prcps': list(prcps)}  
June_df = pd.DataFrame(data=June_prcps)  
June_df.describe()    
