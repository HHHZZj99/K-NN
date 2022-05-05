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
> num.test.set.labels<-n.points*(1-sampling.rate) 
> #the misclassification rate
> training<-sample(1:n.points,sampling.rate*n.points,replace=FALSE)
> #randomly sample which row will go in the training set
> train<-subset(data[training,],select=c(age,income))#define the training set to be those rows
> 
> testing<-setdiff(1:n.points,training)#the other rows are going to the test set
> test<-subset(data[training,],select=c(age,income))#define the test set to be the other rows
> cl<-data$credit[training]#this is the subset of labels for the training set
> true.labels<-data$credit[testing]#subset of labels for testing
>


#loop through and see what the misclassification rate is fr different values of k
for(k in 1:20){
print(k)
predicted.labels<-knn(train,test,cl,k)
num.incorrect.labels<-sum(predicted.labels!=true.labels)
misclassification.rate<-num.incorrect.labeld/num.test.set.labels
print(misclassification.rate)
}


output:
k     misclassification
1     0.28
2     0.315
3     0.26
4     0.255
5     0.23
6     0.26
7     0.25
8     0.25
9     0.235
10    0.24

#chose the smallest mmisclassification that is when k=5,apply to sb 57 with 37000$ salary
test<-c(57,37)
knn(train,test,cl,k=5)
output: low


#assumptions
distance
training data was labeled or classified
pick k number
add more features and check how that aters evaluation metric-- tunning feature and k(in case of overfittng)






