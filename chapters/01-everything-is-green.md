# Chapter 1: Everything Is Green

Ramona settled into the head of the long conference table. Its once-polished surface was now a medley of matte tones, the result of over a decade of spills and haphazard cleanups by whatever solvent and rag were immediately at hand. On the table sat a thick stack of printed, full-color slides with the cover page that read “BIWEEKLY IT OPERATIONS BRIEF, JANUARY 12, 2026.”

It had been a week since Ramona arrived, but this was the first real work meeting that she had attended. As with all new employees at the Civil Defense Agency, her first week was spent completing required orientation and training sessions. She had come from Whalen-Cole, a company that had rebuilt itself around high-octane Silicon Valley culture, and that culture was deliberately nurtured: at Whalen-Cole, orientation for new employees made them feel part of a tradition, a team, a cause.

But at CDA, the orientation focused on fire exits and timecards. The training—which someone advised her to blaze through in one sitting—took four hours and focused on data security and something called the Federal Records Act. Each training module was followed by a quiz that focused more on arcane details than on actionable knowledge:

*Q: Which of the following requires annual training in records management?*

*1: NARA/OMB Memorandum M-19-21<br>
2: NARA Bulletin 2017-01<br>
3: NARA/OMB Memorandum M-12-18<br>
4: 36 CFR 1220.34(f)*

When this question appeared on her screen during her training session, Ramona wondered about the circumstances in which this knowledge would be useful to her. At a party? Did people banter about obscure policy memo titles over cocktails? Was this the average DC wonk’s idea of a good time?

But she was done with that now, mercifully (until next year, at least). The biweekly ops meeting was typically casual, the kind with a box of donuts and off-color jokes. But this time, the room was full but silent. No one dared set the tone of the first meeting with a new boss; once she had done it, everyone else would follow. Still, their faces betrayed their thoughts: *Why was a government novice hired over me to do this job? Does she have any idea what she’s in for?*

“Good morning, everyone,” Ramona began, her voice steady but warm. “Let’s get started.”

This periodic briefing was run by Marcus Blain, the Associate CIO for IT Infrastructure and CDA’s primary POC for most of the issues that would cause large numbers of users to think in unison, *Something’s wrong with my computer*. Usually jocular, he withheld his true personality this morning in exchange for something overly formal.

“Good morning, ma’am. We’ve had three network outages in the past two weeks,” he started. “Two of them were little blips, barely noticeable to anyone. But the third knocked our public-facing benefits portal offline for 90 minutes.” Ramona took this in. The benefits portal was perhaps CDA’s most visible digital product to the general public, and the one that families relied on in the aftermath of displacement to get help. If the portal was down, the entire agency was down in the eyes of those who needed it. In the conversations Ramona had with Director Mercer prior to taking this job, he had specifically called out the waning trust the public had in the agency to get the job done, and outages like this were a big part of the problem.

“It was caused by a misconfigured routing table that was deployed by Axion,” Marcus continued, a tad of frustration cracking through his veneer. “It’s not the first time we’ve seen this.”

Ramona was surprised to hear Axion’s name in the context of network configurations. Axion was well-known in the private sector, but solely as an accounting firm. They were the firm you hired to do independent audits of your financial controls, not run your network. What Ramona didn’t know was that in the public sector, Axion had somehow become the *de facto* vendor for all manner of IT services: cloud hosting, security operations centers, network services, software development, helpdesk. Dozens of federal agencies (and hundreds of state agencies) relied on Axion for at least one critical IT operation.

Ramona didn’t understand routing tables, but she had sat in enough meetings at Whalen-Cole to know two things: when outages happened, they got resolved in minutes; and it had been years since the last such outage at Whalen-Cole, thanks to investments they had made in automated testing for their critical infrastructure. “Ninety minutes seems like a long time to fix a routing table,” she said. “Why did it take so long?”

This was a dangerous question for Marcus. In his experience with Axion, two hours was an improvement. “We got the first notification that the site was down about 20 minutes after the bad configuration went live. We notified the portal team. About 30 minutes after that, they told us there was a DNS issue. We then notified the cloud team, who found the issue and notified the network team of their error. It took the network team about 15 minutes to locate a backup of their previous configuration, then another 25 to roll back and make the correction to the change that broke the table to begin with.”

