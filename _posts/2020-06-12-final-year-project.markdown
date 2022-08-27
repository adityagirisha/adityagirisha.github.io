---
layout: post
title:  'Final Year Project: Preventing DDOS attacks using SDNs'
description:
date:   2020-06-12 18:05:55 +0300
image:  '/images/ddos.png'
tags:   [research, cybersecurity, networks]
---
> Introduction

DDoS attacks are an attack strategy aimed at hindering functionality of the service provided by the network by targeting it with overwhelming amounts of network traffic and denying it’s usage by genuine users.

> Our Approach: SDNs

Software-defined networking (SDN) is a new network architecture that has been proven to enhance network performance and reliability. 
SDN based networks promote logically centralized control of network switches and routers in an SDN environment by separating network behaviour and network functionality.

We deployed an ML Algorithm to our SDN controllers which was trained on the infamous FOI dataset to detect anamolies in packet signatures (comprised of packet length, port used, content, etc). 

On detecting such repeated packets from a particular source the ML classifier would trigger a mechanism that would slowly block all incoming packets/ reroute them to a honey pot and forward it to all lookup tables and SDN routers.

![Picture]({{site.baseurl}}/images/sdn.png)

> Results

The results were an astounding success and the simulated DDOS attack was not affecting the server performance in the slightest as all malicious traffic was being redirected or banned from crossing the network to its target

> Credits

Our Guidess : Dr H.B Prasad and Prof. Suganthi

My Teammates : Abhimanyu Roy and Abhilash Jaysheel


