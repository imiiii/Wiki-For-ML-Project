

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

:::

