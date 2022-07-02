---
marp: true
title: "Smaller Feedback Loops with Docker"
theme: uncover
paginate: false
footer: "Smaller Feedback Loops with Docker | :earth_americas: [SeanKilleen.com](https://SeanKilleen.com) | :bird: [@sjkilleen](https://twitter.com/sjkilleen)"
class: invert
---
<!-- _footer: "" -->
![bg opacity:.4](./assets/images/ines-mills-TGs0tHMk4eg-unsplash.jpg)

# Docker For Smaller Feedback Loops

[dockerloops.seankilleen.com](https://dockerloops.seankilleen.com)

<!--
<br/>
Note to self -- you can use 'b' to blank the presentation.
<br/>
None of the images are mine! Credits in HTML.
<br/>
This is a talk about training your brain to know when Docker might help. How to think about moving it into your state of the art

-->

---
<!-- _footer: "" -->

![bg](./assets/images/Unsplash-wOHH-NUTvVc-dog.jpg)

<!-- Image credit: https://unsplash.com/photos/wOHH-NUTvVc -->
---

# What We'll Cover

- What
- Why
- Types
- Examples

---

# Feedback Loops

- Evidence
- Context
- Consequence
- Action

---

#### Feedback Loops

# Sense &amp; Respond

---

<!-- _footer: "" -->
![bg](./assets/images/isabella-and-louisa-fischer-FrGYMDjdg4U-unsplash.jpg)

<!-- 
Image credit: https://unsplash.com/photos/FrGYMDjdg4U
<br/><br/>
From https://www.radarsign.com/how-effective-are-radar-speed-signs/
<br/><br/>
A pedestrian hit by a car at 40 mph has a 90% fatality rate; at 20 mph the fatality rate decreases to 10%. As you can see in the graph below, just a small reduction in speed has a dramatic effect on whether those involved live or die.
<br/><br/>
"Studies repeatedly show that when alerted by a radar sign, speeders WILL slow down up to 80% of the time. Typical average speed reductions are 10-20%, and overall compliance with the posted speed limit will increase by 30-60%."
-->

---

![bg](./assets/images/rinson-chory-aJgw1jeJcEY-unsplash.jpg)

---

<video src="./assets/images/loops.mp4" autoplay="true"/>

<!-- 
Image credit: https://twitter.com/johncutlefish/status/1391934227055190019
<br/>
Premise of Agile: Smaller loops with customer
<br/>
Premise of DevOps: Smaller loops between dev and ops
<br/>
Smaller Loops == Each of these examples are less expensive
-->

---

#### The only feedback loop that matters

# The Value Stream

<!-- 
Expensive: Waiting for Servers
<br/>
Expensive: Hanging off to other teams
<br/>
Better: Collaborate on containers and deploy them
-->

---

#### Feedback Loops

# Story Time

<!-- 
Problem: Needed to run multiple Databases locally
<br/>
Expensive: Manually setting up DB Servers
<br/>
Better: Containers
-->

---

#### Story Time

# System Doubles

<!-- 
SQL on Linux: https://hub.docker.com/_/microsoft-mssql-server
<br/>
Emulators
-->

---

docker run --name db-sql -e 'ACCEPT_EULA=Y' -e
'SA_PASSWORD=YOUR_PASSWORD' -p 1433:1433 -v F:\DockerData\db-sql\data:/var/opt/mssql/data -v
F:\DockerData\db-sql\log:/var/opt/mssql/log -v F:\DockerData\db-sql\secrets:/var/opt/mssql/secrets -d
mcr.microsoft.com/mssql/server:2019-latest

---

<mark>docker run --name db-sql</mark> -e 'ACCEPT_EULA=Y' -e
'SA_PASSWORD=YOUR_PASSWORD' -p 1433:1433 -v F:\DockerData\db-sql\data:/var/opt/mssql/data -v
F:\DockerData\db-sql\log:/var/opt/mssql/log -v F:\DockerData\db-sql\secrets:/var/opt/mssql/secrets -d
mcr.microsoft.com/mssql/server:2019-latest

---

docker run --name db-sql <mark>-e 'ACCEPT_EULA=Y' -e
'SA_PASSWORD=YOUR_PASSWORD'</mark> -p 1433:1433 -v F:\DockerData\db-sql\data:/var/opt/mssql/data -v
F:\DockerData\db-sql\log:/var/opt/mssql/log -v F:\DockerData\db-sql\secrets:/var/opt/mssql/secrets -d
mcr.microsoft.com/mssql/server:2019-latest

---

docker run --name db-sql -e 'ACCEPT_EULA=Y' -e
'SA_PASSWORD=YOUR_PASSWORD' <mark>-p 1433:1433</mark> -v F:\DockerData\db-sql\data:/var/opt/mssql/data -v
F:\DockerData\db-sql\log:/var/opt/mssql/log -v F:\DockerData\db-sql\secrets:/var/opt/mssql/secrets -d
mcr.microsoft.com/mssql/server:2019-latest

---

docker run --name db-sql -e 'ACCEPT_EULA=Y' -e
'SA_PASSWORD=YOUR_PASSWORD' -p 1433:1433 <mark>-v F:\DockerData\db-sql\data:/var/opt/mssql/data -v
F:\DockerData\db-sql\log:/var/opt/mssql/log -v F:\DockerData\db-sql\secrets:/var/opt/mssql/secrets</mark> -d
mcr.microsoft.com/mssql/server:2019-latest

---

docker run --name db-sql -e 'ACCEPT_EULA=Y' -e
'SA_PASSWORD=YOUR_PASSWORD' -p 1433:1433 -v F:\DockerData\db-sql\data:/var/opt/mssql/data -v
F:\DockerData\db-sql\log:/var/opt/mssql/log -v F:\DockerData\db-sql\secrets:/var/opt/mssql/secrets <mark>-d
mcr.microsoft.com/mssql/server:2019-latest</mark>

---

#### Story Time

# Development Environment

---

#### Story Time

# System Flexibility

<!-- 
Linux on Konmaripo: https://github.com/excellalabs/konmaripo/commit/9c516c56ce7d0ba8056b0dc01ae9fdc240cd5abe#diff-fefee25bf9a9dbf03d1ac8db011a6f5a4a0c33bf9d8dec4f937ac8f85b1eea65
-->

---
<!-- _footer: "" -->
![bg](./assets/images/konmaripo_change.png)

---

#### Story Time

# CI Support

<!-- GitHub Actions for NUnit Docs: https://github.com/nunit/docs/actions/workflows/build-process.yml -->

---

#### Story Time

# Experimenting

<!-- 
Matomo
<br/>
Neo4j
-->

---

![bg contain](./assets/images/youre-awesome.jpeg)

---

<style scoped>
  ul {
    padding: 0;
    list-style: none;
  }
</style>
<!-- _footer: "" -->

![bg left 60%](./assets/images/me.png)

# Thanks

- :bird: [sjkilleen](https://twitter.com/sjkilleen)
- :earth_americas: [SeanKilleen.com](https://seankilleen.com)
- :briefcase: [Excella](https://excella.com)