Ramona played Marcus’s answer back in her head, counting four instances of the word “notify.” “When you say ‘notify,’” she said, “what does that look like?”

“It’s primarily email,” said Marcus, a touch of sheepishness—maybe shame—creeping into his demeanor.

To Ramona, the fact of the broken configuration was overshadowed by the highly manual, back-and-forth manner in which it was fixed. Didn’t they have automated monitors for the site to let them know the portal was down? Weren’t new network configurations tested before deployment? Couldn’t they be rolled back in seconds? And how many separate teams were involved in this process? How much time was wasted waiting for these people to check their email and type out updates?

Automating their infrastructure to prevent such incidents would take months or years, but maybe, Ramona thought, a manual process could be made more efficient. “All in all, how many different teams were involved in this incident? How can we expedite their communication?”

Marcus could have answered this question literally, but he opted to skip to the answer Ramona would have eventually gotten to with repeated questioning. “On our org chart, just two: cyber and infrastructure. But it also required three separate vendor teams: one handling our cyber monitoring, an Axion team performing network operations for the whole enterprise, and another separate Axion team managing the cloud environment.”

“And do the vendors talk to each other?”

“No ma’am. They can’t act without going through us.”

“So, with CDA as a middleman throughout this process, there are maybe a dozen hand-offs for an operation that is essentially a handful of keystrokes.”

Marcus looked up at the ceiling, doing quick math in his head. “I’d say that’s roughly accurate, yes ma’am.”

“Why wait on the contractors? Why not jump in and take care of this problem with our own engineers?” The idea was simple enough to anyone outside government: *Why rely on this peace treaty-level email chain to fix an emergency that takes just a few seconds? Just do it ourselves!* But the answer was the reason behind so much of what holds government IT back: ultimately, they were not in charge of the systems in question.

“Both the cloud and the portal are managed services,” said Marcus. “The vendors control the systems entirely, and we have no window into their operation but through the vendors. They rely on us for permission to act, but we rely on them for knowledge of what’s going on.” Ramona tried to conceal her shock at something that, to everyone else, seemed normal. Rather than betray too much ignorance in her very first meeting, she shifted her focus to the source of the error. “Tell me about Axion’s performance. You said they’ve done this before?”

Marcus sucked his teeth, as though gearing up for a bad story. “In this case, it was caused by new personnel that Axion just added to the contract. This new person replaced someone with a lot of knowledge of our infrastructure, and they didn’t understand the tables like they ought to have.” Marcus paused. He had been practicing this speech in his head, so as to make it seem like he was more on top of this situation than he actually was. “This has become a theme with Axion: a relatively inexperienced engineer joins their team, gets put onto our contract, and builds up indispensable knowledge, eventually becoming a quite skilled network manager. And then, in order to impress a new customer, Axion pulls that highly skilled person off of our contract and replaces them with someone new.”

A few heads shook in agreement, as though it was a recurring theme across several IT programs.

Ramona started this line of questioning thinking that low-hanging fruit could be found, to turn a 90-minute outage into a 5-minute outage. Now, she was beginning to think that, with enough questions about a simple routing table, the room would eventually expose every shortcoming in public sector IT. “Can we find time soon to discuss this more? I’d like to start at the beginning, with the status of their contract.”

“That’s actually on our agenda for this meeting. Shall I skip ahead?”

*So much for deferring it*, Ramona thought. “No.” She wanted to show respect for whoever crafted the agenda. And honestly, her brain needed a break. “Let’s stay the course here and move on to the next scheduled item.”

* * *

The agenda shifted to another topic, and then another. Throughout, Ramona’s attention shifted from the content of the briefings to the format of the meeting: Marcus stood at the opposite end of the table, his laptop opened toward the audience, so that they could see the slides of a PowerPoint file that contained the briefing materials. The file had been appended to the meeting invitation, but Marcus’s team printed copies for all attendees on high-quality paper. Ramona’s copy sat in front of her unopened, but most of the other attendees turned the pages as Marcus advanced his slides, constantly shifting their attention from the paper to Marcus. Ramona got the sense that each person in the room was thinking about something different, rather than everyone focusing closely on his words, let alone participating in a collective discussion.

The agenda eventually wound its way to the Axion contractual item Marcus had mentioned. “As many of you know, we’re currently in a precarious position regarding Axion’s contract.” He clicked through to a slide that displayed a timeline filled with red flags.

