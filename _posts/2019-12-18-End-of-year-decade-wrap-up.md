---
layout: post
title: Year- and Decade-End Recap
date: 18 Dec 2019
published: true
---
Well here we are. We're nearing the end of the Twenty-Tens. A decade of increasing global unrest, political polarization, climate change-related weather anomalies, CRISPR-babies, and Taylor Swift!
<br><br>
This year - 2019 - has been a great year for me. And this decade offers a lot to reflect on - within my own personal life and without. I'd like to kick off a new decade with a 'mental flush' of the events that resonated with me as defining the last 10 years. 
<br>
### Notable Events
#### 2010 <br>
-A 7.0 Mw earthquake devastates the country of Haiti, killing hundreds of thousands.<br>
-The Deepwater Horizon oil rig explodes in the Gulf of Mexico, triggering an environmental crisis.<br> 
-President Obama repeals "Don't Ask, Don't Tell".<br>

#### 2011<br>
-World population exceeds 7 billion.<br>
-Osama bin Laden killed by U.S. Special Forces in Pakistan. <br>
-Egyptian revolution begins a series of protests and revolutions in what is referred to as the "Arab Spring".<br>

#### 2012
<br>
-[CRISPR can be used for *targeted* DNA cleavage.](https://github.com/andrewrlynch/andrewrlynch.github.io/blob/master/Jinek-et-al.-2012.pdf)
-[Higgs boson is detected at CERN.](https://www.nytimes.com/2012/07/05/science/cern-physicists-may-have-discovered-higgs-boson-particle.html)<br>
-The whole Kony 2012 thing.
-The Mayan/Mesoamerican Long Count Calendar ends (21 December). Apocalypse begins. <br>

#### 2013
#### 2014
#### 2015
#### 2016
#### 2017
#### 2018
#### 2019


### For Me - Notable Dates and Milestones
<br>

### The Decade in Data
#### Climate Change
~~~
#Sea Surface Temperature Anomaly
p1 <- ggplot(df2, aes(x = Year, y = Annual.anomaly)) + 
  annotate("rect", xmin = 2010, xmax = 2020, ymin = -Inf, ymax = Inf, alpha = 0.5, fill = "orange") +
  geom_line(lwd = 1) + 
  stat_smooth(method = "gam", formula = y~s(x,bs="cs"), col = "magenta", lty = 3, col = "grey22", lwd = 1.2, fullrange = TRUE, se = TRUE) + 
  labs(x = "Year", y = "Sea Surface Temperature Anomaly (°F)") + 
  xlim(c(1958,2100)) + 
  theme_pubclean() + 
  theme(panel.border = element_rect(colour = "black", fill=NA, size=0.8),
        axis.text.x = element_text(angle = 90, hjust = 1)) + 
  scale_x_continuous(breaks = seq(1960,2100, 10), limits = c(1958,2100))
  
#Atmospheric CO2 Concentration
p2 <- ggplot(monthly_in_situ_co2_mlo, aes(x = yearmonth, y = seasonally)) + 
  annotate("rect", xmin = 2010, xmax = 2020, ymin = -Inf, ymax = Inf, alpha = 0.5, fill = "orange") + 
  geom_line(lwd = 1) + 
  stat_smooth(method = "gam", formula = y~s(x,bs="cs"), col = "magenta", lty = 3, col = "grey22", lwd = 1.2, fullrange = TRUE, se = TRUE) +
  labs(y = "Atmosphere [CO2] (ppm)", x = "Year") + 
  xlim(c(1958,2100)) + 
  ylim(c(300,650)) +
  theme_pubclean() + 
  theme(panel.border = element_rect(colour = "black", fill=NA, size=0.8),
        axis.text.x = element_text(angle = 90, hjust = 1)) + 
  scale_x_continuous(breaks = seq(1960,2100, 10), limits = c(1958,2100))

ggarrange(p1, p2)
~~~
{: .language-r}
<br>
![](/images/Climate.png)
<br>
#### Google Search Trends
![](/images/Trends.png)
