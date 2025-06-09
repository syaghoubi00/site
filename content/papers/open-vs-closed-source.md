---
title: "Open versus Closed Source Information Technology Infrastructure"
date: 2023-10-14
author: "Sebastian Yaghoubi"
summary: "A business analysis of open versus closed source technology in information technology infrastructure."
tags: ["Open Source", "Closed Source", "IT Infrastructure", "Licensing Models"]
keywords: ["Open Source", "Closed Source", "IT Infrastructure", "Licensing Models"]
---

## Memo of Transmittal

This report contains guidance in regards to choosing licensing models to base an information technology infrastructure on. Both open source and closed source technology can come with benefits and drawbacks, this report highlights some of the differences between the two options.

During the planning phase of infrastructure choosing an adequate foundation is essential, as it is what supports everything built on top of it. Open versus closed source technology is one such decision that heavily impacts how the infrastructure foundation is built. An incorrect decision at the beginning of the building process often becomes extremely expensive, and sometimes becomes infeasible to fix without another complete rebuild.

This report concludes that while businesses of all sizes can benefit from open source, there are some caveats to consider during the infrastructure planning phase. The primary factor to be considered is the size of an organization's information technology staff, as some open source projects may not offer support contracts. Support, while not unique to closed source, is often more available due to the proprietary nature of closed source technologies.

## Executive Summary

### Purpose of Report

This report analyzes open versus closed source licensing models and their effects on businesses. With modern business dependance on information technology, planning an information technology infrastructure that can meet the demands of a business is as important as ever. One major consideration when choosing technology to use in an informational technology infrastructure is whether a technology is open or closed source. This is often a high stake decision for a business as it determines how well infrastructure can scale with a business, and what kind of costs a business can expect over time.

### Research Methods

The research in this report consists of both primary observational research and secondary research. Primary research is based on personal observations of the market, and work experience dealing with all of the issues discussed. The secondary research in this report uses information found on the internet. Examples of the secondary research used includes; news articles of historical events, academic whitepapers, corporate blogs, and articles analyzing specific issues.

### Recommendations

The recommendation resulting from this analysis is to use open source software wherever possible in your organization. The benefits of open source make it extremely difficult for closed source technology to compete. Open source often satisfies all business requirements, while reducing costs and increasing choice and flexibility when it comes to information technology infrastructure.

## Open versus Closed Source Information Technology Infrastructure

## Introduction

Modern business operations are highly dependent on information technology, with many businesses being unable to function without email or web services. Small to medium sized businesses are often not concerned with the specifics of the technologies that they are reliant on. As long as a particular piece of information technology is able to fulfill the requirements, the only other consideration is generally cost. Many businesses make the mistake of only considering the immediate costs of technology and fail to consider how information technology costs can compound due to faulty planning and lack of foresight.

The failure to consider the full scope of information technology choices can become a very costly mistake as businesses grow. Technology often becomes a deeply embedded part of business infrastructure and grows with the business. A small mistake made during the early phases of a business's life cycle can quickly become extremely costly as a company attempts to scale their infrastructure to meet ever changing needs. A critical part of information technology infrastructure planning that often goes unconsidered is whether the technology being used is open or closed source.

A fundamental requirement of open source technology is that the underlying specifics of the technology is accessible to the public, hence the source of the technology is ‘open’. Almost all technology is dependent on open source technology at some point. For example, without open source standards many technologies like the internet would be unable to function. Open source is important for technology as it allows for wide adoption and interoperability.

Conversely, closed source technology is generally considered any be anything that is proprietary, which often requires a fee to use or implement. Closed source, while lacking an industry standard definition, Kaspersky Lab (n.d.) provides the definition of closed source software as,

> Lack of access to source code is a common, but not obligatory, feature of proprietary software. The code may be partially or wholly accessible in some cases, but its use without the author’s consent is unlawful. The owner of proprietary software can: Make the source code available to everyone but place legal restrictions on its modification and use; Make the source code available to a limited group of individuals: auditors, government officers, key customers, etc.; Permit the use of a program’s source code under a certain agreement, free of charge or for a fee. Software is proprietary by default under the laws of most countries. When creating a program, the author automatically receives all rights to its distribution, modification, and use, whereas waiving such rights requires documentation.

