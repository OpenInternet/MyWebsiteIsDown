# Что делать, когда ваш сайт теряет работоспособность

Угроза, с которой сталкиваются многие независимые журналисты, новостные сайты и блогеры, это когда их голоса неслышны из-за того, что их сайты недоступны. Во многих случаях причиной неработоспособности сайта могут быть простые и даже глупые ошибки, но в некоторых случаях, причиной может быть атака типа "отказ в обслуживании" (от англ. DoS или Denial of Service).

Этот документ поможет вам сделать первые шаги в диагностике потенциальных проблем. Если ваш сайт подвергается атаке типа "отказ в обслуживании" (DoS), мы предложим некоторые неотложные меры.

 * [Первые шаги](#first-steps-diagnosing-other-potential-problems)
 * [Дальнейшие шаги](#next-steps)
 * [Как реагировать на DoS атаку](#responding-to-a-denial-of-service-attack)
 * [Перед тем как выбрать сервис](#before-you-choose)
 * [Сервисы защиты от DDoS атак](#mitigation-services)

*Все технические термины представленны в [глоссарии](#глоссарий), в конце этого руководства.*

## Не ждите - приготовьтесь сейчас!

**Даже если ваш сайт не подвергался атаке типа "отказ в обслуживании", это руководство предлагает шаги, необходимые для подготовки, которая, мы надеемся, позволит полностью избежать недоступности веб-сайта**.  Перейдите сразу к пункту [Как реагировать на DoS атаку](#responding-to-a-denial-of-service-attack), чтобы узнать о самых распространенных решениях, которые вы сразу можете использовать, чтобы избежать атаку.

Если в настоящее время вы ищите информацию о том, как сделать ваш сайт устойчивым к атакам, которые могут привести к его недоступности, вам стоит для начала прочитать руководство, разработанное Фондом Электронных Рубежей (EFF или Electronic Frontier Foundation): [https://www.eff.org/keeping-your-site-alive](https://www.eff.org/keeping-your-site-alive).

Организация AccessNow предоставляет более углублённое руководство, содержащее множество ресурсов и описывающее большее количество способов защиты на английском, фарси, арабоском и русском языке.  Посетите  [https://www.accessnow.org/policy/docs](https://www.accessnow.org/policy/docs) и кликните по надписи DoS с правой стороны экрана, или скачайте копию руководства здесь: [https://s3.amazonaws.com/access.3cdn.net/3fd9faf32feb878cf7_krm6iy7bo.pdf](https://s3.amazonaws.com/access.3cdn.net/3fd9faf32feb878cf7_krm6iy7bo.pdf).

# Первые шаги: Диагностика других потенциальных проблем

Как правило, проблемы в работе сайтов возникают по причине программных ошибок или технических проблем компании, которая обеспечивает хостинг сайта. Иногда другие сложности, например, причины юридического характера, могут привести к тому, что хостер отключает доступ к сайту. По возможности необходимо для начала связаться с доверенными лицами, которые могут помочь вам решить проблему с сайтом (ваш веб-мастер, люди, которые разрабатывали ваш сайт, ответственный персонал вашей компании, если имеется, а также компания, предоставляющая для вас услуги хостинга).

После того, как вы изучите наиболее частые проблемы, перечисляемые ниже, **обратитесь к своему веб-мастеру и хостеру сайта!** Возможно, проблема, с которой вы столкнулись, еще не указана на их веб-сайте, возможно, проблема носит временный характер, или, возможно, сервис провайдер еще не знает о её существовании. Хорошие отношения с вашими сервис провайдерами требуют усилий: будьте вежливыми и чётко выражайте свои мысли, передайте специалистам результаты своего исследования, используя представленные вопросы, чтобы помочь им быстро решить вашу проблему.

## Список вопросов

1. **Видите ли вы сообщения об ошибках?** Возможно, это ***проблема программного обеспечения***, и для её решения нужно обратить внимание на недавние изменения, которые внесли вы или ваша команда, и связаться с вашим веб-мастером. Если вы отправите веб-мастеру скриншот, ссылку на страницу, на которой возникают проблемы, и сообщения об ошибках, которые вы видите, вы существенно облегчите его задачу по выявлению причины проблемы. Вы можете также попробовать скопировать сообщения об ошибках в предпочитаемый поисковик и посмотреть, легко ли можно устранить проблему.
2. **Видите ли вы сообщение от вашего хостинг провайдера?** Сайт могли отключить на юридических основаниях, из-за задержки оплаты услуг, нарушения авторских прав или других причин. Это ***проблема правил***, и ресурсы, предоставленные EFF, хоть и фокусируются на авторских правах в США, позволяют узнать большеe: [https://www.eff.org/issues/bloggers/legal/liability/IP](https://www.eff.org/issues/bloggers/legal/liability/IP).
3. **Ваш сайт не загружается?** Возможно ваш хостинг провайдер столкнулся с проблемами, то есть у вас ***проблема хостинга***. Можете ли вы загрузить веб-сайт вашего хостинг провайдера? Обратите внимание мы **не** имееем в виду секцию администратора на вашем собственном сайте, но сайт компании или организации, услугами которой вы пользуетесь для обеспечения хостинга вашего сайта. Посетите или постарайтесь найти блог "статуса" (например, status.dreamhost.com),а также поищите дискуссии пользователей о времени отключения хоста вашего провайдера на twitter.com. Простой поисковый запрос, например, “(название компании) отключение” позволит определить, многие ли пользователи столкнулись с такой же проблемой.
4. **Ваш хостинг провайдер работает, но ваш сайт недоступен?**  Зайдите на сайт [http://www.isup.me/](http://www.isup.me/) - и проверьте, возможно ваш сайт доступен, но у вас нет к нему доступа. Это ***проблема сети***. Возможно, проблема связана с вашим Интернет соединением или доступ к вашему сайту заблокирован.
5. **Можете ли вы открыть другие сайты, содержащие контент аналогичный размещенному на вашем сайте?** Попробуйте зайти на похожие сайты или сайты со схожей тематикой. Также попробуйте воспользоваться Tor ([https://www.torproject.org/projects/gettor.html](https://www.torproject.org/projects/gettor.html)) или Psiphon ([https://psiphon.ca/products.php](https://psiphon.ca/products.php)) для получения доступа к вашему сайту. Если это решение поможет у вас ***проблема блокирования*** -- ваш сайт всё ещё доступен в других частях мира, но заблокирован в вашей стране.
6. **Ваш сайт загружается с прерываниями или подозрительно медленно?** Возможно, ваш сайт перегружен числом и скоростью получаемых запросов на загрузку страниц -- это ***проблема производительности***. Это может быть вызвано "хорошими" изменениями, то есть ваш сайт стал более популярным и просто требует улучшения, чтобы обслуживать большее число читателей - проверьте аналитику вашего сайта, чтобы ознакомиться с долгосрочными характеристиками роста. Свяжитесь с веб-мастером или хостинг провайдером для получения инструкций. Многие популярные CMS платформы (Joomla, Wordpress, Drupal...) имеют плагины, позволяющие кэшировать ваш веб-сайт локально и интегрировать сети доставки контента (от англ. CDN или Content Delivery Network), которые могут существенно улучшить производительность и устойчивость сайта. Многие решения, представленные ниже, также могут помочь в решении проблем производительности.

### Советы

* **Резервные копии** В дополнение к услугам и предложениям, представленным ниже, нужно всегда делать резервные копии (сохранять их нужно не в том же месте, где расположен ваш веб-сайт!) - многие хостинговые и веб-сайт платформы включают эту функцию по умолчанию; но лучше всего в дополнение иметь копии, сохраненные на локальном жестком диске.
* **Установка обновлений** Если вы пользуетесь Системой Управления Содержимым (от англ. CMS или Content Management System), такой как  WordPress или Drupal, убедитесь что программное обеспечение вашего сайта обновлено до последней версии, особенно это касается обновлений, влияющих на безопасность.
* **Мониторинг** Есть множество сервисов, которые могут постоянно проверять доступность вашего сайта и сообщать вам по эл. почте или смс, если сайт недоступен. [Эта статья с Mashable](http://mashable.com/2010/04/09/free-uptime-monitoring/) содержит список 10 наиболее популярных сервисов мониторинга. Be aware that the email or phone number you use for monitoring will be clearly associated with managing the website.

# Дальнейшие шаги

If the above diagnoses do not help (or you are experiencing a severe ***performance problem***, your site may be the victim of a **"denial of service" attack**, where a malicious user (or many of them), try to view the website over and over again, quickly (using automated tools), and in doing so crowd out legitimate readers.  Sometimes it’s one “attacker” trying to do this to your site, which usually doesn’t cause much of a problem -- unless you pay for bandwidth.  More common is the “Distributed” denial of service (DDoS), where an attacker who controls thousands of machines targets a site with all of them.

*Imagine hundreds of people in line at a food stall who, when they get to the front of the line, slowly decide not to order anything, but then immediately get back in line.  There may be legitimate customers in line, but it’s going to take them hours to get their food, and the vendor may give up!*

This [video from Google's Project Shield](https://www.youtube.com/watch?v=wmTvv8ISwPA) provides a great description of these attacks.

# Как реагировать на DoS атаку

**Don’t wait until you have been attacked!**  All of the services listed below will work quickly to help you recover during or after an attack, but you can get protected now, before any attack happens!  This can reduce costs by lowering your bandwidth usage, and keep you online during an attack.  Once you’ve been hit, it can take up to three days for the Internet to "find" you at your new, protected address - so in almost every case, it’s much better to **be prepared and get started now**.  The first step is to work with the company you bought your domain from, and change the “Time to Live” or TTL to 1 hour.  This can help you redirect your site once it comes under attack much faster (the default is 72 hours, or three days).

There are many services that can help you with denial of service attacks; and they fall (very broadly) into two categories - **hosted** and **proxied** services.

## Hosted Services

Hosted services require you to move your website completely to their servers - you’re changing hosting providers.  Many of them can help you through this.  The benefits of this include the hosted solution often providing many other protection features in addition to DDoS mitigation; the downside can be cost (depending on what you currently pay) and control - you need to be able to trust your domain host, as they have a lot of control over your website. Hosted services may also use a mixture of the same technology as *proxied services* below.

### Pros:

* Provides one central service for most, if not all, your website needs
* Often includes many secondary services and consulting, and even limited legal defense in some cases
* Full support teams often on staff to help

### Cons:

* You must host your website with the service
* You must trust the service to manage your site and defend your rights
* These services often are much more expensive (but you don’t have to pay other hosting / DNS services anymore!)

## Proxied Services

Proxied services let you continue hosting your site wherever it is, and just change how others on the Internet find and access it - this is generally much easier to set up.  These services have servers around the world which essentially get out in front of your website and absorb or ignore malicious traffic.  They "mirror" and serve constantly-updated copies of your site.  These services are very easy to set up, and you maintain complete control of your website and hosting setup.  One challenge with proxied services is that very complex websites can sometimes experience problems with non-admin user logins and complex interactive/javascript area.  Please discuss these with your webmaster and the proxy service as most can be resolved.

### Pros:

* Lower cost (often with a free level)
* Quick and easy to set up
* You don’t have to change your existing website host
* You can change or quit the service at any time

### Cons:

* Fewer support options
* Focused primarily on just mitigating DDoS attacks - does not necessarily include help with malware or spammers.
* SSL (encrypted) traffic will be briefly decrypted and re-encrypted by the proxy server to pass it from their proxy to your server.

## Custom Options

It’s important to note that there are many ways to combine these approaches.  Many websites use what is called a Content Delivery Network (CDN), which takes some of the burden (serving images and other static content) off of a website and speeds it up greatly.  Dynamic sites (such as those powered by content management systems like Joomla, Wordpress and Drupal), can sometimes be "converted" into static sites that can be fully hosted (mirrored) using CDNs. 

Content Delivery Networks can help reduce bandwidth costs and load during DDoS attacks, which, if your host is powerful enough for the rest, can get you through.  There are hundreds of CDN services, including Akamai and Amazon CloudFront.  MaxCDN has a free level of service, but generally, cost scales with bandwidth, meaning that these may become a financial drain during a DDoS attack. These often require a bit of technical expertise to get working, and you should work with your webmaster.

Another option to investigate is to "mirror" your content across multiple different sites.  This is especially valuable if your content is being targeted for blocking or removal.

## Before you choose

Finally, for any service, you must be comfortable with the provider - that means trust, but also understanding their business model:  Is it fee-for-service?  If there’s a free version, does it receive less support than a paid alternative?  Is it funded by governments?   It is best to cover as much detail up front as possible to avoid surprises down the road.

### For all services:

* How is the company/organization structured and sustained?  What types of vetting or reporting are the required to do, if any?
* Consider what country/countries they have a legal presence in and would be required to comply with law enforcement and other legal requests
* What logs are created, and for how long are they available?
* Are there restrictions that impact you on what content the service will host/proxy?
* Are there restrictions on the countries where they can provide service?
* Do they accept a form of payment you can use? Can you afford their service?
* Secure communications -- you should be able to log in securely and communicate with the service provider privately.
* Is there an option for two-factor authentication, to improve the security of administrator access?  This or related secure access policies can help reduce the threat of other forms of attacks against your website.
* What type of ongoing support will you have access to?  Is there an additional cost for support, and/or will you receive sufficient support if you are using a "free" tier?
* Can you "test-drive" your website before you move over via a staging site?

### For hosted services

* Do they offer full support on moving your site over?
* Are the services equal or better options than your current host, at least for tools/services you use?  Top things to check are:
    * Management dashboards like cPanel
    * Email accounts (how many, quotas, access via SMTP, IMAP)
    * Databases (how many, types, access)
    * Remote access via SFTP/SSH
    * Support for the programming language (PHP, Perl, Ruby, cgi-bin access...) or CMS (Drupal, Joomla, Wordpress…) your site uses

### For proxied services:

* If you use SSL  (also known as HTTPS or secure web traffic), ask how they manage SSL.  In some configurations, it may be easiest to share your private SSL key.  If you do so, you need to have a high level of trust in the service provider, as they can "impersonate" your site (indeed, this is what you are asking them to do by providing a proxy!)
* Ask about how administration / editorial logins and pages are managed
* Talk about any interactive parts of your website (users who log in, comment, admin/editorial needs, complex interactive pages/javascript/animations) -- different proxy services manage these differently; you will need to test these before switching completely.

# Mitigation Services

All of the services listed below provide protection against DDoS attacks.  This is not a complete listing of services - there are many, many more.  These services all represent good starting points, as they have been used by other members in the independent media / human rights / free speech communities.

## Hosted Services

This by no means is an exhaustive list.  It focuses on services which can be initiated quickly and have strong track-records on protecting free speech online.  Please note that prices for hosted services are not directly comparable to those of proxy services.  Hosted services will take the place of any existing cost for website hosting.

### VirtualRoad.org

* **Cost:** Pricing starts at €100/month for simple sites.  Other tiers for more complex hosting needs or higher resource demands are available.
* **Restrictions:** None, though the service is focused on content management systems which use PHP (Joomla, Drupal, Wordpress, and similar)
* **About the organization and its business model:** VirtualRoad.org is part of Media Frontiers, a social purpose enterprise registered in Denmark as an ApS / limited liability company, established by the press freedom NGO, International Media Support (IMS).  IMS is funded largely by the governments of Denmark, Sweden, and Norway.  This organizational structure is meant to build long-term sustainable services for the community.
* **Additional Services:** VirtualRoad.org offers full-range protection encompassing a wide variety of services, from transferring your site to their systems, domain registration, optimization, security audits, protection from hacking and phishing, security reports detailing attempted attacks, and even support in responding to legal requests.  See [https://virtualroad.org/get-protected/packages](https://virtualroad.org/get-protected/packages) for more details.
* **Technical needs:** You will need to have full access to your website’s backend or backups, as well as to edit your nameservers. If you need technical assistance with any of the onboarding or hosting, VirtualRoad.org will support you through the process.
* **Get Started Now:** Visit [https://virtualroad.org/contact](https://virtualroad.org/contact) or email [info@virtualroad.org](mailto:info@virtualroad.org) 

### The Positive Internet Company

* **Cost:** Pricing starts at $495/month for fully managed servers. Shared hosting may be available for only £125/year.
* **Restrictions:** None
* **About the organization and its business model:** The Positive Internet Company is a for-profit company with offices in the UK and the US.
* **Additional Services:** Services are fully managed, including firewalls, databases, and backups. More information available here: [http://www.positive-internet.com/services/vip-hosting](http://www.positive-internet.com/services/vip-hosting)
* **Technical needs:** You will need to have full access to your website’s backend or backups, as well as to edit your nameservers. The Positive Internet Company provides technical assistance with onboarding and hosting.
* **Get Started Now:** Visit [http://www.positive-internet.com/contact-us](http://www.positive-internet.com/contact-us) or email good@positive-internet.com

### More Secure Hosting Organizations:

* **Greenhost:** [https://greenhost.nl/order/](https://greenhost.nl/order/) Greenhost is a Dutch [social enterprise](http://social-enterprise.nl/social-enterprises/greenhost/) founded to provide sustainable, environmentally friendly website hosting services.  Greenhost is committed to an open and free internet, and the protection of its users.
* **Ecological and Dissident Hosting:** [https://ecodissident.net/hosting](https://ecodissident.net/hosting) EcoDissident focuses on providing strong protection for free speech; you may want to pair hosting here with a proxied service, below).  EcoDissident is a service of [Webarchitects](http://www.webarchitects.coop/), a sustainable coöperative social enterprise.
* **Gandi.net** [https://www.gandi.net/](https://www.gandi.net/) .  Gandi is a French company, with offices in Baltimore (USA) and Vancouver (Canada), and supports many popular community tools and projects.
* **Many others!** There are many other organizations who are aligned with promoting Internet freedom and can help you recover from a DDoS in various ways. If you are or know of a service which should be listed here, please contribute.

## Proxied Services

Again, this is by no means an exhaustive list; there are thousands of commercial services which offer variants of proxy and CDN tools which can help defend against DDoS attacks.  This list focuses on services which can be initiated quickly and have strong track-records on protecting free speech online.

### Deflect

* **Cost:** Free
* **Restrictions:** NGOs, human rights, independent media
* **About the organization and its business model:** Deflect is an open source project of eQualit.ie, a not-for-profit technology collective based in Montreal, Canada with deep roots in the human rights technology community.  Deflect is funded by NGOs and governments, including the US government, to provide Deflect services to protect the freedom of speech.  Deflect does not disclose the websites they protect nor need approval to provide service.  Deflect maintains servers with like-minded hosting companies around the world.
* **Additional Services:** The Deflect team will support you getting on to their services.  They have some grant funding available to pay for additional SSL Certificates and other related protection/recovery costs.  Sites protected by Deflect can opt to add additional layers of security to their core site.
* **Technical needs:** You will need the ability to change your nameservers.
* **Get Started Now:** [https://wiki.deflect.ca/signup/](https://wiki.deflect.ca/signup/).  See also [https://wiki.deflect.ca/wiki/Join_Deflect](https://wiki.deflect.ca/wiki/Join_Deflect)

### CloudFlare

* **Cost:** Free for basic protection, $20/month to include SSL support, and up to $200/month for more advanced needs.  Paid customers receive preferential support and uptime guarantees.
* **Restrictions:** Subject to US export controls, see also [https://blog.cloudflare.com/thoughts-on-abuse](https://blog.cloudflare.com/thoughts-on-abuse)
* **About the organization and its business model:** Cloudflare is a privately-held Delware-incorporated US for-profit company based in San Francisco.  They maintain servers around the world ([https://www.cloudflare.com/network-map](https://www.cloudflare.com/network-map)) and comply with legal requests.
It should be noted that part of CloudFlare’s defenses against DDoS attacks occasionally degrade access from the Tor network.  This happens if someone is using Tor to abuse a service, and is **not** a policy decision to block Tor.  See also [this blog post](http://blog.cloudflare.com/cloudflare-and-free-speech) for further policies from CloudFlare regarding free speech.
Cloudflare is required to comply with US legal requests and National Security Letters.
* **Technical needs:** You will need the ability to change your nameservers.
* **Get Started Now:**  Create an account here: [https://www.cloudflare.com/sign-up](https://www.cloudflare.com/sign-up)

### Google’s Project Shield / PageSpeed

* **Cost:** PageSpeed is free during trial period; Project Shield is "currently offered free of charge to trusted testers." For both, there will be a 30-day notice before it changes to a fee-based model.
* **Restrictions:** You must be approved, generally a 2-hour process, but may be restricted for some organizations or countries.  Project Shield is currently invite only, and is "accepting applications from websites serving news, human rights or elections-related content."
* **About the organization and its business model:** Google is an international, public, for-profit company based in Mountain View, California, USA.
As with most Google products, this ties the Google account you use to your website. This service falls under Google’s overall privacy policy and terms of service.  
Google is required to comply with US legal requests and National Security Letters.
* **Technical needs:** You will need the ability to fine-tune your DNS records.  PageSpeed rewrites and optimizes some parts of your website, which can alter functionality; you should be ready to test for this.
* **Get Started Now with Pagespeed:** Begin the sign-up process here: [https://developers.google.com/speed/pagespeed/service](https://developers.google.com/speed/pagespeed/service)
* **Get Started Now with Project Shield:** Request access here:  [http://projectshield.withgoogle.com/about/](http://projectshield.withgoogle.com/about/) . Note that Project Shield is currently invite only and providing access on a rolling basis.  After you sign up, you will "be notified via email if your site is selected to become a 'trusted tester'."

### More Proxy Services

There are many other organizations who offer tools to help protect sites from DDoS attacks. If you are or know of a service which focuses on protecting free speech against DDoS and should be listed here, please contribute.

## Related Services: Domain Name Registration

DDoS attacks also impact many other services around your website - the service that directs visitors to the right webserver (DNS servers or name servers) may also be attacked or impacted.  While the services you engage below will support you in chosing/moving DNS providers, here is a short list of well-regarded services.  EasyDNS and Hover.com are based in Canada, 1984.is, Iceland.

* EasyDNS [https://web.easydns.com/](https://web.easydns.com/)
* 1984.is [https://www.1984.is/](https://www.1984.is/)
* Hover.com [https://www.hover.com/](https://www.hover.com/)

# Глоссарий

* **CDN / Content Delivery Network:** A worldwide collection of computers you can program your website to use to serve content quickly.  Consider the case where your website is hosted in Iceland, but you have visitors from Thailand.  If you use a CDN, at least parts of your site can be delivered to the visitor from a computer that is much closer to them, than having to come all the way from Iceland.  This also has the effect of spreading the load out among other computers, which can reduce the severity of a DDoS Attack
* **DDoS / Distributed Denial of Service Attack:**  a "denial of service" attack is where a malicious user (or many of them), try to view the website over and over again, quickly (using automated tools), and in doing so crowd out legitimate readers.  Sometimes it’s one “attacker” trying to do this to your site, which usually doesn’t cause much of a problem -- unless you pay for bandwidth.  More common is the “Distributed” denial of service (DDoS), where an attacker who controls thousands of machines targets a site with all of them.
* **DNS Record:** The DNS record is like the master Contact List of Phone Book of the Internet.  All website servers are identified by a series of numbers and/or coded letters (the IP Address) - Google.com is 74.125.228.69, for example.  By changing this record, you can give out a different IP Address for a website - which could be a new hosting provider’s address or a proxy for your original website.
* **Domain Name:** The human-readable name of your website - google.com, for example.
* **Nameserver:** When a browser wants to find a website, it will first contact a name server, which will tell connect the domain name (google.com) to it’s Internet address / IP Address (74.125.228.69) via it’s DNS Record (above).  By changing the DNS record at a name server, you can "point" the browser to a different server.
* **SSL:** Also referred to as HTTPS, a secure way (from the browser to the website) to interact with a website. See also [Wikipedia](https://en.wikipedia.org/wiki/Secure_Sockets_Layer#Description)
* **Website host:** The server where your website and its files/databases are stored.


[![githalytics.com alpha](https://cruel-carlota.pagodabox.com/dc4c191166ab89785c89e222c02e5572 "githalytics.com")](http://githalytics.com/OpenInternet/MyWebsiteIsDown)
