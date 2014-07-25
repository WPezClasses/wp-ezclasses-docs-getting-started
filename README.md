WPezClasses
===========

Getting Started: 0.0.2
======================

Alpha / Draft - That is, there could be typos, misspellings, etc.
-----------------------------------------------------------------

###Overview

WPezClasses is an OOP-based WordPress framework that aims to make WP development ez (or at least easier). At 50,000 feet
it's simply a series of classes that you might use, just as you use the traditional WP framework. That is, once in place
WPezClasses is just there. Waiting. 

Naturally, there is a bit of (short term) setup involved in order to fully benefit from the (long term and ongoing) reduction in friction. 
This document will walk you though the setup, as well as answer any other questions you might have. If we missed something you can use: faq.gh [at] wpezclasses.com


=========================================================================================================


1."Why should I care? What's in it for me?"
-------------------------------------------

That's a great question. And always the first question asked when someone is trying to sell you something new. We understand. Thanks for asking. 

But before we get to that, let's discuss who you are and how you're probably using Wordpress. 

+ You are: At least somewhat experienced building WP themes and/or WP plugins.
+ You are: Comfortable with the basics of PHP OOP. 
+ You do: Mostly custom WP development and WP customization, as opposed to themes and plugins (either premium or for the WP.org repos)*.
+ You have: Experienced time-sucks from hell trying to find meaningful answers and The Google and The Bing are of little help**.
+ You have: Planted open palm to forehead and said, "There's got to be a better way."


> * Important - Please Note: The WPezClasses framework on whole is not intended to be used in free-standing themes and plugins.
> With that said, it's certainly possible to fork a given class, refractor it (i.e., change the name and such) and incorporate it 
> into your project. Please, feel free. Just understand we're not going to be able (or willing) to support things. 


> ** TODO Coming soon: WordPress.SnippetSearch.com



2. "I'm still here. So what about question #1?"
-----------------------------------------------

Okay. Okay. These are the major benefits / features of using WPezClasses:

+ Modularity - Each class aims to solve *a* WP problem. Ideally bloat and over-ambitiousness is mitigated as much as possible. 
+ Productivity - Rather than reinventing wheel after wheel, you just reach into your WPezClasses toolbox and make some magic happen. 
+ Community - As others contribute new code and/or vet current code, the product gets bigger, stronger and more reliable for everyone. 
+ Growth - The potential here is endless. Getting on board now means more time saved sooner. And if you don't do it your competition might. 
+ Mindlessness - For all practical purposes WPezClasses acts and feels as if it's part of WP core. It's just there: 24 / 7 / 365 loving you unconditionally. 


Here are some more bits that hopefully excite you:

+ Granular - We consider each class to be its own sub-product, and therefore has it's own repo. Clone what you want, leave what you don't, come back for more some other time. 
+ Consistency - Atypical as some of them might be, the coding patterns make sense and are easy to follow.
+ Death - Along the same lines as Mindlessness; putting "...and copy and paste it into your functions.php" to death would be a giant step forward. 
+ Flexibility - It's all OOP. If there's a method you don't like then exend the class and overide it. You don't have to copy & paste whole chunks of someone else's code just to change a couple lines.  
+ Open Source - We hope you stay and help, but if you fork it that makes us feel good too. 

> FYI: The objective of WPezClasses isn't to solve every problem, in full, for every possibility, all the time. It's a framework, not a religious experience. 
> Success is defined as saving 10% to 20% in dev time and ongoing maintence. That might not sound like much, but when doing bespoke WP work, that's half 
> a day to a whole day per week. The more time WPezClasses saves you, the more time you'll have for anything else.



3. "Sounds good so far. How do I get started?"
----------------------------------------------

This the recommended approach to using WPezClasss. 

