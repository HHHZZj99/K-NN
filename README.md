# K-NN
> age<-c(69,66,49,49,58,44)
> income<-c(3,57,79,17,26,71)
> credit<-c(low,low,low,low,high,high)
错误: 找不到对象'low'
> credit<-c("low","low","low","low","high","high")
> data<-data.frame(age,income,credit)
> head(data)
  age income credit
1  69      3    low
2  66     57    low
3  49     79    low
4  49     17    low
5  58     26   high
6  44     71   high

> n.point<-1000#number of rows in the dataset
> sampling.rate<-0.8
> num.test.set.labels<-n.points*(1-sampling.rate)#the misclassification rate
> training<-sample(1:n.points,sampling.rate*n.points,replace=FALSE)#randomly sample which row will go in the training set
> train<-subset(data[training,],select=c(age,income))#define the training set to be those rows
> 
> testing<-setdiff(1:n.points,training)#the other rows are going to the test set
> test<-subset(data[taining,],select=c(age,income))#define the test set to be the other rows
Error in `[.data.frame`(data, taining, ) : 找不到对象'taining'
> test<-subset(data[training,],select=c(age,income))#define the test set to be the other rows
> cl<-data$credit[training]#this is the subset of labels for the training set
> true.labels<-data$credit[testing]#subset of labels for testing
>
