

[[_TOC_]]
##ML senarios

*here are two senario for using ML in our project

::: mermaid
 graph LR;
 A[time series data ] -->|input| B(forecasting ML algorithm) -->|output| C[predicted values];
 
style B fill:#FFFF00


:::

::: mermaid
 graph LR;
 A[data model with a empty field to predict ] -->|input| B(Fast Tree Regression) -->|output| C[predicted values];

style B fill:#FFFF00


:::
##Use Cases
::: mermaid
graph LR;
style id1 fill:#00FFFF
style xd1 fill:#00FFFF
style ad1 fill:#00FFFF

xd1[trainer]
ad1[admin]
    id1[data provider]  
id1 --> id2[import data]
id1-->id3[see it's data]
id1-->id4[select their data]
id1-->id5[filter data]
xd1-->id6[start training]
id1-->id7[see results]
id1-->id8[normalize data]
id1-->id9[export it's data]
xd1-->id10[save trained model]
id1-->id11[save data model]
id1-->id12[see the correlation for a data]
ad1-->id13[defined job]
ad1-->id14[defined robot]
xd1-->id15[assign robot to pretrained model]
ad1-->id16[assign a job to robot]
xd1-->id17[start prediction]
xd1-->id18[enter training properties]
xd1-->id19[enter prediction properties]
xd1-->id20[see last prediction info]
xd1-->id21[see list of predictions]
id1-->id22[see charts and pivots]
xd1-->id22[see charts and pivots]
xd1-->id7[see results]

:::


##Use Case Relationship Diagram

::: mermaid
 graph LR;
style xd1 fill:#00FFFF

xd1[data provider] --> xd2[see data pack list] --> xd3[see overall info] --> xd4[start new pack] --> xd6[add data with query] --> xd7[see fetched data] --> xd8[pack it's data] --> xd9[see it's chart and pivot] --> xd10[export result]
xd3--> xd5[set robot]
xd4 --> xd11[import data with excel] --> xd12[see their columns] --> xd13[select using columns] --> xd8
xd4 --> xd14[form builder]--> xd15[???ask from master???] --> xd8

xd2 --> xd16[filter packs] --> xd17[see overall info] --> xd18[select one record to see details] --> xd9
:::


::: mermaid
 graph LR;
style xd1 fill:#00FFFF

xd1[trainer] --> xd2[see pretrained model list]  --> xd3[see overall info] -->xd4[select one record to see details] --> xd5[see predicted values]
xd3 --> xd6[set robot]
xd2 --> xd7[start new training] --> xd8[select data pack] --> xd9[fill training parameters] --> xd10[start training process]
xd2 --> xd11[start prediction] --> xd12[fill prediction parameters] --> xd13[see result]
:::

::: mermaid
 graph LR;
style xd1 fill:#00FFFF

xd1[admin] --> xd2[see job list] --> xd3[defined a job]
xd2 --> xd4[filter jobs] --> xd5[select one record to see details]
:::

::: mermaid
 graph LR;
style xd1 fill:#00FFFF

xd1[admin] --> xd2[see robot list] --> xd3[defined a robot] --> xd6[assign a job to robot]
xd2 --> xd4[filter robots] --> xd5[select one record to see details]
:::


