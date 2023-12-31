

[[_TOC_]]
##Overview
AI is one of the multiple Modules used to describe the Fennec project.
::: mermaid
 graph LR;
 A[Fennec Project] --> B[Module A];
 A -->C[Module B]
 A -->D[AI Module]
style D fill:#FFFF00
:::

##About the software
This software is used to predict some values by using regression models such as forecasting algorithms and Tree-like algorithms.
Imported packages for this usage are Microsoft ML, Microsoft ML Fast Tree, and Microsoft ML Time Series, available in the NuGet package. 
##ML senarios

* here are two senario for using ML in our project

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
##Actors
* Data Provider: someone who is an expert in understanding the meaning of Data in software and can create a proper schema for the data view model, gather and combine data to the data view model as data records and import them to the database.
* Trainer: someone who has a slightly shallow knowledge of machine learning algorithms just to start a learning phase and see training results and understand them to know how well the data works with the trained model.
this role can import a record and use the pre-trained model to predict phase.   
* Admin: someone with all the roll in the system that has general knowledge about the system to define software settings.

##Use Cases
> |Data Provider | Trainer| Admin|
> |--------|--------------| -----|
> |import data | start training | defined a job|
> |see it's data|save trained model| see all jobs|
> |select their data | assign robot to pretrained model | defined a robot|
> | filter data| start prediction | see all robots|
> |see results | enter training properties | assign a job to a robot|
> | normalize data| enter prediction properties | select one record to see details |
> |export it's data | see last prediction info | filter robots|
> | save data model| see list of predictions | filter jobs |
> |see charts and pivots | see results | ---- |
> |see the correlation for a data| see charts and pivots | ---- |
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

##Database Diagram

:::mermaid
classDiagram
    Predict<|-- Train
    Train <|-- Data View 
    Data View Record<|-- Data View 
    Predict: +int Id
    Predict: +int Train Id
    Predict: +int Predicted Value

    Train: +int Id
    Train: +int Data View Id
    Train: +string Title
    Train: +string InputCol
    Train: +string OutputCol
    Train: +int SeriesLenght
    Train: +int Horizon
    Train: +datetime LatestUpdate
    Train: +int RSquared

    Data View: +int Id
    Data View: +string Data View


    Data View Record: +int Id
    Data View Record: +int Data View Id
    Data View Record: +int Data Record
    


  
:::


##Machine Learning Services
*Here is the ML service that the AI module used to work with.*
 - Data loader from database by connection string and query.
::: mermaid
 graph LR;
 A1[ConnectionString] -->|input| A2(Load From Database Service) -->|output| A3[IDataView];
A4[Query] --> |input|A2
style A2 fill:#FFFF00


:::
 - Data loader from file.
::: mermaid
 graph LR;
 A1[ML Context] -->|input| A2(Load From File Service) -->|output| A3[IDataView];
A4[Data Path] --> |input|A2
A5[Data Model] --> |input|A2
style A2 fill:#FFFF00


:::
 - Training service to return trained model.
::: mermaid
 graph LR;
 A1[ML Context] -->|input| A2(Train Service) -->|output| A3[ML Context];
A4[IDataView] --> |input|A2
A5[Input Column] --> |input|A2
A6[Output Column] --> |input|A2
A7[Series Lenght] --> |input|A2
A8[Horizon] --> |input|A2
A2--> |output| A9[Trained Model]


style A2 fill:#FFFF00


:::

 - Evaluation service to examine how the trained model works by returning evaluation metrics.
::: mermaid
 graph LR;
 A1[ML Context] -->|input| A2(Evaluation Service) -->|output| A3[Evaluation Metrics];
A4[Trained Model] --> |input|A2
A5[Test Data View] --> |input|A2
style A2 fill:#FFFF00


:::

- Save the pretrained model to the given address.
::: mermaid
 graph LR;
 A1[ML Context] -->|input| A2(Save Model Service) -->|output| A3[Trained Model zip];
A4[Model Path] --> |input|A2
A5[Trained Model] --> |input|A2
A6[IDataView] -->|input|A2

style A2 fill:#FFFF00


:::

- load the saved model from the given address and make a single prediction one it.
::: mermaid
 graph LR;
 A1[ML Context] -->|input| A2(Prediction Service) -->|output| A3[Score];
A4[Model Path] --> |input|A2
A5[DataViewModel] --> |input|A2
A6[IDataView] -->|input|A2


style A2 fill:#FFFF00


:::










