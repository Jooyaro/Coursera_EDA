# <Coursera-Exploratory Data Analysis> Peer-graded Assignment: Course Project 1

## plot1 ##
#1 Loading the data & Converting the variables
mydata<-read.table('household_power_consumption.txt',skip=1, sep=';')
colnames(mydata)<-c('Date','Time','Global_active_power','Global_reactive_power','Voltage','Global_intensity', 'Sub_metering_1','Sub_metering_2','Sub_metering_3')

#2 Choose the part of data
mydata<-subset(mydata, date=='1/2/2007'|date=='2/2/2007')
attach(mydata)

#3 Plotting
hist(as.numeric(as.character(Global_active_power)), xlab='Global Active Power(kilowatts)',main='Global Active Power',col='red')

#4 Copy and save the image
dev.copy(png,file='plot1.png', width=480, height=480)
dev.off()


## plot2 ##
#1 Loading the data & Converting the variables
mydata<-read.table('household_power_consumption.txt',skip=1,sep=';')
colnames(mydata)<-c('Date','Time','Global_active_power','Global_reactive_power','Voltage','Global_intensity', 'Sub_metering_1','Sub_metering_2','Sub_metering_3')

#2 Choose the part of data
mydata2<-subset(mydata, Date=='1/2/2007'|Date=='2/2/2007')
attach(mydata2)
date<-strptime(paste(Date, Time, sep=" "), "%d/%m/%Y %H:%M:%S")

#3 Plotting
plot(date, as.numeric(as.character(Global_active_power, type="l", xlab="", ylab="Global Active Power (kilowatts)"))

#4 Save the plot in a PNG File
dev.copy(png,file="plot2.png",width=480,height=480)
dev.off() 


## plot3 ##
#1 Loading the data & Converting the variables
mydata<-read.table('household_power_consumption.txt',skip=1,sep=';')
colnames(mydata)<-c('Date','Time','Global_active_power','Global_reactive_power','Voltage','Global_intensity', 'Sub_metering_1','Sub_metering_2','Sub_metering_3')

#2 Choose the part of data
mydata2<-subset(mydata, Date=='1/2/2007'|Date=='2/2/2007')
attach(mydata2)
date<-strptime(paste(Date, Time, sep=" "), "%d/%m/%Y %H:%M:%S")

#3 Plotting & Saving
png('plot3.png',width=480, height = 480)
plot(date,as.numeric(as.character(Sub_metering_1)),type='l',xlab='',ylab='Energy sub metering')
lines(date,as.numeric(as.character(Sub_metering_2)),type='l',col='red')
lines(date,as.numeric(as.character(Sub_metering_3)),type='l',col='blue')
legend('topright',legend=c('Sub_metering_1','Sub_metering_2','Sub_metering_3'),lty=1, lwd=2.5, col=c('black','red','blue'))
dev.off()


## plot4 ##
#1 Loading the data & Converting the variables
mydata<-read.table('household_power_consumption.txt',skip=1,sep=';')
colnames(mydata)<-c('Date','Time','Global_active_power','Global_reactive_power','Voltage','Global_intensity', 'Sub_metering_1','Sub_metering_2','Sub_metering_3')

#2 Choose the part of data
mydata2<-subset(mydata, Date=='1/2/2007'|Date=='2/2/2007')
attach(mydata2)
date<-strptime(paste(Date, Time, sep=" "), "%d/%m/%Y %H:%M:%S")

#3 Plotting & Saving
png('plot4.png',width=480,height=480)
par(mfrow=c(2,2))
plot(date, as.numeric(as.character(Global_active_power)), type="l", xlab="", ylab="Global Active Power (kilowatts)")
plot(date, as.numeric(as.character(Voltage)), type="l", xlab="datetime", ylab="Voltage")
plot(date,as.numeric(as.character(Sub_metering_1)),type='l',xlab='',ylab='Energy sub metering')
lines(date,as.numeric(as.character(Sub_metering_2)),type='l',col='red')
lines(date,as.numeric(as.character(Sub_metering_3)),type='l',col='blue')
legend('topright',legend=c('Sub_metering_1','Sub_metering_2','Sub_metering_3'),lty=1, lwd=2.5, col=c('black','red','blue'))
plot(date,as.numeric(as.character(Global_reactive_power)),type='l',xlab='datetime',ylab='Global_reactive_power')
dev.off()