While open and closed source is typically used in reference to software, such as the Kaspersky Lab (n.d.) definition, open and closed source can more broadly refer to hardware, software, implementations, and standards. Closed sourced hardware could be a computer part, such as a CPU or GPU, that cannot be built without licensing proprietary technology. An example of a closed source standard is H.264, a method of compressing video that is used almost everywhere, which has license terms that state, “to use and distribute H.264, browser and OS vendors, hardware manufacturers, and publishers who charge for content must pay significant royalties—with no guarantee the fees won’t increase in the future” (Google, 2011).

A business with an understanding of how it is using various open and closed source technologies is an essential step in designing a successful information technology infrastructure. Not having knowledge of the licensing models in use can open a business up to unexpected fees, lawsuits, and cancellation of services that it is reliant upon. This can lead to business interruption, and in extreme cases bankruptcy.

## Open Source

Open source is informally used to refer to the availability source material, there is however, a formal industry accepted definition set by the Open Source Initiative. The Open Source Definition, set by the Open Source Initiative (2023a), states that open source technology must meet the following criteria; allow free redistribution, have available source code, allow for derived works, ensure integrity of the author’s source code, no discrimination against persons or groups, no discrimination against fields of endeavor, distribution of license, license must not be specific to a product, license must not restrict other software, and that the license must be technology-neutral.

Technology that meets the definition of open source provides a unique benefit to its users. Free redistribution means technologies can remain free and available, removing concerns about unexpected fees or access being limited. Having the source code available allows for inspection, modification, and adaption of the technology for the users specific wants and needs. Derived works allow for technologies to be “forked”, the process of creating a copy of a project and turning it into a new separate derived project; this enables the development of a new version of the project based on the original technology if there is disagreement with a decision made in the original work. Integrity of the author’s source code ensures that different changes and forks can be identified as “official” and “unofficial” modifications. No discrimination against persons or groups and no discrimination against fields of endeavor prevents exclusion from usage based on a creator's preferences, ensuring user diversity and removing restrictions on what kind of businesses can use the project. Distribution of license ensures that a company cannot add restrictions to the original license, such as requiring a non-disclosure agreement to use the technology, if it was not included in the original license. A license that is not specific to a product prevents a license from restricting the usage based on being a part of a larger technology, so everything can be used independently of other technology and licenses. A license that does not restrict other software ensures user choice and flexibility by preventing a license from excluding the usage of other technologies. Licenses that are technology-neutral ensures open source will not interfere with other technologies in use.

### Why Choose Open Source?

The only way to ensure true freedom of choice within a business's information technology infrastructure is through the usage of open source. Your business's infrastructure should be your infrastructure, not restricted by the whims of a company who may not have your best interests in mind. It is not possible to control and manage infrastructure while relying on the closed source decisions of a third party. The freedom of choice provided by open source allows technology to be adapted to the needs of your specific infrastructure. The nature of open source technology also means that you can affect change. This can be achieved by directly modifying an open source project to your needs or helping steer the direction of a project by participating in open discussion. Another common method of affecting change is financially supporting projects through donations and sponsorships, which can encourage development and sustain the technology. Other reasons to choose an open source infrastructure is for the many functional benefits, such as; security, affordability, transparency, perpetuity, interoperability, and flexibility.

#### Security

Having the source code available results in improved security, even though closed source companies try to say otherwise (Clarke et al., n.d.; Wheeler, 2015). A portion of this may have to do with the misaligned incentive of closed source companies to not report security issues, as no one can verify or check for vulnerabilities. This means the company has little incentive to make these issues public or fix them in a timely manner (Wheeler, 2015). The recent exploitation of the company SolarWinds closed source software Orion was called the largest cyberattack in history by Microsoft President Brad Smith (Cerulus, 2021). The notorious SolarWinds hack affected approximately 18,000 businesses, including about a dozen government agencies who stated the hack posed a grave risk to national security (Temple-Raston, 2021; Vaughan-Nichols, 2020).