“The current contract managing our cloud services is expiring in six months. We’ve been working on the recompete since 2023. The RFP went out last summer, and last month, we awarded a new 5-year contract to Axion.” Marcus paused. “Unfortunately, another vendor has filed a protest to the Government Accountability Office.”

With this, the rest of the room finally let its emotion show, first in the form of a collective sigh. Then came a few comments. “Typical,” said an unidentified person under their breath. Then from the outer edge of seats along the wall came a remark that was a bit too edgy for the moment:

“There goes the next three months of your life, Marcus.” Snickers followed, but Tim Krieger, the Chief Information Security Officer, cleared his throat, silencing the comic relief.

“This isn’t a joke,” he said firmly. “If the protest succeeds, we’ll be stuck in procurement limbo while this contract approaches termination. And Marcus, make sure Procurement starts the motions to exercise a 6-month extension. It’s usually allowed under the FAR.”

The conversation had stopped being technical in the technology sense and had become technical in the government administration sense—well outside Ramona’s comfort zone. It was now useless for her to pretend she was following along. The other option—plainly admitting her ignorance of terminology that seemed elementary to her new direct reports—was also fraught. But she had learned something in her years of meetings with technologists: feigning knowledge is a far greater sin than admitting ignorance. There was no quicker way to lose the respect of an engineer than to be a confident charlatan.

She leaned forward and rested her elbows on the table. “I’m sorry, but I need to back up. I’m sure one day I’ll understand these terms. But I just finished a week under an acronym firehose.” This comment got a few grins; they had all been there before. “So, please bear with me and start from the beginning. What exactly is a protest in this context? Is it something we did wrong in the procurement process?”

Though they didn’t say it out loud, a few of the meeting participants were grateful she asked, because aside from their pedestrian understanding of the issue, they didn’t really know the answer either.

Marcus broke the silence. “A protest is when a vendor challenges a government procurement action. Usually it’s because they were bidding on the same contract, and they wish the result had gone their way. So they file a formal complaint with the GAO, alleging that our award decision was flawed in some way.”

That another firm had protested an award to Axion was not a surprise: for a big contract like this, with a 5-year value over $500 million, many firms would file protests simply because the costs of doing so were outweighed by the potential benefits of victory. The biggest firms were staffed with armies of lawyers hired solely to manage contract disputes, so it was quite possible that this protest held no water.

At the same time, it was an open secret that Axion had an unfair advantage over other bidders. As the long-time contractor on the cloud program, they had access to privileged information about CDA’s operations and challenges. And as Marcus had just explained minutes prior, Axion had complete control over CDA’s cloud infrastructure. This made it impossible for any other firm—or even the government itself—to take over the systems without a long, expensive transition process.

“And how long does this protest process take?” Ramona asked, beginning a rough timeline in her notepad. Her eyes stayed focused on the paper as she waited for someone to answer…but no answer came. As it turned out, no one in the room had a firm grasp of the process. On the one hand, Ramona was relieved that her ignorance seemed matched by those in the room. On the other hand, she was dismayed that no one had mastered a topic that, according to so many, had become a fact of life in IT procurement. Beth Ellis, the longtime assistant to multiple CDA CIOs, was finding the answer on her laptop.

“Award protests must be filed within 10 days of the award notice.” She read at a pace that one does when assimilating facts while reading them from a screen, slowly making her way to the pertinent information. “The agency has 30 days from the date of protest to respond…after which the protestor can file *another* protest if they find something protestable in our response…” Beth could feel the room losing either patience or interest. This meeting was supposed to be an IT operations briefing, not a lesson in administrative law. She skipped to the end: “GAO must render its decision within 100 days of the protest being filed.”

One hundred days would eat over half of the six remaining months on the contract. And if GAO sided with the protestor? CDA might have to start over from scratch, on a process that had already taken years.

The prospect of a gap in cloud service was too big a risk for a wait-and-see attitude. “Beth,” Ramona said, “remind me who runs Procurement.”

“Alex Perelman,” Beth said.

“That’s right. I got a nice welcome email from him. Let’s talk to him soon about this and see what we can do to keep this from blowing up in our faces.”

