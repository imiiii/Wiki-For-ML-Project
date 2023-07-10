

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
    id1[user]  
id1 --> id2[import data]
id1-->id3[see it's data]
id1-->id4[select their data]
id1-->id5[filter data]
id1-->id6[start training]
id1-->id7[see results]
id1-->id8[normalize data]
id1-->id9[export it's data]
id1-->id10[save trained model]
id1-->id11[save data model]
id1-->id12[see the correlation for a data]
id1-->id13[defined job]
id1-->id14[defined robot]
id1-->id15[assign robot to pretrained model]
id1-->id16[assign a job to robot]
id1-->id17[start prediction]
id1-->id18[enter training properties]
id1-->id19[enter prediction properties]
id1-->id20[see last prediction info]
id1-->id21[see list of predictions]
id1-->id22[see charts and pivots]

:::