> * Important - Please Note: Given the modular / granular approach there are probably workable variations. Any of those are up to you. We prefer to lean 
> on consistency. For example, you could "manually" do the include() / require() for each class but that's a pain in the ass. You also don't then benefit from 
> spl_autoload (http://php.net/manual/en/function.spl-autoload.php).

+ Install / clone: https://github.com/WPezPlugins/wp-ezmu-plugins. 

> * Important - Please Note: The mu-plugins folder is used because it let's us load WPezClasses before anything else. Be sure to follow the instructions that come along with this repo. 
> FYI: http://codex.wordpress.org/Must_Use_Plugins

+ As a mu-plugin install / clone: https://github.com/WPezPlugins/wp-ezclasses-autoload.

> Within the folder mu-plugins / wp-ezclasses/ *eventually* you're going to need a parent folder for each (classes) grouping (e.g., admin, ctp, etc.). 
> We'll explain this in detail shortly. For now just continue...

+ Within the wp-ezclasses folder install / clone: https://github.com/WPezClasses/ezcore.

> FYI: ezCore are the most frequently used dependencies. Originally, these were "optional" but that didn't make sense when some were used so often (e.g., method-static).

+ Install / clone: https://github.com/WPezClasses/wp-ezclasses-master-singleton.

+ In the end you should have the follow folder structure:

-- mu-plugings

---- wp-ezclasses

------ ez-core

-------- class-wp-ezclasses-ezcore-conditional-tags

-------- class-wp-ezclasses-ezcore-devtools-log

-------- class-wp-ezclasses-ezcore-methods-static

-------- class-wp-ezclasses-ezcore-wp-enqueue

---- wp-ezclasses-autoload

---- wp-ezmu-plugins

---- wp-ezclasses-master-singleton


> Important - Please Note: We hear you grumbling. This bit could probably be simplified but we fear there would then be a loss of granularity and (you having total) control. 
> It's a one-shot deal that in total shouldn't take you longer than 30 to 45 minutes. The benefit is worth it. Once all this is in place, it's just a question
> of adding more repos / classes in the correct parent folders. 



4. "Okay. It took me closer to an hour but everything is in place. Now what?"
-----------------------------------------------------------------------------

Great. Glad to hear you've made it this far. Now let's do a quick example.

+ Add a folder under wpezclasses called: admin. This folder is a sibling of the ezcore folder.

+ Wihin the admin folder install / clone: https://github.com/WPezClasses/class-wp-ezclasses-admin-ui-cleanup-1-presets-1.

+ Wihin the admin folder install / clone: https://github.com/WPezClasses/class-wp-ezclasses-admin-ui-cleanup-1.

+ In your regular plugin folder install / clone: https://github.com/WPezPlugins/wp-ezplugins-admin-ui-cleanup-1. 

> Important - Please Note: Before you activate the plugin have a look at the plugin's code. Notice how much is NOT in the plugin. Now have a look at the two classes
> you installed / cloned into the wp-ezclasses / admin folder. 

+ In the end you should now have the follow folder structure:

-- mu-plugings

---- wp-ezclasses

------ ez-core

-------- class-wp-ezclasses-ezcore-conditional-tags

-------- class-wp-ezclasses-ezcore-devtools-log

-------- class-wp-ezclasses-ezcore-methods-static

-------- class-wp-ezclasses-ezcore-wp-enqueue

------ admin

-------- class-wp-ezclasses-admin-ui-cleanup-1-presets-1

-------- class-wp-ezclasses-admin-ui-cleanup-1


---- wp-ezclasses-autoload

---- wp-ezmu-plugins

---- wp-ezclasses-master-singleton



5. "Wait. Sorry. I don't get it. Help?"
---------------------------------------

No problem. Here's the deal:

Think of class-wp-ezclasses-admin-ui-cleanup-1-presets-1 as the "fuel". It's the setting for series of commonly used filters and actions for cleaning up the Admin UI. For example, 
remove the Yoast SEO stuff. The idea is to get rid of "How do I do that again?" or "Where did I put that snippet?" 

>> No offense Yoasty. It's just that the issue comes up often enough that we wanted to make it ez for people to adjust such things to their own liking / project / client.

Now think of class-wp-ezclasses-admin-ui-cleanup-1 as the "engine". It takes the fuel and executes / implements the various setttings as defined in class-wp-ezclasses-admin-ui-cleanup-1-presets-1's method admin_ui_cleanup_presets_combinations().

Actually, using a combinations settings from (the method) admin_ui_cleanup_presets_combinations is optional. You could set up you own array and feed it to class-wp-ezclasses-admin-ui-cleanup-1. The
combos are there to reduces repeating something you've probably don't before. Keep in mind, you can come up with your own sets of combos for yourself, or in a pull request. 

> Important - Please Note: This approach is something that's common to the WPezClasses mindset. Quite often in WP dev we're just calling functions. For example, wp_enqueue() is just
> a function. So why not just maintain a list(s) of possible settings and pick and choose what you need, as you need it? The settings are static. No more typing and retyping. No
> more copy & paste. Instead, it's now "Use these...".   

And finally, there's the plugin wp-ezplugins-admin-ui-cleanup-1. This is where you call the other two classes. This is where you can quickly and easily configure a custom UI Cleanup
on a project by project basis. 

Could we / you build a UI for this? Yeah, probably. But in the case of "set it once and forget it" type things a UI is overkill. It's bloat. Instead, the code is tucked into a plugin. 
You know where to find it if you need. You make a quick adjustment if necessary. Done. Less code (i.e., UI) means less stuff to go wrong. 



6. "Wow. That's pretty cool. But what's up with the long class names?"
----------------------------------------------------------------------

Another great question. Glad you asked. Mainly it has to do with spl_autoload() and using the class name (parsed) as a means to assist spl_autoload().

As an example, let's use class-wp-ezclasses-admin-ui-cleanup-1. 

Here's the segment by segment breakdown:

+ class - A WP coding standard requirement. FYI: http://make.wordpress.org/core/handbook/coding-standards/php/. We do try to stick with these, mostly. 

+ wp-ezclasses - A unique identifier (of sorts) that tells the autoload plugin "This one's for you!".

+ admin - The name of the subfolder under the wp-ezclasses parent folder where the class will be found. A single folder with a mess of .php files and such would be too messy. 

+ ui-cleanup-1 - Finally, (more of less) the name of the class (sans the previous necessities) that make it unique. 



7."Why don't you use Git submodules?"
--------------------------------------

That was considered but then ruled out for a number of reason. Mainly because most people are probably not familiar with them. 

Instead, we stuck with KISS. Yes, it added a bit of overhead, but it also maintained the ideal of giving you as much control as reasonable possible. 

Link: http://www.git-scm.com/book/en/Git-Tools-Submodules

