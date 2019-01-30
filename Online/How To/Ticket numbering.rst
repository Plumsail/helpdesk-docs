Custom ticket numbering
#######################

You can configure unique tickets numbering. 
Just customize formula: it must contain **{{IDCounter}}** token and may contain optional **{{CurrentDate}}** token.

**IDCounter** is an instance-wide ticket counter. 

**CurrentDate** is current date/time.

You can use different formats to show only part of current date/time. 
For example, **{{CurrentDate:HH-mm}}** will show only hours and minutes in 24h format. 

By default, the formula is **{{IDCounter}}**, so tickets are numbered as "1", "2" etc. 

For example, you can change it to **IT {{IDCounter}} {{CurrentDate:HH-mm}}**.
In this case new tickets will be numbered as "IT 3 12-35", "IT 4 14-33", "IT 5 00-10" etc