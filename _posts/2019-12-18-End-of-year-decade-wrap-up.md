---
layout: post
title: Year- and Decade-End Recap
date: 18 Dec 2019
---
Well here we are. We're nearing the end of the Twenty-Teens. A decade of increasing global unrest, political polarization, climate change-related weather anomalies, CRISPR-babies, and Taylor Swift!
<br>
This year - 2019 - has been a great year for me. And this decade offers a lot to reflect on - within my own personal life and without.
<br>
###Notable Events

<br>


###Notable Dates and Milestones
<br>

###The Decade in Data
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
![]({{site.baseurl}}/https://github.com/andrewrlynch/andrewrlynch.github.io/blob/master/images/Climate.png?raw=true)
