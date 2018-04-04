# <Coursera-Exploratory Data Analysis> Peer-graded Assignment: Course Project 1

## plot1 ##
#1 Loading the data & convert the variables
mydata<-read.table('household_power_consumption.txt',skip=1, sep=';')
colnames(mydata)<-c('date','time','global_active_power','global_reactive_power','voltage','global_intensity', 'sub_metering_1','sub_metering_2','sub_metering_3')

#2 choose the part of data
mydata<-subset(mydata, date=='1/2/2007'|date=='2/2/2007')
attach(mydata)

#3 histogram
hist(as.numeric(as.character(global_active_power)), xlab='Global Active Power(kilowatts)',main='Global Active Power',col='red')

#4 copy and save the image
dev.copy(png,file='plot1.png', width=480, height=480)
dev.off()
