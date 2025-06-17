#Code
In this folder we are going to put the whole code of the course.
> The code in this folder has been developed by the whole audience.
> # DATA VISUALISATION

# Code for remote sensing data handling and analysis

install.packages("devtools")
library(devtools)
install_github("ducciorocchini/imageRy")

library(terra)
library(imageRy)

# Listing data inside imageRy
im.list()

# without imagery
b2 <- rast("F:/2025/spatial_data_course/sentinel.dolomites.b2.tif")
plot(b2)

cl <- colorRampPalette(c("black", "grey", "light grey")) (100)
plot(b2, col=cl)

b3 <- rast("F:/2025/spatial_data_course/sentinel.dolomites.b3.tif")
plot(b3)


b4 <- rast("F:/2025/spatial_data_course/sentinel.dolomites.b4.tif")
plot(b4)

b8 <- rast("F:/2025/spatial_data_course/sentinel.dolomites.b8.tif")
plot(b8)

par(mfrow=c(1,4))
plot(b2)
plot(b3)
plot(b4)
plot(b8)

par(mfrow=c(2,2))
plot(b2)
plot(b3)
plot(b4)
plot(b8)


sent <- c(b2, b3, b4, b8)
plot(sent)

library(viridis)
plot(sent, col=magma(100))


# b2= blue -1
# b3 = green -2
# b4 = red -3
# b8 = NIR -4 

#borrar la gráfica
dev.off()
plotRGB(sent,r=3, g=2, b=1, stretch="lin")

plotRGB(sent,r=4, g=3, b=2, stretch="lin")


plotRGB(sent,r=3, g=4, b=2, stretch="lin")

plotRGB(sent,r=3, g=2, b=4, stretch="lin")

#pairs()


# deforestation with bare soil created in time

pairs(sent)
