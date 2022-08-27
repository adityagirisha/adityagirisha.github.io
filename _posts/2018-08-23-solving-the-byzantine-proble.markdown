---
layout: post
title:  'Research Project: Solving the Byzantine Problem' 
date:   2019-08-23 15:01:35 +0300
image:  '/images/byzantine.jpg'
tags:   [research, byzantine problem, networks]
---

> Introduction

Byzantine Failure, The term takes its name from an allegory, the "Byzantine generals problem". In its simplest form, a number of generals are attacking a fortress and must decide as a group only whether to attack or retreat. Some generals may prefer to attack, while others prefer to retreat. 

The important thing is that all generals agree on a common decision, for a halfhearted attack by a few generals would become a rout, and would be worse than either a coordinated attack or a coordinated retreat.

The problem traslates to modern day computer networks where a certain piece of code is executed parallelly across multiple systems (lets say three for example). If Node A says 1+1=2 and Node B and C say that 1+1=3 there isnt a reconcilliation in results among the nodes.

We cant say with certainity if node A is wrong or node B and C are wrong unless we calculate the result ourselves. The descrepancy in results can be from various sources from sporadic failure to bad actors. Our mission was to find a way into detecting these anamolies in calculations.

> Our Approach: Memory Heat Maps

We introduce Memory Heat Map to characterize the memory behavior of the operating system. Using the data we collected from our nodes our ML algorithm automaticall detect deviations from the normal memory behavior patterns. This provides an insight into who is the performing an incorrect calculation

![Picture]({{site.baseurl}}/images/heat_map.png)

A blockchain was deployed on the private network, and performs the functions of storing memory maps across all nodes in the system without being tamperied. It is important to note that it is just used for the functionality of distributed ledger to securely store the heat maps (no monetization mechanism is performed).

A simple classification ML algorithm was deployed to find any anamolies in the calculation. If any discrepany is detected, the node is removed from the network and replaced by its backup, where the process continues again.

> Outcome

This project was a tru eye opener into OS memory behaviour and also let us play around with complex networks, distributed ledgers, Machine Learning. We concluded with a POC network on the cloud with the aforementioned scenario and successfully detect faulty systems.

> Credits

Our Guide : Dr H.B Prasad

My Teammates : Animesh ND and Abhilash Jaysheel