Open source also means that technology can be publicly scrutinized by security researchers. This allows users of a technology to see security researchers safety evaluation, and any potential flaws found within a technology. An example of this is cryptography, where universities and government agencies sponsor the research of the latest encryption technology through competitions. Because of this public research, a backdoor put into an encryption standard, which allowed the government to effectively spy on anyone using the encryption method was identified by security researchers (Masnick, 2013). Security research is also incentivized through the use of ‘bug bounties’, a practice in which a company offers a reward to researchers who are able to identify security issues. This also means you can pay to have a technology put through a security audit, though larger projects will often use community funding to provide a public security audit (Wheeler, 2015).

#### Affordability

With software costs increasing 62% on average during the period between 2009 and 2019, free open source technology can become extremely appealing to businesses of all sizes (Guay, 2019). Even with the additional costs associated with the purchase of optional support contracts, open source almost always is more affordable. Red Hat (now owned by IBM), the company behind Red Hat Enterprise Linux, an open source operating system with first party commercial support, showed that when compared to Microsoft Windows Server, a closed source operating system, using Red Hat Enterprise Linux can reduce server infrastructure costs by 29% and reduce information technology staffing costs by 41% (Red Hat Enterprise Linux Team, 2013). Another example is comparing two popular database options, where the open source option PostgreSQL is free compared to the closed source option Oracle Database, which starts at $104,310 (Anderson, 2020). With cost being a primary consideration when choosing technologies, an infrastructure built on open source offers maximal savings.

#### Transparency

While some closed source technology may have source code available, project contributions and communications by the individuals working on the project are often redacted or omitted. Conversely, all open source code, contributions, and communications are publicly available. This gives a huge advantage to open source, as project direction and progress can be tracked, as opposed to relying on press releases and company communications. Additionally, there is often much more visibility into why certain decisions were made. This provides much more visibility into the technology being used, and can aid in decision making when choosing infrastructure technologies.

#### Perpetuity

Due to the license model of open source technology, there is never a concern of sudden cost increases or license changes. A recent example is how the video game development tool company Unity made a sudden and unexpected change to their fee structure. Unity decided to add a retroactive fee based on downloads of products developed using their tool. This fee model was so poorly thought out it was quickly met with a fury of responses from users of the product who pointed out this new model can bankrupt some businesses (Parrish, 2023). This is not uncommon, and while Unity backpedaled some of the changes after public outrage, it serves as an example of how closed source technology can change fees at will, while open source is free and stays free. This reduces business risk, and can provide peace of mind when integrating technologies into business infrastructure.

#### Interoperability

Open source technology will most often utilize other open source standards, this improves interoperability with other technology. Closed source technology however will often create proprietary protocols and standards that will only interoperate with other technologies that pay to implement the proprietary technology. The license model of open source allows for projects to be modified and adapted; this enables custom integrations with other products that may be in use in your infrastructure, further improving interoperability. Closed source will usually prohibit such modification, preventing any possibility of adapting other products or making necessary changes to allow interoperability; this is usually intended to prevent the migration away from the closed source product. Being able to easily interoperate with other technologies ensures the infrastructure remains flexible and able to adapt to changes.

#### Flexibility

All of the benefits of open source technologies culminate to give maximal flexibility. Having the freedom of choice when it comes to infrastructure means easy adaptability and scaling. Without the binds of closed source technology, infrastructure components become much more like interchangeable pieces as opposed to rigid immovable blocks. This enables changes to be made much more effectively and efficiently, saving both time and money. Open source licenses will often lack any restrictions on deployment sizes as well, giving the flexibility to scale far beyond what may be limited by the contractual limits of closed source (The Linux Foundation, 2018). Having the ability to be flexible when it comes to infrastructure allows for more choice. This can help prevent your business from being put in difficult situations with no options.

### Advocates of Open Source

