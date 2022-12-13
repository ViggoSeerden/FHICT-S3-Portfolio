# Data Protection
By Viggo Seerden

## Table of Contents

- [Introduction](https://github.com/ViggoSeerden/FHICT-S3-Portfolio/blob/main/Research%20Report:%20Data%20Protection.md#introduction)
- [What is data protection and why does it matter?](https://github.com/ViggoSeerden/FHICT-S3-Portfolio/blob/main/Research%20Report:%20Data%20Protection.md#what-is-data-protection-and-why-does-it-matter)
- [How can we properly protect data?](https://github.com/ViggoSeerden/FHICT-S3-Portfolio/blob/main/Research%20Report:%20Data%20Protection.md#how-can-we-properly-protect-data)
- [Conclusion](https://github.com/ViggoSeerden/FHICT-S3-Portfolio/blob/main/Research%20Report:%20Data%20Protection.md#conclusion)
- [Sources](https://github.com/ViggoSeerden/FHICT-S3-Portfolio/blob/main/Research%20Report:%20Data%20Protection.md#sources)

## Introduction

Privacy and security are both big parts of todays world that go hand-in-hand together. Applications, websites, and other can sometimes require users to enter personal data to progress. This can be anything from something as trivial as a username or as sensitive as creditcard details. Anyone would be cautious if asked to just enter something valuable that you would normally take to your grave, so it's of extreme importance to make sure no one can access this data. The data does have to be stored somewhere after all, like in a database, but this alone doesn't mean much, since others can still look at what's inside of said database. It's with this research that I want to find out how to properly protect user data.

## What is data protection and why does it matter?

Data protection is the act of securing any information stored in a location such as a database. These databases are usually remotely accessible, which means it can in theory be accessed from any device with an internet connection. This can be a scary thought for some people who have sensitive data stored in one. There are several examples of huge data leaks that have happened which exposed all kinds of data to people with bad motives from sites like FaceBook, Twitter and LinkedIn, but also from other apps and platforms like Zoom and PlayStation Network. These sites can all store sensitive information about their users like full names, pictures, addresses and payment details. However it's not just big data leaks, because hackers can also break into targeted individuals' accounts. 

## How can we properly protect data?

There are several ways that a software developer can protect user data stored in a database. I'll go over a few methods here.

First of all: Authentication and authorization. Authentication means locking data behind, for example, an account, which requires logging into before being able to access your data. Having a login system on your website is the most common way of going about this. Allowing every user to create their own account with their own unique data also means preventing other users from accessing your data. Of course, someone might get into an unsuspecting users account somehow, but thats where authorization comes in. This means performing an extra check to see if it really is an accounts rightful owner trying to log in, and not some random other person. This is nowadays commonly done through Two-Factor Authentication, or 2FA for short. After logging in, 2FA sends the linked account a confirmation code, usually via phone or mail, which is then entered in the website or app to continue. A system like this can be created from scratch, but personally I'd use an existing one like Sign in with Google. 

Aside from general accounts available to the public, locking access to your database from some management tool behind an authentication system is also a good idea. This means having to authenticate yourself to access the database tables, and thus the data stored within. 

If someone is able to break into your databases somehow anyway, enabling something like encryption is another way to stop someone from unauthorized access. Encryption means encoding the data to something uncomprehensible to humans using an algorithm. Take for example a password. If encryption is applied, a password like "thisismypassword" can be converted to any random combination of characters. This gibberish can then be stored directly into a database. Encrypted data can also be used while making API calls, so that anyone wiretapping your internet won't be able to make out any data from the requests and responses sent. The only way to decrypt it is through a decryption key, which pretty much means running the algorithm in reverse. 

Other methods that can be used to achieve a similar effect include pseudonymisation, anonymisation, suppression and generalization. Pseodonymisation means processing data in a way that makes it unable to be linked to a data subject without additional information. Anonymisation is the irreversible deletion of parts of data which could be used to identify a data subject. Suppression is censoring data in a literal sense, as in replacing (parts of) the data with a certain character like in a password input box. Finally, generalization is making data more vague, by increasing the amount of possible correct ways to interpret it. For example, storing someones age of 25 as "20-30" or "20 < Age < 30".

Finally, I have a few smaller, but effective examples of things that can be done to prevent any data from leaking. The first being through backups. Should a nefarious person access your database, and decide to wipe the whole thing, or delete chunks of it, having a backup can save you a lot of trouble. Another thing to do is to delete any data you don't need anymore. It's easy to just forget about this, but if you don't need a piece of data anymore from a user, then you shouldn't have that data. You can also decide to use a third-party hosting service for your database. These can include more advanced security measures that would take a very long time to recreate, while also possibly doubling as a management tool or providing you with other tools. And last but not least: Removing logging. During development, an easy way to test the connection to a database is to log the received data in a console. I know this, since I've done it myself quite often, and this too is easy to forget about. If all it takes to see your data is pressing the F12 key, you should really take a step back and fix this. 

It should be noted that software developers and engineers are not the only ones who can take security measures; you can too. There are a few things you can do to protect your accounts. First of all is by clearing cache, to destroy any possible traces of login information, or by making your login information more complicated, deleting unneccessary accounts, or avoiding public networks, which have less security like a lack of encryption and don't require a password to establish a connection. Someone on the same network can use a program like WireShark to grab data from webrequests. Finally, there are sites like HaveIBeenPwned.com which lets you see if any of your email addresses or phone number have been in a data breach. It shows you the exact site or app that was breached. If you get one or more matches, you can go to those breached accounts and change their info or delete them outright. These measures can be encouraged and advertised in your application or on your website to help users protect their data.

## Conclusion

Data protection is an important part of securing your application or website. The chances of someone or something being able to successfully expose data, by any means neccessary, that generally shouldn't be must be minimized as much as possible. It's because of this that data protection measures should be taken. There are several ways to go about the protection of data, such as authentication and authorization, censoring data through encryption or a similar practice, or things like a third-party database hosting service, backing up data, deleting unneccessary data. Encouraging users to take some actions of their own should be done. A few ways to do this include deleting unneccessary accounts, clearing cache, or by informing them about possible dangers that come with public networks. It's with these measures that our privacy can stay just as it should be: Private.

## Sources

- [Data Protection Practices(GDPR Informer)](https://gdprinformer.com/gdpr-articles/6-essential-data-protection-methods)
- [Data Protection Practices(Meta/FaceBook Developers)](https://developers.facebook.com/docs/development/data-security)
- [Data Censoring Types (TeskaLabs)](https://teskalabs.com/blog/data-privacy-pseudonymization-anonymization-encryption)
- [Account Security Measures You Can Take (LiveLearn)](https://livelearn.ca/article/digital-citizenship/5-easy-things-you-can-do-now-to-keep-your-accounts-secure/)
- [HaveIBeenPwned](https://haveibeenpwned.com/)
