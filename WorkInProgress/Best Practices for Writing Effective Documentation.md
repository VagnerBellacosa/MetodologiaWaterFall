| [![img](http://agilemodeling.com/images/logoAgileModeling.gif)](http://agilemodeling.com/) | Core Practices for Agile/Lean Documentation |
| ------------------------------------------------------------ | ------------------------------------------- |
|                                                              |                                             |

[Home](http://agilemodeling.com/)[Start Here](http://agilemodeling.com/essays/whereDoIStart.htm)[Core Practices](http://agilemodeling.com/essays/bestPractices.htm)[Disciplines](http://agilemodeling.com/)[Artifacts](http://agilemodeling.com/)[Resources](http://agilemodeling.com/)[Contact Me](http://ambysoft.com/contactMe.html)

 



[![img](http://ambysoft.com/ad/bannerAd.png)](http://ambysoft.com/ad/adRedirect.html)



Ideally, an [agile document](http://agilemodeling.com/essays/agileDocumentation.htm) is [just barely good enough](http://agilemodeling.com/essays/barelyGoodEnough.html), or just barely sufficient, for the situation at hand. Documentation is an important part of [agile software development](http://agilemodeling.com/essays/agileSoftwareDevelopment.htm) projects, but unlike traditionalists who often see documentation as a risk reduction strategy, agilists typically see documentation as a strategy which increases overall project risk and therefore strive to be as efficient as possible when it comes to documentation. Agilists write documentation when that's the best way to achieve the relevant goals, but there often proves to be better ways to achieve those goals than writing static documentation. This article summarizes common "[core practices](http://www.ambysoft.com/essays/bestPractices.html)" which agilists have adopted with respect to documentation.

Best practices for increasing the agility of documentation:

1. Writing
   - [Prefer executable specifications over static documents](http://www.agilemodeling.com/essays/agileDocumentationBestPractices.htm#ExecutableSpecifications)
   - [Document stable concepts, not speculative ideas](http://www.agilemodeling.com/essays/agileDocumentationBestPractices.htm#DocumentStableConcepts)
   - [Generate system documentation](http://www.agilemodeling.com/essays/agileDocumentationBestPractices.htm#GenerateSystemDocumentation)
2. Simplification
   - [Keep documentation just simple enough, but not too simple](http://www.agilemodeling.com/essays/agileDocumentationBestPractices.htm#JustSimpleEnough)
   - [Write the fewest documents with least overlap](http://www.agilemodeling.com/essays/agileDocumentationBestPractices.htm#FewestDocumentsLeastOverlap)
   - [Put the information in the most appropriate place](http://www.agilemodeling.com/essays/agileDocumentationBestPractices.htm#AppropriatePlace)
   - [Display information publicly](http://www.agilemodeling.com/essays/agileDocumentationBestPractices.htm#DisplayInformationPublicly)
3. Determining What to Document
   - [Document with a purpose](http://www.agilemodeling.com/essays/agileDocumentationBestPractices.htm#DocumentWithAPurpose)
   - [Focus on the needs of the actual customers(s) of the document](http://www.agilemodeling.com/essays/agileDocumentationBestPractices.htm#NeedsOfActualConsumers)
   - [The customer determines sufficiency](http://www.agilemodeling.com/essays/agileDocumentationBestPractices.htm#CustomerDeterminesSufficiency)
4. Determining When to Document
   - [Iterate, iterate, iterate](http://www.agilemodeling.com/essays/agileDocumentationBestPractices.htm#Iterate)
   - [Find better ways to communicate](http://www.agilemodeling.com/essays/agileDocumentationBestPractices.htm#FindBetterWaysToCommunicate)
   - [Start with models you actually keep current](http://www.agilemodeling.com/essays/agileDocumentationBestPractices.htm#StartWithCurrentModels)
   - [Update only when it hurts](http://www.agilemodeling.com/essays/agileDocumentationBestPractices.htm#UpdateOnlyWhenItHurts)
5. General
   - [Treat documentation like a requirement](http://www.agilemodeling.com/essays/agileDocumentationBestPractices.htm#TreatDocumentationLikeARequirement)
   - [Require people to justify documentation requests](http://www.agilemodeling.com/essays/agileDocumentationBestPractices.htm#JustifyDocumentationRequests)
   - [Recognize that you need some documentation](http://www.agilemodeling.com/essays/agileDocumentationBestPractices.htm#RecognizeYouNeedSomeDocumentation)
   - [Get someone with writing experience](http://www.agilemodeling.com/essays/agileDocumentationBestPractices.htm#GetSomeoneWithWritingExperience)



## 1. Best Practices for Writing Effective Documentation

The following practices will help you to improve your approach to writing documentation:

1. [Prefer executable specifications over static documents](http://www.agilemodeling.com/essays/agileDocumentationBestPractices.htm#ExecutableSpecifications)
2. [Document stable concepts, not speculative ideas](http://www.agilemodeling.com/essays/agileDocumentationBestPractices.htm#DocumentStableConcepts)
3. [Generate system documentation](http://www.agilemodeling.com/essays/agileDocumentationBestPractices.htm#GenerateSystemDocumentation)



## 1.1 Prefer Executable Specifications Over Static Documents

The majority of the information captured in traditional specification documents, such as requirements specification, architecture specifications, or design specifications, can be captured as "[executable specifications](http://agilemodeling.com/essays/executableSpecifications.htm)" in the form of tests. When you take a [Test-Driven Development (TDD)](http://agiledata.org/essays/tdd.html) approach you effectively write detailed specifications on a just-in-time (JIT) basis. With TDD you write a test, either at the customer/acceptance level or the developer level, before writing sufficient functionality to fulfill that test. The tests are used for two purposes: they specify the requirements/architecture/design and they validate your work. This is an example of the practice [Single Source Information](http://agilemodeling.com/essays/singleSourceInformation.htm).



## 1.2 Document Stable Concepts, not Speculative Ideas

As you see in [Figure 1](http://www.agilemodeling.com/essays/agileDocumentationBestPractices.htm#Figure1), the agile strategy is to defer the creation of all documents as late as possible, creating them just before you need them via a practice called "[document late](http://agilemodeling.com/essays/documentLate.htm)". For example, system overviews are best written towards the end of the development of a release because you know what you've actually built. Similarly, the majority of user and support documentation is also best written towards the end of the lifecycle. However, this doesn't mean that all documentation should be left towards the end. You might still want to take notes for these sorts of documents throughout development so that you don't lose critical information. These notes may be nothing more than point-form information as there is no need to "polish" documents until just before final delivery of them.



**Figure 1. Documentation throughout the software development lifecycle.**

![img](http://agilemodeling.com/images/lifecycleDocumentation.jpg)



By waiting to document information once it has stabilized you reduce both the cost and the risk associated with documentation. Cost is reduced because you won't waste time documenting information that changes, which in turn motivates you to update the documentation. Risk is reduced because there is significantly less chance that your existing documentation will be out of date. If you write documentation containing information which has not yet stabilized then you are at risk of having to rework the documentation once the information has changed. In other words, you do not want to invest much time documenting speculative ideas such as the requirements or design early in a project. Instead, wait until later in the lifecycle when the information has stabilized and when you know what information is actually useful to you. The implication is that your documentation effort may be a few iterations behind your software development effort.

An extreme version of this practice is to wait until you are finished and then write the documentation, the primary advantage being that you are writing about a known and stable thing (the release of the software that you just built). There are clearly several disadvantages to this approach:

- You have likely forgotten some of the reasons behind the decisions that you made, clearly a problem if this is important to you.
- You may not have the right people anymore to write the documentation because they've moved on to other projects.
- You may not have funding to do the work.
- The will to write the documentation may no longer exist.



## 1.3 Generate System Documentation

Modern software-based modeling tools can reverse-engineer existing code and present a multitude of views into it. In short, you can save significant money by generating the majority of the system documentation that you need.



## 2. Best Practices for Simplification

The following practices will help you to simplify the documentation that you write:

1. [Keep documentation just simple enough, but not too simple](http://www.agilemodeling.com/essays/agileDocumentationBestPractices.htm#JustSimpleEnough)
2. [Write the fewest documents with least overlap](http://www.agilemodeling.com/essays/agileDocumentationBestPractices.htm#FewestDocumentsLeastOverlap)
3. [Put the information in the most appropriate place](http://www.agilemodeling.com/essays/agileDocumentationBestPractices.htm#AppropriatePlace)
4. [Display information publicly](http://www.agilemodeling.com/essays/agileDocumentationBestPractices.htm#DisplayInformationPublicly)



## 2.1 Keep Documentation Just Simple Enough, but not Too Simple

| Comprehensive documentation [does not ensure project success](http://www.agilemodeling.com/essays/agileDocumentationBestPractices.htm#ProjectSuccess), in fact, it increases your chance of failure. Documentation should be concise: overviews/roadmaps are generally preferred over detailed documentation. Follow the Agile Modeling (AM) practices [Use the Simplest Tools](http://agilemodeling.com/practices.htm#UseTheSimplestTools), [Create Simple Content](http://agilemodeling.com/practices.htm#CreateSimpleContent), and [Depict Models Simply](http://agilemodeling.com/practices.htm#DepictModelsSimply) when creating documentation. The best documentation is the simplest that gets the job done. Don't create a fifty-page document when a five page one will do. Don't create a five-page document when five bullet points will do. Don't create an elaborate and intricately detailed diagram when a sketch will do. Don't repeat information found elsewhere when a reference will do. Write in point form. Document only enough to provide a useful context. Start with a document that's minimal enough for the needs of its customers then augment it as needed. To determine what is truly the minimum amount of documentation required by my customers I will actively explore how they intend to use the documentation and why they are using it that way.The basic trade-off is the "security" of having the document against your trust in its accuracy. What would you rather have, 500-page system document that is likely to have a significant number of errors in it but significant details or a 10-page, high-level overview? The large document would very likely have most of the information that you need to maintain and enhance your system, but would you trust the information contained in it? The shorter document very likely wouldn't contain the detailed information you need but it would provide a map from where you could dive into the source code, or other documents, for details. You'd be more likely to trust this document because it's shorter, worst case you could easily update or simply rewrite it if you found it to be grossly inaccurate, and because it deals with high-level concepts such as your system architecture which will change more slowly than the detailed minutiae contained in the larger document. It is important to understand that I am not saying that a larger document is automatically of lower quality than a shorter one, but I am saying that it is likely to be perceived as such until proven otherwise. | **[![Agile Documentation](http://images.amazon.com/images/P/0470856173.01.MZZZZZZZ.jpg)](http://www.amazon.com/exec/obidos/ASIN/0470856173/ambysoftinc)** |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
|                                                              |                                                              |



## 2.2 Write the Fewest Documents with Least Overlap

You should strive to [travel as light](http://agilemodeling.com/principles.htm#TravelLight) as you possibly can, writing on just enough documentation for the situation at hand which is [just barely good enough](http://agilemodeling.com/essays/barelyGoodEnough.html) to fulfill it's purpose. One way to achieve this is to build larger documents from smaller ones. For example, I once worked on a project where all documentation was written as HTML pages, with each page focusing on a single topic. Agile teams often use Wikis like this. One page described the user interface architecture for our system, a page which included a user interface flow diagram and appropriate text describing it. The table of contents pages for the system documentation and the support guide both linked to this UI architecture page. The advantage was that this information was defined in one place and one place only, so there was no opportunity for overlap.



## 2.3 Put the Information in the Most Appropriate Place

Where will somebody likely want a piece of documentation? Is that design decision best documented in the code, added as note on a diagram, or best placed in an external document? Is a specific requirement best captured as part of a use case, in a business rule specification, or as an [executable test](http://www.agilemodeling.com/essays/agileDocumentationBestPractices.htm#ExecutableSpecifications)? The answer to these sorts of question should be driven by the needs of the customer of that information, where are they most likely to need that information. It is also driven by your desire to follow the principle [Quality Work](http://agilemodeling.com/principles.htm#QualityWork) – you should strive to record the information once where it enhances your work the most (e.g. [Single Source Information](http://agilemodeling.com/essays/singleSourceInformation.htm)). You should also consider issues such as indexing, linking, and accessibility when writing documentation because you don't always know who will eventually become its customer.



## 2.4 Display Information Publicly

When [models are displayed publicly](http://agilemodeling.com/practices.htm#DisplayModelsPublicly) – on a whiteboard, corkboard, or internal web site – you are promoting transfer of information and thus communication through the application of what [Cockburn](http://www.amazon.com/exec/obidos/ASIN/0201699699/ambysoftinc) refers to as an “information radiator”. The greater the communication on your project the less need for detailed documentation because people already know what you're doing. Having said that, don't forget to indicate the status of your work so that people can put them in context – you'll treat a model that is still a draft much different than one that has been baselined for your current release of software.



## 3. Best Practices for Determining What to Document

The following practices will help you to determine what to document:

1. [Document with a purpose](http://www.agilemodeling.com/essays/agileDocumentationBestPractices.htm#DocumentWithAPurpose)
2. [Focus on the needs of the actual customers(s) of the document](http://www.agilemodeling.com/essays/agileDocumentationBestPractices.htm#NeedsOfActualConsumers)
3. [The customer determines sufficiency](http://www.agilemodeling.com/essays/agileDocumentationBestPractices.htm#CustomerDeterminesSufficiency)



## 3.1 Document with a Purpose

You should only create a document if it fulfills a clear, important, and immediate goal of your overall project efforts. Don't forget that this purpose may be short term or long term, it may directly support software development efforts or it may not. Also remember that each system has its own unique documentation needs, that one size does not fit all -- the implication is that you're not going to be able to follow a "repeatable process" and leverage the same set of documentation templates on every project, at least not if you're interested in actually being effective.



## 3.2 Focus on the Needs of the Actual Customers(s) of the Document

You want to [work closely with the audience](http://agilemodeling.com/principles.htm#ModelWithAPurpose) of the document so that you know what they actually require of it. To do this you need to identify who the potential customer(s) for your documentation are, what they believe they require, and then negotiate with them the minimal subset that they actually need. To discover what they believe they require ask them what they do, how they do it, and how they want to work with the documentation that you are to produce. By understanding the needs of your customers you will be able to deliver succinct and sufficient documentation and deliver it where they will actually need it and find it – it doesn't matter how well written a document is if nobody knows that it exists.



## 3.3 The Customer Determines Sufficiency

Years ago I worked for a large Canadian financial institution and one of their policies were that you couldn't transition a system to someone else until they were willing to accept it. They would inspect your code and supporting artifacts and if they felt the artifacts weren't up to par then you needed to improve it and try again. Sometimes you would work on improving the artifacts together, and sometimes not. This practice provided a fair and effective quality gate between developers and the customers of our work. As writer of the documentation it is your job to ensure that it has true meaning and provides value, your customer's role is to validate that you have done so.



## 4. Best Practices for Determining When to Document

The following practices will help you to determine when to document:

1. [Iterate, iterate, iterate](http://www.agilemodeling.com/essays/agileDocumentationBestPractices.htm#Iterate)
2. [Find better ways to communicate](http://www.agilemodeling.com/essays/agileDocumentationBestPractices.htm#FindBetterWaysToCommunicate)
3. [Start with models you actually keep current](http://www.agilemodeling.com/essays/agileDocumentationBestPractices.htm#StartWithCurrentModels)
4. [Update only when it hurts](http://www.agilemodeling.com/essays/agileDocumentationBestPractices.htm#UpdateOnlyWhenItHurts)



## 4.1 Iterate, Iterate, Iterate

Ideally you should create documentation throughout the entire software development lifecycle (SDLC) when it makes the most sense, albeit that's usually towards the end of the lifecycle. When you do write documentation, you should take an evolutionary (iterative and incremental) approach to its development so that you gain feedback as to its actual value. In other words, write a little bit, show it to someone, get feedback, act on that feedback, and then iterate. The best documents are written iterative, not all at once. An iterative approach enables you to home in on what the audience for your documentation actually needs.



## 4.2 Find Better Ways to Communicate

| [Highsmith](http://www.amazon.com/exec/obidos/ASIN/0932633404/ambysoftinc) believes that the primary issue with [communication](http://agilemodeling.com/essays/communication.htm) is one of understanding, not of documentation, therefore you should not overrate the value of documentation. Well-written documentation supports [organizational memory](http://en.wikipedia.org/wiki/Organizational_Memory_System) effectively, but is a poor way to communicate during a project. Your goal is to ensure that maintenance developers understand how the system works so they can evolve it over time, not to produce a mound of documentation that they may or may not use. Your goal is to ensure that your users work with your system effectively, not that they have a pretty help system available to them. Your goal is to enable your support and operations staff, not bury them with paper.Documentation supports knowledge transfer, but it is only one of several options available to you and as [Figure 2](http://www.agilemodeling.com/essays/agileDocumentationBestPractices.htm#Figure2) depicts it often isn't the best option. The implication of this diagram is that you should choose the best communication option available to you given your current situation. Documentation options, in particular "paper specifications" are your least desirable choice, not the most desirable one. Conversations with project stakeholders, having them [actively involved with development](http://agilemodeling.com/essays/activeStakeholderParticipation.htm), being available to work through any issues with them often go much further than the best documentation. Documentation becomes a better option for you the greater the distance, either physical or temporal, between the individuals who are communicating. | **[![Agile Modeling](http://ambysoft.com/artwork/covers/agileModeling.jpg)](http://www.ambysoft.com/books/agileModeling.html)** |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
|                                                              |                                                              |

**Figure 2. Comparing the effectiveness of various communication modes.**

[![img](http://agilemodeling.com/images/communicationModes.gif)](http://agilemodeling.com/essays/communication.htm)



It's important to recognize that when you specify details of how to do something and then hand the document to someone for them to follow, you effectively take all of the joy out of the activity for that person because you've done the thinking for them. What would the motivation be for an intellectual worker, such as an IT professional, to follow detailed instructions? Never forget that developers rarely trust the documentation, particularly detailed documentation because it's usually out of sync with the code, so minimize the amount of documentation that you do deliver.



## 4.3 Start With Models You Actually Keep Current

If you've chosen to keep your [UML deployment diagram](http://agilemodeling.com/artifacts/deploymentDiagram.htm), your [user interface flow diagram](http://agilemodeling.com/artifacts/uiFlowDiagram.htm), and your [physical data diagram](http://agilemodeling.com/artifacts/physicalDataModel.htm) up to date throughout development then that is a good sign that these are valuable models that you should base your documentation around. Models that weren't kept up to date likely weren't because there was little sense in doing so, so not only are they out of date they aren't of value anyway.



## 4.4 Update Only When it Hurts

In this respect documents are just like models, my recommendation is to follow the practice [Update Only When It Hurts](http://agilemodeling.com/practices.htm#UpdateOnlyWhenItHurts). Agile documents, like agile models, should be just good enough. Many times a document can be out of date and it doesn't matter very much. For example, when I wrote the first version of this article I was working with the early release of the JDK v1.3.1 yet I regularly used reference manuals for JDK 1.2.x – it's not a perfect situation but I get by without too much grief because the manuals I'm using are still good enough. Would the manuals for Java v1.0.x be sufficient? Likely not, because there has been a significant change since that release and my productivity loss would be much greater than the cost of new manuals.



## 5. General Best Practices

The following practices will generally help you to improve your documentation efforts:

1. [Treat documentation like a requirement](http://www.agilemodeling.com/essays/agileDocumentationBestPractices.htm#TreatDocumentationLikeARequirement)
2. [Require people to justify documentation requests](http://www.agilemodeling.com/essays/agileDocumentationBestPractices.htm#JustifyDocumentationRequests)
3. [Recognize that you need some documentation](http://www.agilemodeling.com/essays/agileDocumentationBestPractices.htm#RecognizeYouNeedSomeDocumentation)
4. [Get someone with writing experience](http://www.agilemodeling.com/essays/agileDocumentationBestPractices.htm#GetSomeoneWithWritingExperience)



## 5.1 Treat Documentation Like a Requirement

A common agile philosophy is to treat documentation like any other [requirement](http://agilemodeling.com/essays/agileRequirements.htm): it should be estimated , [prioritized](http://agilemodeling.com/essays/prioritizedRequirements.htm), and [put on your work item stack](http://agilemodeling.com/essays/changeManagement.htm) (see [Figure 3](http://www.agilemodeling.com/essays/agileDocumentationBestPractices.htm#Figure3)) along with all other work items that you must address. The need to write a document clearly is a requirement just like the need to write a feature. Any investment you make in documentation is investment that you could have made in new functionality, and vice versa, so someone should make a conscious decision as to how much that investment (if any), should actually be. By treating documentation as a requirement you make its creation a visible and explicit decision for your stakeholders to consider. Fundamentally, the investment in documentation is a business decision, not a technical one: you shouldn't create documentation because your process says you should but instead because your stakeholders say you should.



**Figure 3. Managing work as a prioritized stack.**

[![img](http://agilemodeling.com/images/requirementsManagement.gif)](http://agilemodeling.com/essays/changeManagement.htm)



## 5.2 Require People to Justify Documentation Requests

Does the person know what they're asking for, and why they need it, or are they asking for it because they've been told to ask for it? Are users asking for documentation because they were burned in the past by developers, or their colleagues were burned in the past, and now they ask for everything in the hopes they'll get something? Does the requester understand the trade-offs that are being made, see [What Are The Issues Associated with Documentation?](http://agilemodeling.com/essays/agileDocumentation.htm#IssuesWithDocumentation), and that documentation comes at a cost? My experience is that when you explore the documentation issue with your project stakeholders that you quickly discover they're asking for it because they don't trust you, they often don't understand the implications of what they're asking for, and they often don't know that there is an alternative (e.g. less documentation). Really good questions to ask are what they intend to use the documentation for and how they actually use the documentation. When you do that you often discover that they don't use all the documentation, that they instead just want it there as a security blanket more than anything else. There are much better way ways to address fear than writing documentation. Some important issues:

1. You should understand the total cost of ownership (TCO) for a document, and strive to [maximize stakeholder ROI](http://agilemodeling.com/principles.htm#MaximizeStakeholderInvestment) to provide the best value possible to your organization.
2. Someone must explicitly choose to make the investment in the documentation.
3. The benefit of having documentation must be greater than the cost of creating and maintaining it.
4. Ask whether you NEED the documentation, not whether you want it.

|      |      |
| ---- | ---- |
|      |      |

## 5.3 Recognize That You Need Some Documentation

Some important observations:

1. **Documentation is as much a part of the system as the source code**. In addition to working software, you'll also likely need to minimally deliver user manuals, support documentation, operations documentation, and system overview documentation.
2. **Your team's** [primary goal is to develop software](http://agilemodeling.com/principles.htm#SoftwareIsYourPrimaryGoal)**, its** [secondary goal is to enable your next effort](http://agilemodeling.com/principles.htm#EnablingTheNextEffortIsYourSecondaryGoal). Yes, building high-quality working software which meets the needs of your stakeholders is important, but ensuring that the people who come after you can maintain and enhance it, operate it, and support it is also important.
3. **Documentation still serves a purpose**. In particular, you want to capture high-level information in documentation but not details. You will still need to capture important information permanently, and sometimes regulations require certain levels of documentation (yet another [requirement](http://www.agilemodeling.com/essays/agileDocumentationBestPractices.htm#TreatDocumentationLikeARequirement)).
4. **Agilists are in fact writing documentation**. [DDJ's 2008 Modeling and Documentation survey](http://www.ambysoft.com/surveys/modelingDocumentation2008.html) found that agile teams were just as likely as traditional teams to write deliverable documentation such as user manuals, operations documentation, and so on. [Figure 4](http://www.agilemodeling.com/essays/agileDocumentationBestPractices.htm#Figure4) summarizes the results of the survey pertaining to deliverable documentation. The important thing is that this survey should help to lay waste to some of the misunderstandings that people have when it comes to agile software development and documentation.

**Figure 4. Deliverable documentation creation.**

[![img](http://www.ambysoft.com/artwork/graphs/documentationCreation.jpg)](http://www.ambysoft.com/surveys/modelingDocumentation2008.html)



## 5.4 Get Someone With Writing Experience

Technical writers bring a lot to the table when it comes time to write documentation because they know how to organize and present information effectively. Don't have access to a technical writer? Here are some strategies:

- Consider reading and following the advice presented in [UnTechnical Writing](http://www.amazon.com/exec/obidos/ASIN/0966994906/ambysoftinc) or taking a night-school course in writing fundamentals.
- Try writing documentation with a partner, just like there is significant value [pair programming ](http://pairprogramming.com/)there is similar value in “pair documenting”.
- Have shared ownership of all documentation so that multiple people will work on it.
- Purchase text-to-speech software that allows you to listen to what you've written, a great way to discover poorly written passages.



------



## Recommended Reading

| [![Choose Your WoW!](http://www.ambysoft.com/artwork/covers/chooseWoW.jpg)](https://marketplace.pmi.org/Pages/ProductDetail.aspx?GMProduct=00101623401) | This book, [Choose Your WoW! A Disciplined Agile Delivery Handbook for Optimizing Your Way of Working](https://marketplace.pmi.org/Pages/ProductDetail.aspx?GMProduct=00101623401), is an indispensable guide for agile coaches and practitioners to identify what techniques - including practices, strategies, and lifecycles - are effective in certain situations and not as effective in others. This advice is based on proven experience from hundreds of organizations facing similar situations to yours. Every team is unique and faces a unique situation, therefore they must choose and evolve a way of working (WoW) that is effective for them. [Choose Your WoW!](https://marketplace.pmi.org/Pages/ProductDetail.aspx?GMProduct=00101623401) describes how to do this effectively, whether they are just starting with agile/lean or if they're already following Scrum, Kanban, SAFe, LeSS, Nexus, or other methods. |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [![The Object Primer 3rd Edition: Agile Model Driven Development (AMDD) with UML 2](http://ambysoft.com/artwork/covers/objectPrimer.jpg)](http://www.ambysoft.com/books/theObjectPrimer.html) | [The Object Primer 3rd Edition: Agile Model Driven Development with UML 2](http://www.ambysoft.com/books/theObjectPrimer.html) is an important reference book for agile modelers, describing how to develop 35 [types of agile models](http://agilemodeling.com/artifacts) including all 13 [UML 2 diagrams](http://agilemodeling.com/essays/umlDiagrams.htm). Furthermore, this book describes the fundamental programming and testing techniques for successful agile solution delivery. The book also shows how to move from your agile models to source code, how to succeed at implementation techniques such as [refactoring](http://agiledata.org/essays/databaseRefactoring.html) and [test-driven development(TDD)](http://agiledata.org/essays/tdd.html). The Object Primer also includes a chapter overviewing the critical database development techniques ([database refactoring](http://agiledata.org/essays/databaseRefactoring.html), [object/relational mapping](http://agiledata.org/essays/mappingObjects.html), [legacy analysis](http://agiledata.org/essays/legacyDatabases.html), and database access coding) from my award-winning [Agile Database Techniques](http://www.ambysoft.com/books/agileDatabaseTechniques.html)book. |



------

[![The PMI Disciplined Agile (DA) tool kit](http://www.ambysoft.com/artwork/buttons/buttonPMIDA.jpg)](https://pmi.org/disciplined-agile) [![Agile Modeling: Practices for Scaling Agile](http://www.ambysoft.com/artwork/buttons/buttonAM.gif)](http://agilemodeling.com/) [![Agile Data: Practices for Scaling Agile](http://www.ambysoft.com/artwork/buttons/buttonAD.gif)](http://agiledata.org/) [![EnterpriseUP: Agility at Scale](http://www.ambysoft.com/artwork/buttons/buttonEUP.gif)](http://enterpriseunifiedprocess.com/) [![Ambysoft Inc.](http://www.ambysoft.com/artwork/buttons/buttonAmbysoft.gif)](http://ambysoft.com/) [![Follow @scottwambler on Twitter!](http://www.ambysoft.com/artwork/buttons/buttonSWATwitter.gif)](http://twitter.com/scottwambler)

------

[Copyright](http://www.ambysoft.com/licensing.html) 2001-2022 [Scott W. Ambler](http://www.ambysoft.com/scottAmbler.html)