Some of the largest companies in the world have an active open source culture, such as Amazon, Google, IBM, and Meta. The world's fifth largest company, Amazon, with a 2023 market value of \$1.3 Trillion, has been an advocate of open source since 2006, with over 1,200 Amazon open source projects, while contributing and supporting many more (Amazon (AMZN) - Market Capitalization, n.d.; Amazon, n.d.). Google, the world’s fourth largest company valued at \$1.65 Trillion, is responsible for open source projects we are all familiar with, such as: Android, the mobile operating system; Chromium, the browser in which Google Chrome and many other web browsers are built upon; Go, a programming language used by many web applications; and Kubernetes, which is in common use across industry information technology infrastructure (Alphabet (Google) (GOOG) - Market Capitalization, n.d.; Google, n.d.). Meta, previously known as Facebook, currently has over 700 open source projects, with over 220,000 forks and 1.1 Million project followers (Meta, n.d.). IBM, another well known name in business, has been supporting open source for over twenty-five years, with 7,400 employees working on open source projects, and over 2900 open source projects available (IBM, n.d.).

## Open Source Considerations

### Lack of Support

While open source provides many desirable qualities, it does have some shortcomings. Notably, smaller projects will often lack commercial support. While community support is often available, this may be unsuitable for businesses requiring reliable and timely support. Usage of open source may require a highly trained internal information technology staff to overcome a lack of support options. The need for highly trained information technology professionals can sometimes be cost prohibitive depending on the size of the business. While there are companies specialized in informational technology contracting, this still may not be a viable option for smaller businesses.

### Potential User Interface Problems

Another possible undesirable quality of open source is what some may consider unpolished user interfaces. This is usually caused by development focusing on function rather than appearance. A common flaw in the closed source model is that companies will create a nice interface to attract customers to generate revenue, but often lack function as more development goes towards appearance to attract customers. The removal of this profit motive often leads to a focus on function first and appearance as a secondary feature in open source technologies.

### Abandonware Risk

One of the largest fears amongst open source consumers is a developer abandoning a project. Since work is generally entirely voluntary or donation based, developers may often have to prioritize other work to make money and put community open source projects secondary. This can lead to slow development times, and worse yet, total abandonment. While large open source projects often have corporate backing and support, some smaller projects often do not have this luxury. While derived works will allow the project to be maintained by someone else, there is sometimes no one willing to continue development.

## Closed Source

Because of the proprietary nature of closed source, most companies are going to opt into releasing their technology as closed source. Closed source provides the easiest path to charge customers for usage and make profits. The lack of visibility also limits competition by preventing competitors from viewing how certain processes are implemented within a technology, this is desirable for most companies selling a technology. Closed source also often enables vendor lock-in, which is profitable for businesses looking to retain customers, as consumers cannot easily change the product they use.

### Why Choose Closed Source?

### Niche Products

Since most companies will release their technology as closed source, there may not be an open source alternative to meet requirements. While the largest enterprises can afford to develop their own open source alternative, this is usually not financially feasible for small to medium sized businesses. This leaves no choice for many businesses, and closed source may be the only option. Even if there is an open source alternative available, it may not always be the best choice. For specialized tasks with specific requirements a closed source product may be able to best satisfy those needs. Understanding infrastructure requirements can help determine whether a closed source solution is required.

### Commercial Support

While many open source projects may not directly provide support contracts, open source allows for third parties to easily compete providing support to satisfy market demand. This is not always the case though, and support may not be available. If your business lacks the internal information technology staff to provide its own support, or prefers to have these services provided contracted out, choosing a closed source technology may better satisfy this requirement. Another reason to choose closed source technology for support is that in the case of first party support, they are often going to have the highest level of expertise when it comes to their own product. Most small businesses are likely going to fall into this category, as most businesses will not develop an information technology staff until later stages of growth.

## Addressing the Drawbacks of Closed Source

### Accounting for Future Migration

When choosing closed source, understanding how a future migration may be handled is essential. Because many closed source products often result in vendor lock-in, this may result in your business committing to using a particular product for the life of your business. This can also lead to being forced into supporting technologies long after they should be retired. Legacy system support can provide significant risk for businesses. A part of legacy system support risk is becoming burdened with significant expenses as outdated technologies often require highly specialized technicians to maintain them. Another risk associated with legacy systems is cybersecurity hazards, where systems that are no longer supported will not receive security updates, leaving your business exposed to security vulnerabilities. Understanding how, and if, the business will be able to retire and migrate away from closed source technology in the informational technology infrastructure will help with planning, and may provide a reason to choose one product over another.

