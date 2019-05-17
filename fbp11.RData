 #input data
 data<- `2005_2006_flights`
 
 #plot
 library(ggplot2)
 qplot(data,count,data=data)
 View(data)
 summary(data)
 
 #missing data, log transform
 data$count[data$count=0]<-NA
 ds<-data$date
 y<-log(data$count)
 df<-data.frame(ds,y)
 qplot(ds,y,data=df)
 
 #forecast
 library(prophet)
 m<-prophet(df)
 
 #predict
 future<-make_future_dataframe(m,periods=365)
 tail(future)
 forecast<-predict(m,future)
 tail(forecast)
