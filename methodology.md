**General overview of the Mapping Privacy dashboard**

This dashboard was created to uncover the real availability of PA API traffic without 3rd-party cookies worldwide and by country. By the courtesy of RTB House, AdLook and PrimeAudience who shared their data with the authors of this report, it has been discovered that the cookieless traffic available via PA API is much lower than the 0.75% claim provided by the Chrome browser and strongly depends on the market and the approach of companies operating in the area.

**All PA API scale**

The straightforward approach of simply comparing the number of PA API bid requests from Chrome browsers without third-party cookies to all incoming bid requests from Chrome is not feasible due to technical differences between PA API and classic bid streams. Such a simplification inflates the numbers leading to false conclusions. The values calculated this way are also visible below the addressable metric to show how much the approach changes the results.

**Addressable PA API scale**

Addressable bid requests are used to present the current scale. These bid requests represent users who are available for a buyer to bid for. Specifically, for this case they are the users who belong to at least one buyer’s interest group. The values are presented in packets aggregated by week. The green or red indicator above the value shows the week-to-week change.

**More technical details**

Addressable PA API scale is then calculated in the following way: Scale = a/b * 100%, where

a - stands for addressable PA API bid requests from cookieless Chrome

b - stands for all addressable bid requests incoming via Chrome

The source for counting PA API addressable bid requests are the bid debug reports. Since one bid request can include multiple interest group and may result in multiple auctions performed, they are deduplicated by the request ID. Only the bid requests from Chrome treatment_1.* labels (cookieless) are included to calculate addressable PA API bid requests.

To calculate all addressable bid requests coming from Chrome browsers both the 

This logic is described visually in the addressable_paapi_scale.png file.

**Technical details impossible to include**

Bid debug reports are the only source for the analysis of the incoming bid requests in PA API. Their character doesn't allow to include some factors that may influence the results, like for example timeouts and bids not answered for unidentified reasons. Also the buyer not being present on the publisher's buyers list or not completed campaigns PA API migration on the buyer side may affect the result. Different lifetime of a cookie and interest group also influences the results but comes from native attributes of those two environments. It was a conscious decision not to include this factor in calculations.

There are multiple reasons that influence the PA API addressable bid requests scale calculations, but are impossible or doubtful to include due to technical reasons. Since the bid debug reports are the only source for the analysis of the incoming bid requests in PA API, it is important to raise that Chrome is planning to throttle them in the future. When that happens the calculations will no longer be possible. If the size of sampling will be known some estimations may be possible, but the precision will drop.

