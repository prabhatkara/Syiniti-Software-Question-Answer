# Syiniti-Software-Question-Answer

Q1. What’s your proudest achievement? It can be a personal project or something you’ve worked on professionally. Just a short paragraph is fine, 
but I’d love to know why you’re proud of it.
Ans: - My proudest achievement is getting Bronze Apex Award from CGI Inc. This is for outstanding performance in the second quarter of 2020. In the last quarter, I had resolved 5 critical defects meeting the SLA deadlines. Client has appreciated my sincere efforts and also
received pat on the back from our client. In a short span of time, I worked proactively in various aspect of client requirements and delivered my best.  

Q2. What’s a personal project you're currently working on? This could be a coding side project, hobby, or otherwise real-world project you're working on.
Ans: - As of now I am more engaged in certification program and completed 2 Microsoft certification exams by going through the in-depth concept of cloud and data fundamentals. By using those concepts, I am planning to 
crate a project of my own which will give the best practice of my knowledge and hands-on experience.

Q3. Tell us about a technical book or article you read recently, why you liked it, and why we should read it.
Ans: - Recently I have gone through an article Telecome-101.  This article is curated by the Telco to acquainted with concepts and technologies in the communications landscape. 
 This article will provide a flavor of the global Telco markets with emerging industry trends. With Telecom 101, I learn about: 
 • The history and business ecosystem of telecom 
 • Core telecom networks and networking concepts 
 • Telecom broadcasting, Wireless and Internet technologies, OSS/BSS and Telecom framework After completion, you will gain knowledge in these telecom concepts: 
 • Business Ecosystem 
 • Access and Core Networks 
 • Wireless Technologies 
 • Service Fulfilment & Assurance journeys
 • Industry & Regulatory bodies 
 • Carrier Networks & De-regulation 
 • OSS, BSS and NMS 
 • TM Forum Frameworks

Q4. Tell us about one of your favorite products (physical or software) and one specific aspect that makes it truly great.
Ans: - One of my favorite product is RBM (Rating and Billing Management). This is a product of Netcracker which is a leading Telco in the globe. Netcracker digital BSS/OSS portfolio is the optimal choice for service providers looking for a cloud-native solution that enables AI-driven, digital-first, omnichannel customer engagement. It also provides efficient monetization of new lines of business,
rich digital partner ecosystems and end-to-end service automation of hybrid and cloud services from edge to core. 

Q5. In this repo is a data.json file. It contains an imaginary example set of data a customer might need to migrate from one system to another. It's a JSON encoded array of objects. The customer understands some of the data might be bad and wants to know which records are invalid so they can ensure the new system will only have valid data. Write a program that will read in the data and mark any records:

That are a duplicate of another record
name field is null, missing, or blank
address field is null, missing, or blank
zip is null, missing, or an invalid U.S. zip code
Each record has an ID but that should only be used to identify a record, not for validity or duplication testing (e.g., two records may be identical but have different IDs).

The output of the program should list the IDs of each invalid or duplicate record, one per line. In the case of duplicates, mark both.

Program
---------
import json
f= open("data.json")
js= json.load(f) # list of dictionaries containing content of data.json file
l1=[] # list of IDs with faulty name or address or zip
for item in js:
    if len(item)<4 or item["name"] in [None, ''] or item["address"] in [None, ''] or item["zip"] in [None, ''] or item["zip"].isdecimal() is False:
            l1.append(item["id"])
            print(item["id"])
l2=[] #list of duplicate records
for i in range(0,len(js)):
    if js[i]["id"] not in l1:
        l2.append(js[i]["name"]+js[i]["address"]+js[i]["zip"]+":"+str(i))

l3=[i.split(":")[0] for i in l2]
l4=[]
for i in range(0,len(l3)):
    if l3.count(l3[i])>1:
        l4.append(i)
for index in l4:
    print(js[int(l2[index].split(":")[1])]["id"])

f.close() 