For the final agenda item, Marcus gave the floor to Rick Caldwell, a software applications program manager. This wasn’t the typical forum for discussing software projects, but Rick’s program had implications for infrastructure. In fact, it was such an important program that its success or failure could impact the careers of everyone in the room. Rick was leading the development of RescuePoint.

RescuePoint wasn’t just another software program. It represented the White House’s commitment to restoring public faith in the CDA, and to burnishing the President’s image as a technology-minded leader. Ramona understood the stakes. CDA’s failures during the previous hurricane season had become a national scandal. Hurricane Loretta had devastated coastal communities from Florida to Virginia. Rescue teams were deployed to locations with mild flooding, while stranded families elsewhere waited for help that never arrived. Emergency supplies were cut off from disaster areas, and donated blood sat on the tarmac risking expiration. Media coverage was relentless as the death toll rose.

A congressional inquiry had found that CDA’s antiquated systems were to blame. Video clips of the previous Director stammering through explanations about “technical limitations” had gone viral. Within those explanations lay esoteric information about the data formats that field units were using on decades-old devices, but the headlines were all that most people gathered: CDA’s bad tech had caused people to die.

RescuePoint was the White House’s answer to this challenge: a smartphone application designed to revolutionize emergency response by allowing citizens to request help directly, sharing their precise location and situation details. The White House had announced it with considerable fanfare, promising it would be operational before the upcoming hurricane season.

Ramona wasn’t hired to fix the IT helpdesk. She was hired to restore public trust, and in the 21st Century, public trust in government agencies was increasingly a function of the value and reliability of the digital tools those agencies put in the public’s hands. In the eyes of the new Administration, Ramona’s track record of digital transformation in the private sector made her the perfect candidate to ensure RescuePoint’s successful delivery. Director Mercer had made it clear to her that the White House was watching this project closely.

Rick Caldwell stood up, thanked Marcus, and adjusted his tie. He carried himself with the confidence of someone who had spent decades in government giving briefings just like this one. He knew the drill.

“RescuePoint is progressing on schedule,” he announced, clicking to the next slide. It contained a manually constructed table—individually drawn vertical and horizontal lines, painstakingly spaced to give the appearance of an actual table—filled with green check marks. “The vendor, Valence Digital, has completed the user interface design and backend integration with Axion’s cloud environment.”

Heads nodded around the table.

“According to their latest status report, they’re tracking to meet all milestone deliverables for the quarter.” The next slide portrayed the product roadmap, a sequence of features superimposed over a horizontal timeline. Ramona studied the slide, noting how neatly everything was aligned: every feature in the past was green, every feature in the future in the “planning” phase. The room was filled with a palpable sense that RescuePoint would make them all proud.

“This sounds promising,” Ramona said. “Could we see a demo of what they’ve built so far? I’d like to get a feel for what the everyday user will see.” Ramona’s question came from a place of genuine curiosity; she was aware of RescuePoint because the White House had mentioned it, but few public details were available, and Ramona had had zero exposure to the program until now.

But Rick’s demeanor suddenly shifted. For the first time he could remember, he had no ready-made response to a question. Ramona had worried that her question about protests would make her look like a fool. Instead, it was this one that had everyone in the room furrowing their eyebrows. *Why would anyone ask to see a product before it was finished?*

“Um,” Rick started. “I’m not sure you’d want to see it right now, Ms. Callahan. It still has a lot of quirks to iron out.”

“That’s okay, I’m used to that,” Ramona replied. “It’s really not a problem if it’s not perfect. I just want to see that things are on the right track, with my own eyes.” At Whalen-Cole, the executive training program had included a full day on the management principles taught in Jeffrey Liker’s book *The Toyota Way*. One part of the book had stuck with Ramona for years: a term Toyota calls *genchi gembutsu*. “Go and see for yourself.” So here Ramona was, asking to see for herself.

“Ah, I see. Yes, of course, Ms. Callahan.” Rick’s approach was far more formal than anyone else’s in the room, which was why he’d been put in charge of critical programs like RescuePoint. His military-like respect for authority put senior leaders at ease. “Unfortunately, we can’t demo it today. The product is being developed in Valence’s own environment, which we can’t access from my government laptop.” He adjusted his glasses, still nervous as he navigated his way through unknown territory. “Government staff typically wouldn’t have access to the prototype until it’s complete and staged for live deployment.”

