# Amazon CloudSearch - its performance and scalability
## About Amazon CloudSearch
Amazon CloudSearch is a fully managed service, offering search as a cloud-based service (Search As A Service) and can be used as a search solution for applications to search large collections of data. 

This would mean that multiple processes involved in setting up a search tool would be conveniently automated and abstracted behind one platform and includes the steps of:
-	Setting up servers
-	Installing and configuring search software
-	Indexing data
-	Designing code to integrate search into an application

The service is powered by the underlying text search engine [Apache Solr](https://solr.apache.org/?trk=public_post-text), thus enabling features such as:
-	Faceted search to refine search results
-	Geospatial search
-	Autocomplete suggestions
-	Support for 34 languages
Moreover, being a fully managed search service on the AWS cloud, it :
-	Automatically scales vertically and horizontally.
-	Automatically configures updates.
-	Provisions hardware and software.
-	Re-indexes data upon schema change in data or search fields.

## A brief history of Amazon CloudSearch
CloudSearch stemmed from Amazons in house search engine, A9, the search engine that powers search in Amazon.
To fill a gap in Amazon Web Service’s suite of tools, the power of A9 was introduced as CloudSearch with the A9 search engine underneath, and to provide a hassle-free experience of integrating search into application, CloudSearch was provided as a managed service in the AWS Cloud. This step automated most of the technicalities and the cloud-architecture maintained provisioning of resources, combining to give a hassle-free integration.
From 2013 onwards, Apache Solr was used as the underlying search platform of CloudSearch. This enhanced the capabilities of CloudSearch by bringing in key features such as geospatial search to its API.


## What makes CloudSearch attractive
### High level of abstraction
The cloud architecture of CloudSearch has abstracted most of the complexity of implementing a search service such as hardware provisioning and made it into nearly a plug and play service that can quickly be added to an existing application and control its technical aspects from the Amazon Web Services console, making it very simple to use.
### High availability
Secure servers of Amazon combined with CloudSearch’s option to provision resources for and host the search domain in two availability zones to serve as backups to each other, greatly increases availability to reduce chances of the search capability to go out of service due to server errors.
### A Fully Managed and customizable service
The high level of abstraction makes CloudSearch a managed service, automating tasks such as scaling up and down thus allowing developers to focus more on customizing the search experience by configuring to fine tune search results with words to ignore (stopwords) and synonyms for search items or commonly misspelled words.

Regular updates are instantly available to users as the service is hosted on the cloud, furthermore, changes and data migrations needed as a result of an upgrade are also handled by CloudSearch automatically.

## Scalability of CloudSearch – with data
Scalability is a feature that is shown as most advantageous, for a few reasons:
#### It scales automatically to the optimal size
CloudSearch calculates the amount and size of search instances needed for high throughput and low latency search. Therefore, no consumer intervention is needed. A search engine is created and at least one search engine of the optimal size (small, medium or large) is assigned.
#### It upgrades to a larger search instance type as search domain data gets larger.
As data gets larger and the threshold increases, the instance type is automatically upgraded toa  larger type. When the maximum instance type is reached, data is partitioned across multiple instances, this scaling **horizontally** with data.

#### Automatically scales down after drop in data or traffic
If an application only experiences a sudden increase in data or traffic and the volume of data later reduces, the domain and instances automatically scale down to a lower number of instances or a smaller instance type to minimize resources and therefore reduce service costs.

## Scalability of CloudSearch – with traffic
The load (traffic) handled by a search instance increases as the search complexity or volume increases. In that case, CloudSearch scales **vertically** by duplicating the search instance this providing additional processing power.

The following diagram taken from the Amazon CloudSearch Documentation shows how data scales horizontally with increasing data by partitioning, and vertically (with increasing search traffic and complexity) by duplicating search instances.

![cloudsearch-scaling-diagram](https://user-images.githubusercontent.com/62464945/193476811-476a56ec-12f5-4ac7-9805-0959384f8bb6.png)


Similar to scaling with data, scale ups due to increases traffic is scaled down as incoming search lowers by removing duplicate instances to automatically to minimize costs.

## How CloudSearch performance is improved
Since the servers are remote and provided through cloud architecture by Amazon Web Services, a provider with many datacenters across the world, and the domain is hosted in the cloud, this leaves room for data to be duplicated elsewhere away from the main data center should something to the main server.

Amazon offers this through the multi-AZ deployments (multi-Availability Zone deployment). This was an addition to the API in 2013, multi-AZ deployments allowed a user to select one other availability zone to duplicate and serve the search domain isolated from the main zone (and anything happening to it) but in the same region.

The zones follow the Primary-Replica architecture and share the search traffic load. Each server could also handle the full load of traffic. This increases availability as when one zone’s server became unavailable, the remaining zone’s server can instantly take on all the search traffic thus providing a seemingly uninterrupted search experience to those using the service.
## How CloudSearch search results are improved
Another aspect of CloudSearch’s performance is how it retrieves relevant data.

Search engines do this by stemming, which refers to mapping entered words to their stem and retrieving results for all the words sharing the same [word stem]( https://en.wikipedia.org/wiki/Word_stem). This improves search performances by retrieving other related search items as well.

From the 2013 API update onwards, CloudSearch uses an algorithm-based approach, as opposed to the previous explicitly declared stemming dictionaries (JSON objects) which were provided by developers, to identify the stems of entered search words.

The level of algorithmic stemming performed can be configured by developers to one of the levels:
-	None – Algorithmic stemming disabled
-	Minimal – Removes plural suffixes to perform basic stemming
-	Light – Targets most common noun/adjective conjugations
-	Full – Assertively stem conjugations and suffixes 

But to accurately stem words and avoid under/over stemming of inconsistent words, developers can also explicitly declare stemming dictionaries as JSON objects (as done before the 2013 API update) and use them together with algorithmic stemming to override certain instances of over-stemming or under-stemming due algorithmic stemming.
## How improved scalability and performance affect other quality attributes
Yet, the measures taken to increase scalability and performance could have mixed outcomes on other aspects of quality in a system.
#### Availability
The time taken to deploy new instances when autoscaling can lead to an increase in internal server errors during the time span taken until the new search instances can begin taking requests.
However, these requests can be configured to be caught and resent and implementing exponential backoff algorithm of Amazon Web Services SDK can briefly reduce incoming requests and lower failed requests.

#### Affordability
Despite automatic scaling reducing the amount of compute resources wasted, activating the Multi-AZ option duplicates the available search instances in another zone thus, doubling the search instances and the cost of running them.

---
To summarize, CloudSearch could be described as a very productive tool for adding search service to an application with an almost plug and play approach thanks to it being provided as cloud architecture utilized proving simple set up and configuration through the Amazon web services console, and due to being a managed service with its features such as auto scaling and data migration. Also, its scalability due to being automated to scale optimally, can be seen as a benefit among similar cloud search engines.


---
#### References
-	Developer guide
https://docs.aws.amazon.com/cloudsearch/latest/developerguide/cloudsearch-dg.pdf
-	Amazon CloudSearch
https://aws.amazon.com/cloudsearch
-	Amazon CloudSearch Documentation
https://docs.aws.amazon.com/cloudsearch/latest/developerguide/what-is-cloudsearch.html
-	Amazon CloudSearch FAQs
 https://aws.amazon.com/cloudsearch/faqs/
