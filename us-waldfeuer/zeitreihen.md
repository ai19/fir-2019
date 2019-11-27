# Anzahl Brände in Kalifornien pro Monat

```
select fire_year, 
       date(discovery_date) as datum, 
       strftime('%m', date(discovery_date)) as monat, 
       state, 
       count(*) as anzahl_feuer 
       FROM fires 
       WHERE state="CA" 
       GROUP BY fire_year, monat, state order by datum;
       
 ```
 
 
