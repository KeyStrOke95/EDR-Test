.. raw:: html

   <h1 align="center">

   <br class="title">
   EDR-Test
   <br>

.. raw:: html

   </h1>

#CobaltStrike #AggresorScript #EDR #MITREAttack #PurpleTeam

.. contents:: 
    :local:
    :depth: 1

=============
INTRO
=============

**Who said Cobalt Strike was meant to be use only as an offensive tool (Red Team)?**

As part of the purple team activity, I am involved in testing different EDRs solutions to evaluate their detection capabilities by emulating attacks using Techniques, Tactics, and Procedures (TTP) used by adversaries. I wanted to automate the tests, to make it easier for us as well as to make a consistent and effective comparison between the different solutions.

My first consideration was the project **Atomic Red Team** , it is a really nice project and initiative. Unfortunately, the project did not allowed me to met some of my objectives such as 

* not to use powershell
* to have better flexibility
* some custom (ninja) features

Link: https://github.com/redcanaryco/atomic-red-team

After some online search (thanks to Dr. google) to find some other (FREE) alternatives. I came to the conclusion that if I wanted to meet all my objectives, I needed to get the hand dirty. So I decided to go for my own project but what Programming Language to use ? Since at that time, I was aiming to improve my coding skills in Cobalt strike Aggressor Script (.cna) and that on top of that, it would allow me to achieve all my objectives, it was the way to go.

For those who don't know what I am talking about!

**What is Cobalt Strike ?**

Adversary Simulations and Red Team Operations are security assessments that replicate the tactics and techniques of an advanced adversary in a network. While penetration tests focus on unpatched vulnerabilities and misconfigurations, these assessments benefit security operations and incident response.

**What is Aggressor Script (.cna) ?**

Aggressor Script is a scripting language for red team operations and adversary simulations inspired by scriptable IRC clients and bots. Its purpose is two-fold. You may create long running bots that simulate virtual red team members, hacking side-by-side with you. You may also use it to extend and modify the Cobalt Strike client to your needs.

=============
Where to Start ?
=============

The answer was as simple as the MITRE ATT&CK® framework. The MITRE ATT&CK® framework, which stands for MITRE Adversarial Tactics, Techniques, and Common Knowledge (ATT&CK), is a knowledge base for modelling the behavior of a cyber adversary. 

Link: https://attack.mitre.org/

The framework was used to built the CNA scripts with the different tests, it should be noted that at the time of the writing, I have not yet implemented all the tests from the framework but only those with high interest and relevant to the objectives were prioritised in the development of the script.

=============
Menu
=============

Below is the menu where it is possible to either select for unit test or multiple tests in either the user or admin context. 


 .. image:: ./img/socks-test.png
 	:width: 650px
 	:alt: Project

The [P] flags indicates that the test makes used of proxy socks.

This is a portion of the CNA code for the menu:

 .. image:: ./img/Template-Menu.png
 	:width: 500px
	:height: 700px
 	:alt: Project


=============
Tests
=============

 .. image:: ./img/tool-header.png
 	:width: 700px
 	:alt: Project

The tests are splitted as followed: 
--------------------------
1. User Unit Test
2. Admin Unit Test
3. User All Tests
4. Admin All Tests

Tests implemented : More than 60 tests (including variant test**) - 49 Unique tests (TTPs)

** Some tests can be performed using either native windows executable or cobalt strike functions or external tools (python, C#,...).

 .. image:: ./img/vtest.png
 	:width: 600px
 	:alt: Project
	
Example of output on Cobalt Strike

 .. image:: ./img/out.png
 	:width: 1000px
 	:alt: Project
	


The screenshot below shows information about some tests (variant test) (whether proxy is used, a .NET binary, cobalt strike function, windows binary,...)

 .. image:: ./img/info2.png
 	:alt: img-broken  


Multiple Test
--------------------------

The multiple test can be either in the user or admin context. It is also possible to specify the delay between each test (eg. 5mins).

 .. code-block:: console
 
 .. image:: ./img/AllTests.png
 	:width: 400px
 	:alt: img-broken  

=============
Timeline
=============
	
This functionality is important since it can be used to match detection on the EDR console vs TTPs used duirng the test. The time the tests were performed can be use to perform this match.

 .. image:: ./img/timeline.png
 	:width: 1000px
 	:alt: img-broken  

=============
Comparing EDRs solutions
=============

Due to security concerns, I can't provide the solutions that I have tested nor the results but the project below might give you an insight. It should also be noted that the results presented by the below project is relevant at a specific point in time due to the fact that some of the EDRs detection capability evolved over time.

Project: https://attackevals.mitre-engenuity.org/enterprise/participants/?rounds=carbanak_fin7

 .. image:: ./img/EDRs.png
 	:width: 1000px
 	:alt: img-broken  

Result on comparing the EDRs solution detection capability with reference to TTPs.

Link: "https://mitre-evals.kb.europe-west1.gcp.cloud.es.io:9243/app/dashboards#/view/c2184e40-a13a-11eb-9d57-5de8e1bfb5ea?_g=(filters:!(),refreshInterval:(pause:!t,value:0),time:(from:now-15m,to:now))"

=============
Note
=============

The project EDR-Test is not published online for now but can be shared if you contribute (at least 5 tests - can include variant -> Create a pull) or for sponsor contact me on adblue2017[@]gmail[.]com

List of already implemented tests : /img/test-implemented.png
