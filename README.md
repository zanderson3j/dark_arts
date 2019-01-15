# Defense Against the Dark Arts

## Student: Zachary Anderson (andezach)

### Week 1 (1/15/19)

The Lecturer this week was Christiaan Beek. He works for Intel/McAfee and has done lots of work for the government as well. He is very knowledgeable on the subject of malware and is very enjoyable to listen too as he shares anecdotes about some high profile cases of attacks as well as some I hadn’t heard of.

Malware (Malicious Software) is created for many different reasons depending on the attackers motivations. It can be politically motivated such as attacks by governments on each other, financially like a criminal stealing credit card numbers or businesses bankrupting a competitor, or possibly made by someone who wants to just destroy things. Whatever the motivation, companies and people need to protect themselves, and one way is with anti-virus (AV) software which McAfee makes.

Mr. Beek has done a lot of research on samples of malware. He talks about using different tools to understand the threat and build a solution. He mentions that his company can get 200k-300k  malware samples to test daily which I found very interesting. Luckily, malware research seems to be very collaborative across companies and governments because that is an immense number of threats. It is mentioned that there is a demand for malware research skills. I am interested in the subject matter of this course since it is very foreign to me, and although I find it interesting to learn about so far, I don’t think it is something I would like to pursue as a career. It does seem useful to be aware of however.

There are different types of malware and I didn’t know the details of their differences before:

* Viruses:
  * Parasitic - depends on another file
  * Polymorphic - dynamically changes itself (very difficult to analyze/kill)
  * Worm - spreads quickly
* Trojans - sits on a host computer and sends back stolen information
* Potentially Unwanted Program - stuff that ends up on your computer you might not want like adware

The polymorphic viruses sounded particularly interesting and difficult to deal with. They can change where the malicious code is in a file and make themselves difficult to detect. 

Computers get infected in a variety of ways, but the primary method is by the user. At some point it is mentioned that for an email with a malicious link, it typically only needs to be sent to 8-10 people to get one click. Things like USBs are another way, but I found it very interesting that PDF and Microsoft Office files were a particularly popular way to deliver malware. I never really thought about it, but the lecturer really stressed the vulnerabilities of these file types.

Some More New Malware Definitions I Learned:
* White - clean sample
* Black - dirty sample (infected)
* Gray - not really sure if it is clean or dirty
* Sample - potentially malicious program being researched
* Goat - sacrificial computer that malware is run on to see what it does. some malware can recognize it is running on a virtual machine and change its behavior so this is useful. (this is also my favorite new word/definition)
* Honey-Pot - server waiting to catch malware so it can be studied.
* Hash - unique string calculated from a file and its contents. (only one piece of malware has been able to duplicate a hash)
* Replication - replicate what the malware is doing in order to create counter measures.

I found exploitation kits interesting. It seems like a hacker could gather information about a computer and then use exploits from a kit specifically tailored for that type of operating system and version, etc. I also thought ransom ware was very interesting. This is software that can hold data or access to a system for ransom. It was really spooky when it was later talked about how this could be used on a car or medical device. Ransom ware seems like it will be a huge problem with the internet of things.

In the lectures and in the lab, I was introduced to some ways to analyze malware. There are two main methods:

Dynamic:
This is where a malicious sample is run on a Goat or virtual machine (VM) and different tools are used to analyze what it is doing in real time. Here are the new tools I have been getting familiar with this week while analyzing a piece of malware on a VM:
* Flypaper - This program prevents a program exiting. One way this might be useful is if a program deletes evidence of its evildoing when it exits.
* FakeNet - This program creates a fake network for the malware to connect to so you can see the requests being made. I found this very helpful since it gives you the domain name and HTTP request.
* Process Monitor - This shows what a process is doing which could include creating new processes to check for. I used this to see that a program was making a bunch of new driver files, running command line commands, and making other directories and executables.
* Process Explorer - This shows parent and child running processes. I was able to see a malicious program had two child processes which were running on windows terminals.
* Antispy - This has a lot of different kinds of information on things like registries, processes, and network activity. I used it to see new run keys in the registry.

Static:
This is where a file’s contents are analyzed. Sometimes malicious code is embedded in a file and can be found by looking through the contents. I used a new tool called FileInsight to look at the contents of an executable that was scheduling tasks. It allowed me to see the code and try to understand what it is doing that way.

Overall this week, I found the lectures very enjoyable, but the hands-on work was a mixed bag. Listening to a Industry Professional with varied experience share his insights was a pleasure. The lab was a struggle because the VM would often freeze and I would have to revert to my last snapshot (version of the VM at a time before the virus was run) and restart the steps in the lab. I suspect that it could be a cpu issue since I had better results running less tools at a time. The actual work of trying to understand what a piece a malware was doing was fun, although I don’t think I’m very good at it yet.