“I see,” Ramona said, her neutral expression disguising her horror at what Rick had just said: they would not be able to see if the vendor had done a good job until that vendor had finished? After said vendor had been working on the system for over a year? “So we haven’t actually seen these features that the deck says are complete?”

“Not directly,” Rick admitted, “but Valence has provided screenshots and detailed documentation.” He clicked to the next slide showing polished mockups of the application. “Their project manager assures me everything is on track.” The mood in the room remained optimistic, with most attendees seemingly satisfied by Rick’s explanation and the gleaming mockups. Nisha Deshmukh, the ACIO for Application Development and Rick’s boss, saw a concerned look in Ramona’s eye and sought to reassure her. “It’s normal for the vendor to develop on their own systems before we can see it,” she said. “We’ll find a way to give you a demo in the coming days without moving the system to our staging environment.”

Ramona gave a quick nod, making a note in her notebook with a bit more force than necessary.

* * *

With the agenda concluded, people began folding their colorful, high-bond, single-use booklets of slides and gathering their things. From the back row along the wall came a voice. It was the same voice that had made the jibe at Marcus’s expense earlier in the meeting. The body from which the voice emitted rose halfway, with a hand raised, and a sheepish head sticking out from behind his neighbor.

“Beth?” the voice said. “Do we still have time?”

“Oh, right!” said Beth. “Sorry, everyone. We have one last-minute addition to the agenda. This just broke last night so we didn’t have time to add it to the slides.” Beth gestured to the man, now awkwardly half-standing, as though waiting for permission to extend his legs fully. “This is Kevin Harper, with the SecureDistribute program.”

Everyone’s eyes turned to Kevin, whose usual conflict-averse demeanor was even more on display today. SecureDistribute was the middleware system that sat behind the benefits portal, moving funds from the CDA’s disaster relief fund to the bank accounts of families who needed the help.

Kevin took a deep breath and gestured to a man who had been standing the entire meeting, leaning casually against the wall with a laptop under his arm and a pencil behind his ear. “Samir Rao is a data scientist on our team, and he has identified some anomalies in our recent transaction history.” Samir’s position in the room—chairless, against the wall—indicated his status in the organizational hierarchy: he was there to be invisible and speak only when spoken to. This was in part because he had a tendency to do the opposite.

Ramona sat back in her chair, prepared for what felt like the beginning of bad news. “What kind of anomalies?”

Kevin’s hesitation gave Samir an opening. “It’s probably easiest if I just show you,” he said to Ramona. It was the first time someone in the meeting had addressed Ramona casually. “It’ll be a lot clearer that way.”

“Actually, Samir,” Kevin interjected, “we try to keep the biweekly ops report at a high level.” His tone was measured but tinged with discomfort. His desire to control this conversation was second only to his desire for it to not exist at all.

For Ramona, the past hour had felt like a fruitless search for detail. Finally, someone was offering it, yet their supervisor was trying to stop them. “You know, I’d like to hear the details,” she said. She gestured for Samir to proceed.

Kevin’s discomfort could be felt by everyone in the room. Samir placed his laptop at the end of the table and turned it to face the others. “I’ve identified a pattern in the disbursement activity,” he said, his voice laid back. “It appears that a user has been defrauding the recovery fund for the past three weeks by filing requests under stolen identities.” His laptop displayed a spreadsheet of the transactions he had labeled as potentially fraudulent.

Ramona looked at Samir. He seemed different than everyone else in the room—his demeanor, his focus, his clothing. He wore a wrinkled shirt, a haphazard attempt to conform to the unofficial dress code without sacrificing comfort.

Ramona leaned forward, squinting at the laptop’s 14-inch display. “What makes you think this is fraud?”

“It’s pretty obvious when you look at the data,” he said. “Here are 73 applications from last week, all of them with different names, but all with the same bank account number.”

“So someone is creating a bunch of bogus accounts and then filing applications for payments en masse?”

“That’s right. And the people’s identities are real. Their names and addresses correlate to a chemical spill in Ohio last year. The grants we’re disbursing replace lost wages, so they’re taxable, and these people will get tax bills for money they aren’t receiving.” Groans filled the room.

“Is there anything we can immediately do to stop this activity?” Ramona asked.

“I already have,” Samir said. “I built a model that proactively identifies these applications—because the fraudster is using the same bank account over and over, he’s made it easy for me—and from there, we pull those payments from the payment file before it goes to Treasury.”

