---
title: 日本国民の年代別身長/体重情報
---

<Details title='このデータについて'>
  このデータはe-Statより取得したデータを可視化しています
</Details>


<Dropdown 
  data={data_label} 
  name=MeasurementItem 
  value=MeasurementItem
  defaultValue ="身長(cm)"
   
/>

<LineChart 
    data={human_data}
    x=AgeType
    y=Value 
    yAxisTitle="Length (cm)"
    series=Gender
    sort=AgeType
/>


```sql data_label
select MeasurementItem
from estat_root.e0003289205
group by MeasurementItem
```


```sql human_data
select *
from estat_root.e0003289205
where MeasurementItem like '${inputs.MeasurementItem.value}'
```