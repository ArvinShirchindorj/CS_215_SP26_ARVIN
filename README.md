## Week 10 Update

For my final project, I have decided to work on my own. My project topic is air pollution in Ulaanbaatar, Mongolia. I chose this topic because it is personally meaningful to me, and I also think it can be an interesting topic to do analysis on. It is a topic where I can look at trends over time, compare places, combine datasets, and ask interesting questions.

The main dataset I am considering is PM2.5 air quality data for Ulaanbaatar. I want to use PM2.5 as my main indicator of air pollution because it is a common and important measurement of air quality. One advantage of using this dataset is that it directly matches my topic and should give me enough data to look at seasonal and yearly patterns. One possible downside is that the data may have missing values or different monitoring locations, so I may need to spend time cleaning it.

I am also considering using weather data for Ulaanbaatar, especially temperature, precipitation, and possibly wind. This would make the project stronger because it would let me look at factors that may be associated with air pollution levels instead of only describing the pollution itself. The advantage is that I could merge the weather data with the air quality data by date and look for patterns. The downside is that combining datasets may be harder if the date formats or time ranges do not match well.

Another possible data source is PM2.5 data from a small number of other capital cities. I think this would help me compare Ulaanbaatar to other places and see whether it stands out. The advantage is that it would add more depth to the project. The disadvantage is that city comparisons may not be perfectly fair if the cities have different monitoring systems or different years of available data.

Right now, the main questions I want to explore are:
1. How does PM2.5 in Ulaanbaatar change by month, season, and year?
2. Are certain weather conditions associated with worse PM2.5 levels in Ulaanbaatar?
3. How does Ulaanbaatar compare to some other capital cities?
4. How often does Ulaanbaatar experience especially bad pollution days or periods?

-----

## Week 11 Update
Moving forward with air pollution in Ulaanbaatar, Mongolia as my final project topic, my main goal this week was to stop just brainstorming and actually start working with the data, figuring out which sources were realistic, and building a process for collecting and cleaning it. After a long process of looking for an appropriate data, I was able to find the right sources.

The main data source I decided to use is OpenAQ for air quality data in Ulaanbaatar. I chose this source because it gives access to monitoring locations, pollutants, sensors, and measurement data. I also liked that it lets me work with multiple pollutants instead of only PM2.5. So far, I have been able to pull data for SO2, PM10, NO2, PM2.5, CO, and O3, which makes the project much stronger and gives me more to analyze. Right now, my cleaned air dataset has data from 2016 to 2019 and more than 52,000 daily rows, so it is definitely large enough for the project.

A big part of this section of the project was figuring out how to actually get the data. At first, I thought it would be simple to just search for Ulaanbaatar directly, but it ended up taking more trial and error than I expected. I spent time reading through the OpenAQ API documentation and examples to understand how their locations, sensors, and measurements are structured. That was important because I realized that I could not just stop at the location level. I first had to identify the Ulaanbaatar monitoring sites, then move to the sensor level, because the actual measurement downloads are tied to sensor IDs. That was one of the main things I had to figure out before the process started making sense.

There were also a few points where I got stuck. One problem was that my first attempts at filtering locations by country and city name did not return the Ulaanbaatar stations the way I expected. After some more checking, I switched to a coordinate-based search, and that worked much better. Another issue happened when I started the full download loop. Some requests were failing at first, even though the sensors themselves were valid. To figure that out, I tested one failed sensor separately, read the error message more carefully, and then changed the loop to be more stable by adding retries and short pauses between requests. After that, the full download worked with 0 failed sensor requests.

As I worked through this, I was also trying to keep the notebook organized as more of a data collection and cleaning notebook instead of mixing everything into one big final project notebook. So far, I have built the raw air quality dataset, cleaned the datetime and pollutant values, unpacked nested metadata, and created a few derived datasets.

There were also a few smaller places where I got stuck on the coding side, especially when I was trying to understand why certain cells were not running correctly or why some operations failed. For a few of those moments, I asked ChatGPT for guidance and advice, mainly to help me think through the process, fix errors, and debug my code. It helped me move through the most confusing part more efficiently.

The next major step is to add a supporting weather dataset for Ulaanbaatar so I can study possible relationships between pollution levels and factors like temperature, precipitation, and maybe snow-related conditions. I think that will make the project much stronger because it will let me go beyond just describing pollution trends and start exploring what conditions are associated with worse air quality. I may also later add a small comparison with a few other capital cities, but for now my main focus is getting the Ulaanbaatar air and weather data into a strong final form.