### Understanding the Business Model

Having an awareness of how a closed source technology plans to make money can help prepare for future changes. If a product’s business strategy is to act as a loss leader to capture the market, expect some form of pricing model change or platform decay as value is attempted to be recovered. Vendor lock-in and aggressive license and support costs are common business strategies amongst closed source companies. Vendor lock-in prevents reasonably changing products, often trapping a consumer into using the product as fees increase. Aggressive license and support costs are often enabled by vendor lock-in. When a consumer is unable to switch to a competitor, there is no incentive to have competitive prices. Acquisitions are another strategy used to reduce competition and grow the reliance on a single platform. By acquiring a company or competitor, changes can be made, locking more consumers into a particular vendor.

As Platforms Decay, Let’s Put Users First (Doctorow 2023), highlights the many strategies companies use to ‘trap’ customers on platforms. The common closed source lifecycle starts with luring consumers with new, often free features, to build the platform. Once customers are using the product, companies use strategies like limiting interoperability and preventing an easy exit from the platform, trapping customers (Doctorow, 2023). Once customers are trapped, the company can harvest profits by limiting investment in improvement and reducing spending on maintenance of the product. Because this process of attract, trap, harvest, and decay is an effective profit strategy it is used by many companies. Understanding these models can help with implementing a response plan and planning for changes, improving infrastructure resilience during times of predictable change.

### Litigation Avoidance

Many closed source companies are known to engage in highly aggressive auditing of usage to ensure licensing compliance. Having an understanding of the exact terms of your licensing agreements can help prevent expensive litigation as a company tries to charge extra fees and back pay for contractual violations. Employing the usage of licensing experts to audit your infrastructure and review contractual agreements can save on unexpected penalties.

## Conclusion

The many benefits of open source make it difficult to compete with, though there are a few situations where closed source technology may be a better choice for an informational technology infrastructure. There are also degrees of practicality for implementing open source technology. Software is an easy starting point, as open source software will often better integrate with other open source technology, such as open source hardware and standards. This is also the most common piece of technology that businesses interact with. Implementing technology that maximizes choice and flexibility early on in a businesses informational technology infrastructure journey will help minimize future problems.

If an open source hardware alternative is available and meets requirements it should be considered for businesses of all sizes. As a general rule, prioritizing open source hardware is an inefficient use of time by small to medium businesses. This is because of the budget and scale necessary to afford and justify current open source hardware, which is often specialty equipment. Only the largest of businesses typically have the scale and budget to justify custom open source hardware because of the specialty and expense associated with such technology.

In cases where closed source technology makes more sense, such as the need for a niche product or a specific support requirement, there are some strategies that can minimize risk to an organization. Strategies to minimize risk include creating migration plans and understanding how the technologies in use plan to make money. Migration plans can create a method of moving to an alternative product if the need arises, minimizing business disruption. Understanding the business models of technologies in use can help predict changes in costs associated with a particular technology that businesses are often unprepared for.

It is often difficult to go wrong with an open source information technology infrastructure. Some of the oldest technologies in use are open source, reducing the risk of becoming outdated. Many of the largest businesses in the world utilize open source technology. This is because of the flexibility and choice provided by open source technology. These benefits can be utilized by businesses of all sizes, and open source technology can scale as a business grows. This makes open source information technology a superior choice when compared to closed source.

## References

Alphabet (Google) (GOOG) - Market capitalization. (n.d.). Retrieved September 27, 2023, from <https://companiesmarketcap.com/alphabet-google/marketcap/>

Amazon. (n.d.). Open source – Amazon Web Services. Amazon Web Services, Inc. Retrieved September 27, 2023, from <https://aws.amazon.com/opensource/>

Amazon (AMZN) - Market capitalization. (n.d.). Retrieved September 27, 2023, from <https://companiesmarketcap.com/amazon/marketcap/>

Anderson, K. (2020, July 22). PostgreSQL vs Oracle: Difference in costs, ease of use, and functionality. DZone. <https://dzone.com/articles/postgresql-vs-oracle-difference-in-costs-ease-of-u>

