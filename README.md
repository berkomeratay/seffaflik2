# EPİAŞ Transparency Platform 2.0 Python Library

This library enables users to get data from EPİAŞ's Transparency Platform by using simple python functions.

Please note that this is not an official release, and the accuracy or reliability of the data retrieved through this library cannot be guaranteed. Users are advised to exercise caution and verify the data independently before making any decisions based on it. 

The author(s) of this library shall not be held responsible for any inaccuracies or damages resulting from the use of the data.

Date input formats should be such as: "YYYY-MM-DD". An example would be : "2024-05-29"

All the functions returns a pandas dataframe, except epias_tgt function which returns a string.

## Currently few selected datasets are available, which are:

### TGT

epias_tgt(e_mail,psw): Function that returns "TGT" key to access EPİAŞ Transperancy Platform's API. Valid for 8 hours once acquired.

### Day-ahead-market
epias_mcp(start_date,end_date,tgt,e_mail,psw): Function that returns the MCP for a given interval

epias_pi_offer(start_date,end_date,tgt,e_mail,psw):  Function that turns the amount of price independent offers in day-ahead-market for a given interval

epias_pi_bid(start_date,end_date,tgt,e_mail,psw):  Function that turns the amount of price independent bids in day-ahead-market for a given interval

epias_spot(start_date,end_date,tgt,e_mail,psw): Function that turns the amount of matched amount in day-ahead-market for a given interval

epias_ba_offers(start_date,end_date,tgt,e_mail,psw):  Function that turns the amount of block offers (matched and non-matched) of day-ahead-market for a given interval

epias_ba_bids(start_date,end_date,tgt,e_mail,psw):  Function that turns the amount of block bids (matched and non-matched) of day-ahead-market for a given interval


### Generation

epias_kgup(start_date,end_date,tgt,e_mail,psw): Function that returns the DPP's (KGUP) based on resources for a given interval

epias_plant_kgup(start_date,end_date,pl_id,o_id,tgt,e_mail,psw): Function that returns the DPP's (KGUP) based on resources for a given interval (org_id: Organization ID, pl_id: Plant ID) Organization IDs can be obtained via epias_org function Plant IDs can be obtained via  epias_uevcb function

epias_org(start_date,end_date,tgt,e_mail,psw): Function that returns the organizations for a given interval

epias_uevcb(start_date,end_date,o_id,tgt,e_mail,psw): Function that returns the UEVCB data for a given interval (o_id: Organization ID)

### Consumption

epias_demand(start_date,end_date,tgt,e_mail,psw): Function that returns the real time electricity consumption for a given interval

### Intraday market

epias_idmp(start_date,end_date,tgt,e_mail,psw): Function that returns the intraday weighted average prices for a given interval

epias_idma(start_date,end_date,tgt,e_mail,psw): Function that returns the trade amount at intraday market for a given interval 

### Balancing Power Market

epias_smp(start_date,end_date,tgt,e_mail,psw): Function that returns the System Marginal Price for a given interval 

epias_yal(start_date,end_date,tgt,e_mail,psw): Function that returns the amount of load orders (YAL) for a given interval 

epias_yat(start_date,end_date,tgt,e_mail,psw): Function that returns the amount of deload orders (YAT) for a given interval

### Ancillary Services

epias_sfc(start_date,end_date,tgt,e_mail,psw): Function that returns the SFC prices for a given interval

epias_pfc(start_date,end_date,tgt,e_mail,psw): Function that returns the PFC prices for a given interval





#### Example

```python
import seffaflik2 as sf
myMail = "myMail@email.com"
myPsw = "MyPsW384@*6459"
myTGT = sf.epias_tgt(myMail,myPsw)
day_ahead_prices = sf.epias_mcp("2024-01-15","2024-03-16",myTGT,myMail,myPsw)

print(day_ahead_prices)
```


