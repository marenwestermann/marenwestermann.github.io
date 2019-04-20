---
layout: post
title:  "Shortcomings of online security by software providers"
date:   2019-04-20 14:12:49 +1000
categories: blogpost
---

# Collection#1
In January this year it came out that there had been a massive data breach. In total, more than 1 billion unique combinations of email addresses and passwords had been made public. The breach was named "Collection #1" by Troy Hunt, an Australian IT security expert, who discovered the breach. You can read more about it [here](https://www.troyhunt.com/the-773-million-record-collection-1-data-reach/). 

After learning about this I decided that it was time to update all of my passwords. According to the website <https://haveibeenpwned.com/> (which is run by Troy Hunt) I haven’t been pwned but my password practices were absolutely not secure. I had 7 passwords and used 4 of them multiple times. Additionally, the length of 3 of my passwords was no longer than 8 characters. That was too short. On top of that I used 2-factor authentication only for my Google accounts. 

I updated the passwords of all my accounts, reviewed all security settings (and while I was onto it also privacy settings) and enabled 2-factor authentication wherever possible. I generated random passwords using a small Python script (for more information see [here](https://www.practicepython.org/solution/2014/06/06/16-password-generator-solutions.html)) and set the password length to a default of 30 characters. I invested a bit of money in a password manager and stored all of my new passwords in it. (Note that most password managers come with their own password generator so you don’t need to run a script if you safely want to generate a random password.) 

Now one would think that it is easy to change a password, that you can always use long passwords of 20 characters or more and that there is always a backup method available when using 2-factor authentication. However, this is not the case. Here’s an excerpt of the most interesting things I encountered when updating my security settings. 



# Financial institutions 
I have bank accounts at two banks, one of the big four Australian banks and a major German bank. While it was possible to specify 30-character passwords for most of my accounts, this wasn’t the case when it came to online banking. The maximum password length is 16 characters at the Australian bank and 20 characters at the German bank. At least you can include numbers, letters and special characters. 

Furthermore, 2-factor authentication is not possible with both institutions. When you want to transfer money you need a code for authenticating the transaction (the Australian bank sends you codes via text message and the German bank has its own code generating device) but if someone would find out my passwords for these accounts, the person could view my account balances and my whole transaction histories. You could easily be scammed if someone gets hold of these information. 

Additionally, with both institutions you can’t specify that you want to get a notification (e.g. via email or text message) when an account login happened or the password changed. 

So in summary, the financial institutions stood out for me in insufficient IT security practices. 



# 2-factor authentication 
When you enable 2-factor authentication you need one primary authentication method and at least one additional authentication method, otherwise you are at risk of losing access to your account. For example, let’s say you use an authenticator app or codes sent via text messages to your phone for your primary 2-factor authentication and you don’t have a backup authentication method. If you lose your phone under this circumstance, you’re screwed. Maybe you’re lucky and can recover access to your account if you contact the software provider but I wouldn’t bet on that. 

One would think that software providers think of that (they have an expertise in IT, right?) but no, not all of them do. On LinkedIn for example you can enable 2-factor authentication but you can’t specify a backup method. It’s the same with ebay. 

The most interesting case in this respect was the Australian “myGov” through which you can manage government related organisational tasks like tax returns, unemployment benefit applications, etc). When using myGov you are obliged to have one 2-factor authentication method but you can’t specify more than one. 



# Let me quickly change my password
One would think that changing a password is a quick thing to do. However, in my experience this was not always the case. 

When I logged into my university email account and tried to update my password, I got the message that I don’t have the permission to do this: 

![UQ]({{ site.url }}/images/uq.png)

I contacted the IT service of my university to ask for help. I was notified that my university email account is linked to my general university account and that therefore it is not possible to change my password within my email account. I had assumed that because of this link changing my password within my email account would automatically apply to my general university account but this wasn’t the case. I was required to change the password for my general account and I needed to do it via a specific website which I previously was unaware of. I successfully updated my password, however it should be more straightforward. For example, if I would have noticed a suspicious activity in my email account on a Saturday and I wouldn’t have been able to figure out myself how to change the password, I would have needed to wait until the next Monday to contact the IT service. In the meantime, my account would have been unprotected. 

The strangest thing I encountered was when I wanted to change the password of my Skype account. When I tried to do this, I got the following notification: 

{:refdef: style="text-align: center;"}
![skype ><]({{ site.url }}/images/skype.png)
{: refdef}

Why do I need to wait for a month before I can make security changes to my account? On the official Microsoft support website it is said that the waiting period is put in place in order to “stop unauthorized people from trying to completely take over an account that isn't theirs” ([see here](https://support.microsoft.com/en-my/help/4057241/microsoft-account-why-does-resetting-security-info-take-30-days)). Although this is a good intention, it comes with some problems. Firstly, Microsoft’s solution for protecting its accounts is not very user-friendly. Secondly, not being able to change the password for a month is not good security practice because it gives someone who gets unauthorized access to your account a lot of time to inspect and store all of your data. 



# Summary and conclusion 
I thought that software providers, especially big companies, generally provide good IT security and that it’s mostly the everyday users without a background in IT that don’t make use of best security practices. However, as I learned, even when you want to apply best security practices as a user this is not always possible. I can therefore conclude that we have to catch up on this topic, not only from the user perspective but also from the provider perspective and therefore as a society. 

<br>

# Additional notes

#### **Data breaches**
The data breach Collection#1 is just one out of many data breaches. (For more information, look [here](https://en.wikipedia.org/wiki/Collection_No._1).)

#### **Password manager**
As I learned, there is a free, open source password manager that also comes with its own password generator. It’s called [KeePass](https://keepass.info/).

#### **Password length** 
There is a debate on the minimum length of passwords and unfortunately there is no clear answer. When using a password that consists of random alphanumeric characters and symbols, 16 characters should be long enough. I’m using the word “should” here because after doing some online research, different websites have told me that a random password of this length would take longer than the lifetime of a person to crack, even with multiple parallel GPUs. However, I couldn’t find out how many GPUs this information was based on.

In comparison, when a password consists of a concatenation of words that can be found in dictionaries, this password could potentially be cracked within a short amount of time (hours to days) through a dictionary attack. In this case it would be safer to use a password of more than 20 characters.

In general, I found it difficult to find quality information about the minimum length of passwords. When I researched this topic online there were multiple websites offering feedback about password strength and about how long it would take to crack a certain password. However, these websites were all privately owned by individuals or companies. The only independent advice that I could find, that was backed by a team of experts, was on the website of the German [Federal Office for Information Security](https://www.bsi-fuer-buerger.de/BSIFB/DE/Empfehlungen/Passwoerter/passwoerter_node.html) where it is recommended that passwords should generally consist of at least 8 characters and should be of at least 20 characters when Wi-Fi encryption methods like WPA and WPA2 are used. 