Ramona was getting into a groove with Samir. “How much money can we attribute to this scheme so far?”

“Let me run a quick SQL query and get the exact number.” Ramona was pleased. Details!

The rank and file in the room felt increasingly awkward watching this exchange: Why was the CIO spending her time watching data scientists write SQL queries? And why was she having a one-on-one conversation with a GS-13, while the 13’s manager just sat there, unable to keep up?

Kevin was the first to notice that the scheduled time for the meeting had elapsed. He jumped at the opportunity to end this emasculating experience. “We’re going to have to end it there, as I’m sure Ms. Callahan has a 10:30 to get to.”

“Actually,” said Ramona, her voice upbeat, “we’re getting somewhere. The Director might ask me this very question this afternoon, and I need an answer.”

“We’d be happy to send it to you in an email once the query is done running,” Kevin said.

“I’d rather wait three minutes to see it live than wait four hours for an email,” Ramona said.

No one realized it at the time, but this debate over a paltry detail would prove to be a microcosm of the culture battles Ramona would fight over the coming year.

Everyone was too busy swiveling their heads between Ramona’s and Kevin’s faces to notice when Samir plugged his laptop into the projector so that everyone could see his query results in the command line (not that many people understood it anyway).

“How did you plug that into the projector?” wondered Beth. “I’ve never seen an adapter in these parts.”

“I brought my own from home!” Samir said. “I just got tired of waiting for them to show up, and I knew it might be useful during this meeting.”

At the far end of the table, Tim Krieger bit his lip and put his head down. Plugging your own store-bought device into a government system was a clear security violation, but he remained silent, unsure how to broach the issue in the midst of Samir’s productive exchange with the CIO. But someone else beat him to it:

“Oh, I thought we could only use approved, government-issued adapters,” someone muttered from the far end of the table. The comment sparked a ripple of side chatter from voices that had remained silent until now, threatening to unravel the meeting.

“Yeah, try getting approval for one of those.”

“Rules matter.”

“But if the process for following the rules is broken, what do we expect people to do? Fail at their jobs?”

Ramona took a moment to take this scene in—clearly there was built-up tension here, sparked, it seemed, by a $4 piece of plastic—before nodding at Samir to continue.

“I only have data up through two nights ago, but the total from the transactions that follow this pattern is about $700,000.” Ramona was relieved. Coming from the payment processing sector, she had been steeling herself for a more eye-watering number.

“Because this constitutes criminal activity, we need to notify the Inspector General,” Tim said.

Ramona nodded. “Thank you. Can your team handle that?” Tim shot Ramona a thumbs-up. “Samir, are you confident we’ve put a stop to this?”

“Only kind of. We’ve identified the current pattern only. When this actor stops getting paid, they’ll know we’re onto them, and they might change their behavior.”

“Like using a different bank account?” Ramona asked.

“That’s one easy way,” Tim said, nodding. “This is how fraudsters work: they expend the bare minimum effort in order for the scheme to work, so they can maximize their margin. Once we throw up a defense, they’ll spend just enough money to surmount it, and no more. Then we raise more defenses. It’s a cat-and-mouse game. We can’t make fraud impossible. Our job is to make it *expensive* for them, so they move on to another victim.”

“How do we make it expensive?” asked Kevin, thankful for the opportunity to remind the room of his presence.

“We could add a CAPTCHA to the relief request form,” said Nisha. Her team would be in charge of any changes to a public-facing system. “It’s definitely not iron-clad, but if the fraudster has programmed a bot to submit the forms for him, it will cost him a bit of money to solve the CAPTCHA each time.”

“Great,” said Tim. “That’s unfortunately the best weapon we have right now. Meanwhile, Ms. Callahan, we’ll work on that IG report and send it to you for approval tonight.”

With that, Ramona thanked everyone and ended the meeting, leaving her copy of the printed slides behind. Still with her was the concern about the Axion contract and its role in CDA’s destiny. CDA worked in a world where seconds could make the difference between life and death, and here she was waiting 100 days for Congress to decide whether her new contract could be approved—on top of the years it had already taken to get to this point. If the protest succeeded, her entire infrastructure could be in limbo for the duration of her term.

And if the protest failed? Ramona would be left with an entrenched vendor that had made the agency both technologically and emotionally dependent on its presence. She knew this would be one of her biggest challenges.

