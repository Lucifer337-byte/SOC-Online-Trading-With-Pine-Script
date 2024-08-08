# SOC-Online-Trading-With-Pine-Script
### STATEGY 1; 1. Moving Average Crossover Strategy

//@version=5
indicator("Moving Average Crossover")
fastLength = input.int(50, minval=1)
slowLength = input.int(200, minval=1)

price = close

fastMA = ta.sma(price, fastLength)
slowMA = ta.sma(price, slowLength)

crossover = ta.crossover(fastMA, slowMA)
crossunder = ta.crossunder(fastMA, slowMA)

plotshape(crossover, style=shape.circle, location=location.top, color=color.green)
plotshape(crossunder, style=shape.circle, location=location.bottom, color=color.red)
