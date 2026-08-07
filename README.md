<a href="https://www.linkedin.com/in/nivi-I/"><img width="60" height="60" alt="image" src="https://github.com/user-attachments/assets/2a8859b9-ac1c-411d-adea-71a05a184ff4" /></a>
 

**FIFA 2026 Worldcup Football Data Analytics Dashboard**
<img width="1162" height="652" alt="FIFA Dashboard" src="https://github.com/user-attachments/assets/628c9a19-fc0d-46d3-a4e2-4aad2f8d0500" />
Cleaning Steps Used

No cleaning required

Meaure added for Goal Type

Goal Type = IF(goalscorers[own_goal] = True(), "Own Goal", IF(goalscorers[penalty] = True(), "Penalty", "Normal Goal"))



**Telecom Churn Analytics Dashboard**
<img width="1052" height="587" alt="image" src="https://github.com/user-attachments/assets/1b26b4b2-dda3-4047-a368-cf68f3df26fd" />

Cleaning Steps Used
No cleaning required

**Solar Generation Analysis**
<img width="1162" height="652" alt="Solar Generation Dashboard" src="https://github.com/user-attachments/assets/026e0995-d5c7-4f1a-a974-9a3dfea44e21" />

Cleaning Steps Used

No Cleaning required


**Netflix User Data Analytics Dashboard**
<img width="1157" height="652" alt="Netflix Dashboard" src="https://github.com/user-attachments/assets/e4e6fdfd-f33d-45b0-8f07-9f6eebef6067" />

Cleaning Steps Used
No cleaning required

**Global Ad Performance Analytics Dashboard**
<img width="1128" height="635" alt="Global Ad performance dashboard" src="https://github.com/user-attachments/assets/516e47f0-4221-4cbd-b70e-cb55b267fc3e" />


Cleaning Steps Used
No Cleaning required

**Indian Tourism Analytics Dashboard**
<img width="1295" height="731" alt="Indian Tourism Dashboard" src="https://github.com/user-attachments/assets/8283dff4-b777-4154-a037-51b21fa4febb" />

Cleaning Steps used
No cleaning required

Measure Added
Popular Attraction Count = CALCULATE(COUNT('Top Indian Places to Visit'[Name]),'Top Indian Places to Visit'[Google review rating] >= 4.5)


**Iran Geopolitical risk & Global Oil Market Analysis**
<img width="1317" height="737" alt="Iran Geopolitical Dashboard" src="https://github.com/user-attachments/assets/bb522d47-98a7-43fe-9dc7-148a81ca5461" />

Cleaning Steps used

No cleaning required

Added New Table

DateTable = CALENDAR(MIN(oil_prices_daily[date]),MAX(oil_prices_daily[date]))


**Forbes Companies Analytics Dashboard**
<img width="1181" height="672" alt="Forbes Global Companies Dashboard" src="https://github.com/user-attachments/assets/53a5e1db-6c4d-430c-8cdc-0dfaee6162d7" />

cleaning steps used

No cleaning required

**Next Generation Mobile Network Analysis**
<img width="1281" height="717" alt="Next Generation Network Analysis Dashboard" src="https://github.com/user-attachments/assets/e3825196-9082-4958-a015-a322ce990841" />

Cleaning Steps Used

No Cleaning required

Added New Combined Table

Combined Network = UNION(SELECTCOLUMNS('Signal Metrics 3g',"Network", "3G", "Speed",'Signal Metrics 3g'[Data Throughput (Mbps)],"Latency",'Signal Metrics 3g'[Latency (ms)], "Signal Strength", 'Signal Metrics 3g'[Signal Strength (dBm)], "Range", Blank()), SELECTCOLUMNS('march18_myspeed', "Network", "4G", "Speed", 'march18_myspeed'[Data Speed (Mbps)], "Latency", BLANK(), "Signal Strength", 'march18_myspeed'[Signal Strength (dBm)], "Range", BLANK()), SELECTCOLUMNS('5g_network_data', "Network", "5G", "Speed", '5g_network_data'[Download Speed (Mbps)], "Latency", '5g_network_data'[Latency (ms)], "Signal Strength", '5g_network_data'[Signal Strength (dBm)], "Range", BLANK()), SELECTCOLUMNS('6G_Prediction', "Network", "6G", "Speed", '6G_Prediction'[Download Speed(Mbps)], "Latency", '6G_Prediction'[Latency(ms)], "Signal Strength", BLANK(), "Range", '6G_Prediction'[Range(km)])) 

Added New 6G Prediction Table

6G_Prediction = ROW("Network", "6G", "Latency(ms)", (AVERAGE('Signal Metrics 3g'[Latency (ms)]) + AVERAGE ('5g_network_data'[Latency (ms)])) / 2 * 0.1, "Download Speed(Mbps)", (AVERAGE('Signal Metrics 3g'[Data Throughput (Mbps)]) + AVERAGE('march18_myspeed'[Data Speed (Mbps)]) + AVERAGE('5g_network_data'[Download Speed (Mbps)])) / 3 * 10, "Upload Speed (Mbps)", AVERAGE('5g_network_data'[Upload Speed (Mbps)]) * 10, "Throughput(Mbps)", (AVERAGE('Signal Metrics 3g'[Data Throughput (Mbps)]) + AVERAGE('5g_network_data'[Download Speed (Mbps)]) + AVERAGE(march18_myspeed[Data Speed (Mbps)])) / 3 * 12, "Signal Quality (%)", AVERAGE('Signal Metrics 3g'[Signal Quality (%)]) * 1.05, "Range(km)", 5)


**Network Traffic Analysis**
<img width="1222" height="690" alt="Network traffic Performance Dashboard" src="https://github.com/user-attachments/assets/42c4e5d5-dce6-4633-ac14-392faa97562e" />

Cleaning Steps used 

No cleaning required

Added Measures and Table

CalendarTable = CALENDARAUTO()

3-Period Rolling Throughput = 
VAR CurrentTimestamp = MAX('network_traffic_clean'[Timestamp])
VAR WindowStart = CurrentTimestamp - TIME(0, 45, 0)
RETURN
    CALCULATE(
        AVERAGE('network_traffic_clean'[Throughput_Mbps]),
        REMOVEFILTERS('CalendarTable'),
        'network_traffic_clean'[Timestamp] > WindowStart &&
        'network_traffic_clean'[Timestamp] <= CurrentTimestamp
    )

Critical Signal Drop Rate % = 
DIVIDE(
    CALCULATE(COUNTROWS('network_traffic_clean'), 'network_traffic_clean'[Packet_Loss_Rate] > 10),
    [Total Packet Streams],
    0
)

Total Packet Streams = COUNTROWS('network_traffic_clean')

**Banking Performance Analysis**
<img width="1145" height="643" alt="Banking Performance Analysis" src="https://github.com/user-attachments/assets/274641e3-4ce2-49cc-a8aa-0bd0b6d53169" />

Cleaning Steps used 

No cleaning required









