# Using-a-third-variable-to-label-a-scatterplot
### USING A THIRD VARIABLE TO LABEL A SCATTERPLOT 

data<- read.table("pgr.txt", header = TRUE)
View(data)
attach(data)
names(data)

plot(hay, pH, main = "Scatterplot of Hay versus Soil pH ", pch = 20 ,col = rainbow(8), 
     xlab = "Total Hay", ylab = "Soil pH")

text(hay, pH, labels = round(FR, 1), pos = 1, offset = 0.5, cex = 0.7)


median(data$FR)

plot(hay, pH, pch = 20, col = ifelse(FR > median(FR), "green", "black"), 
     main = "Scatterplot of Hay versus Soil pH ")
legend(locator(1), c("FR > median" , "FR = median"), pch = 20, col = c("green", "black"))