* * *

Ramona closed the door to Director Mercer’s office behind her, exhaling a breath she hadn’t realized she was holding. She had wanted to tell him about the fraud as soon as he was available, and she managed to find him alone in his office after the day had ended.

The meeting had gone surprisingly well. Mercer loved hearing that the pattern had been discovered by one of CDA’s own instead of an auditor or journalist. And he loosened up upon hearing the relatively modest sum involved.

“Seven hundred thousand isn’t nothing,” he’d said, “but it could have been much worse. Good catch by your team.”

The Director had been even more enthusiastic about the progress on RescuePoint. When Ramona mentioned they were on track for the hurricane season deadline, he threw up his hands.

“Hallelujah!” he’d said. “The White House has been breathing down my neck about this one. Last year’s failure was...politically uncomfortable. We need this win, Ramona.”

Ramona stepped out of the elevator, stopping by her desk to retrieve her belongings before heading home. The fluorescent lights had gone dark across most of the floor, but Ramona noticed a glow from the data bullpen. Inside, Samir sat alone, surrounded by three monitors. Where most people’s screen real estate was dedicated to Outlook and SharePoint, Samir’s displays were a pile of command line windows, all of them sporting finely tuned bash prompts that transformed the typical white-on-black format to a richly decorated experience reminiscent of an old Atari game. A few empty Diet Dr Pepper cans littered his desk.

“You’re here late,” Ramona said.

He startled slightly. “Oh! Ms. Callahan. Yeah, I’m just running some additional pattern analysis on those fraud cases.”

“Find anything new?”

“Nothing concrete. But I’ve flagged sixteen other claims from the past that have similar characteristics.” He gestured to a cluster of dots on his screen. “We should add a simple bank account-based filter to our back-end transaction script. That’ll keep fraudsters from using the same basic scheme in the future.”

Ramona pulled up a chair. “I just told the Director about your work today. He was genuinely thrilled.”

His face betrayed a bit of pride, but not too much. “Thanks. Though we’re just playing whack-a-mole, of course.”

This was clear to Ramona during the ops briefing. Still, she loved Samir’s candor, and when he talked, ideas flowed. “Tell me more,” she said.

Samir leaned back. This was the point at which most people would choose their words carefully, but in Samir’s world, that only stemmed the flow of ideas. “I’d be surprised if someone hasn’t perpetrated this same scheme in the past. It’s very simple. Adding a filter to watch for repeat submissions using the same bank account? We should have been doing that all along. Adding a CAPTCHA won’t do anything; they are easily surmounted by fraudsters willing to hire a CAPTCHA farm, all while making the application more difficult for legitimate users. Our new guy? He’ll find out soon enough that we’re onto him. And we don’t have the technical capacity to spot his next move. What if his scheme is working on the bank side too, and he has control of multiple bank accounts? He could be using money mules for their account numbers, or something else we haven’t even considered.”

Ramona could tell Samir would talk as long as she let him, so she did.

“We used to have staff on hand who could think through these problems and then implement solutions all on our own,” he continued. “But not anymore. OCIO’s expertise has been hollowed out over the years.”

“Where have they all gone?”

“Two places: the beach, because they’ve retired; and to vendors like Axion, who pay them double the salary to come right back into a government agency and do the same work as a contractor that they had been doing as part of the civil service.”

“What have we done to fill the gap? When people retire, we fill their seats somehow, right?”

“We hire slower than people retire. Right now, about 40% of your whole team is eligible to retire in the next five years.” As he spoke, Samir was busy digging into his files, looking for workforce demographics analyses he had done for the HR team. “Most teams have given up trying to recruit great people from industry. They just post and pray.”

Ramona squinted. “Post and pray?”

“That’s what government HR people call the standard recruiting strategy: we post vacancy announcements to USAJOBS.gov, and we pray that good people find them and apply. No advertising on social media, no deliberate outreach to candidates we want. Absolutely zero effort.”

“Well then…how did you find your way here?”

“Data’s different. About fifteen years ago, everyone was as excited about data as they are today about AI. People were calling data ‘big data’ and dropping the term into every memo in order to sound edgy and innovative. Several federal agencies made a huge push to recruit strong data teams. CDA was one of them. That’s how I ended up here.” Samir waved a hand across the surrounding desks of several other data newcomers. “Now that we have a reputation in the data community, we don’t have to recruit hard anymore. We attract talent just by continuing to do good work that gets noticed.”