Cerulus, L. (2021, February 15). SolarWinds is ‘Largest’ cyberattack ever, Microsoft president says. POLITICO. <https://www.politico.eu/article/solarwinds-largest-cyberattack-ever-microsoft-president-brad-smith/>

Clarke, R., Dorwin, D., & Nash, R. (n.d.). Is open source software more secure?: Homeland Security / Cyber Security. University of Washington. Retrieved September 27, 2023, from <https://courses.cs.washington.edu/courses/csep590/05au/whitepaper_turnin/oss(10).pdf>

Doctorow, C. (2023, June 27). As platforms decay, let’s put users first. Electronic Frontier Foundation. <https://www.eff.org/deeplinks/2023/04/platforms-decay-lets-put-users-first>

Google. (n.d.). Google open source. Google Open Source. Retrieved September 27, 2023, from <https://opensource.google/>

Google. (2011, January 14). More about the Chrome HTML video codec change. Chromium Blog. <https://blog.chromium.org/2011/01/more-about-chrome-html-video-codec.html>

Guay, M., [@maguay]. (2019, September 3). It’s not just you: Software has gotten far more expensive: The software inflation rate from 2009 to 2019. Capiche. <https://capiche.com/e/software-inflation-rate>

IBM. (n.d.). Open source at IBM. IBM Developer. Retrieved September 27, 2023, from <https://www.ibm.com/opensource/>

Kaspersky Lab. (n.d.). Closed-source software (proprietary software). Encyclopedia by Kaspersky. Retrieved September 27, 2023, from <https://encyclopedia.kaspersky.com/glossary/closed-source/>

Linode. (2023, March 9). Open source vs. Closed source: What’s the difference? Linode Guides & Tutorials. <https://www.linode.com/docs/guides/open-source-vs-closed-source/>

Masnick, M. (2013, December 23). RSA’s “Denial” concerning $10 million from the NSA to promote broken crypto not really a denial at all. Techdirt. <https://www.techdirt.com/2013/12/23/rsas-denial-concerning-10-million-nsa-to-promote-broken-crypto-not-really-denial-all/>

Meta. (n.d.). About | Meta open source. Retrieved September 27, 2023, from <https://opensource.fb.com/about>

Open Source Initiative. (2023a, February 22). The open source definition. <https://opensource.org/osd/>

Open Source Initiative. (2023b, April 14). The open source definition (annotated). <https://opensource.org/definition-annotated/>

Parrish, A. (2023, September 12). Unity has changed its pricing model, and game developers are pissed off. The Verge. <https://www.theverge.com/2023/9/12/23870547/unit-price-change-game-development>

Red Hat Enterprise Linux Team. (2013, October 7). How Red Hat Enterprise Linux trims total cost of ownership (TCO) in comparison to Windows Server. Red Hat Blog. <https://www.redhat.com/en/blog/how-red-hat-enterprise-linux-trims-total-cost-of-ownership-in-comparison-to-windows-server>

Satyabrata, J., [@Satyabrata_Jena]. (2023, March 24). Difference between open source software and closed source software. GeeksforGeeks. <https://www.geeksforgeeks.org/difference-between-open-source-software-and-closed-source-software/>

Temple-Raston, D. (2021, April 16). A “Worst Nightmare” cyberattack: The untold story of the SolarWinds hack. NPR. <https://www.npr.org/2021/04/16/985439655/a-worst-nightmare-cyberattack-the-untold-story-of-the-solarwinds-hack>

The Linux Foundation. (2018, March 8). Why using open source software helps companies stay flexible and innovate - linux foundation. The Linux Foundation. <https://www.linuxfoundation.org/blog/blog/why-using-open-source-software-helps-companies-stay-flexible-and-innovate>

Vaughan-Nichols, S. J. (2020, December 18). SolarWinds, the world’s biggest security failure and open source’s better answer. The New Stack. <https://thenewstack.io/solarwinds-the-worlds-biggest-security-failure-and-open-sources-better-answer/>

Wheeler, D. A. (2015, July 18). Why open source software / free software (OSS/FS, FOSS, or FLOSS)? Look at the numbers! <https://dwheeler.com/oss_fs_why.html>