“A recruiting flywheel.”

“Right. Like Steve Jobs said: ‘A’ players attract other ‘A’ players. ‘B’ players attract ‘C’ players. Data has A players. But cybersecurity, systems forensics, software development? We’ve been weak in those areas for a long time.” Samir began shutting down his system. “No one from those fields is going to join us with our current recruiting approach, not when we’re competing with tech companies that have armies of recruiters hunting talent.”

Ramona nodded, connecting the dots between recruiting and the vendor dependency on display in the ops meeting. “So not only can we not devise our own solution to this problem. Based on what I heard today, it sounds like our contracts don’t even permit us to touch the relevant systems.”

“They know more about our systems than we do. And they like it that way.” Samir thought for a moment as he created a hypothesis. “I think it’s a self-repeating cycle: we’re dependent on Axion because we don’t have the talent to do the work ourselves, and then once Axion is inside our doors, we don’t have the talent to evaluate their work or hold them accountable. This leads to lower quality of work, which gives us a worse reputation in the eyes of the tech talent market, making it harder for us to recruit, making us more even more dependent on vendors…”

He trailed off and glanced at the door, as if checking for eavesdroppers, before continuing in a lower voice. “Look, I know the recompete for the cloud services is a big deal. People are worried about what happens if Axion loses.”

“You have thoughts on this?” Ramona asked, genuinely curious. She’d found that analysts like Samir often had the clearest view of institutional problems: they had their analytical minds deep in business problems all day, but were far enough removed from the politics to have an objective opinion.

“No matter what, it’s going to be hard,” he said, choosing his words carefully for the first time. “If Axion keeps the contract, we maintain the status quo, and things keep going as they are, not terrible, but not great either. We sink deeper into dependency. Eventually, we’ll be so trapped by them that they’ll start extracting higher and higher fees from us, knowing that we have no choice but to pay them. You *want* to break away from them at some point, and the sooner, the better.”

“Sounds like there’s a ‘but’ there,” Ramona said.

“Yep. Transitioning a major IT services contract like this will be very painful. It has to be planned very carefully. You need to be sure you’re picking a new vendor that’s better than Axion—which is hard to do when we don’t have the right talent to evaluate vendor work—and you need to get full cooperation from Axion, which is also hard to do, because they will have just lost a contract and will have no incentive to help their replacement succeed. Their heads will be on the next business opportunity, not the one they just lost. Then you get a new team learning our systems, temporary degradation of service, maybe even some outages. But at least there’s a chance for actual transformation.”

Ramona sat and digested it all, trying to understand what it meant for her next steps. Samir took her silence as a sign he’d overstepped.

“Apologies if that’s too much to hear on your first day in the office,” he said, gathering his belongings. “Data people aren’t known for our social graces. We just see patterns and report them, for better or worse.”

“Don’t worry about it!” Ramona said, rising from her chair. “I think I’m going to need that forthrightness in this job.”

The two said their goodbyes, and Samir walked out of the data bullpen and to the elevator bank. Ramona sat back down and stared out the window. She looked at her watch. Almost 8 p.m., well past the hour that she expected to leave her new government job. She looked out at the row of federal buildings down the avenue, each of them dotted with several lit-up windows.

Her orientation the previous week had been unremarkable and mostly unmemorable. A series of facts that were presented as a matter of habit, so that the agency could say they had done so, with little engagement or attempt to build rapport or a shared sense of mission: These are your benefits, here is how parking works. But one fact from those days had hit her hard, and it came back to her again as she sat staring out the window at agencies still hard at work. It had come from an HR rep who, in the middle of talking about some mental health service that was part of their health plan, paused her rehearsed script to tell the new employees—Ramona was in a room with 30 or so other newcomers—something important: The frequency of ER visits among CDA employees was up 30% in the past year. Not from the danger associated with rescue operations, but from stress. These were desk workers overwhelmed by the weight of their responsibilities. When she heard the HR rep say this, she took the words seriously, although she believed that, with her cutthroat corporate background, the stress would be nothing new for her. But now, with a plate full of crises after just one day on the ground, she could feel herself bracing for what was to come.
