WPezClasses
===========

Getting Started: 0.0.1
======================

Alpha / Draft - That is, there could be typos, misspellings, etc.
-----------------------------------------------------------------


WPezClasses is an OOP-based WordPress framework that aims to make WP development ez (or at least easier).

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

Okay. Okay. These are the benefit / features of using WPezClasses:

+ Modularity - Each class aims to solve *a* WP problem. Ideally bloat and over-ambitiousness is mitigated as much as possible. 
+ Granular - We consider each class to be its own sub-product, and therefore has it's own repo. Clone what you want, leave what you don't, come back for more some other time. 
+ Consistency - Atypical as some of them might be, the coding patterns make sense and are easy to follow.
+ Extendability - It's all OOP. If there's a method you don't like then overide it (while you leave the rest of the class intact). 
+ Community - As others contribute new code and/or vet current code, the product gets bigger, stronger and more reliable for everyone. The potential here is endless. 
+ Productivity - Rather than reinventing wheel after wheel, you just reach into your WPezClasses toolbox and make some magic happen. 
+ Mindlessness - For all practical purposes WPezClasses acts and feels as if it's part of WP core. It's just there: 24 / 7 / 365 loving you unconditionally. 
+ Open Source - We hope you stay and help, but if you fork it that makes us feel good too. 


> FYI: The objective of WPezClasses isn't to solve every problem, in full, for every possibility, all the time. It's a framework, not a religious experience. 
> Success is defined as saving 10% to 20% in dev time and ongoing maintence. That might not sound like much, but when doing bespoke WP work, that's half 
> a day to a whole day per week. The more time WPezClasses saves you, the more time you'll have for anything else.



3. "Sounds good so far. How do I get started?"
----------------------------------------------

This the recommended approach to using WPezClasss. 

> * Important - Please Note: Given the modular / granular approach there are probably workable variations. Any of those are up to you. We prefer to lean 
> on consistency. For example, you could "manually" do the include() / require() for each class but that's a pain in the ass. You also don't then benefit from 
> spl_autoload (http://php.net/manual/en/function.spl-autoload.php (http://php.net/manual/en/function.spl-autoload.php)).

+ Install / clone: https://github.com/WPezPlugins/wp-ezmu-plugins. 

> The mu-plugins folder is used because it let's us load WPezClasses before anything else. Be sure to follow the instructions that come along with this repo. 

+ As a mu-plugin install / clone: https://github.com/WPezPlugins/wp-ezclasses-autoload.

> Within the folder mu-plugins / wp-ezclasses/ *eventually* you're going to need a parent folder for each (classes) grouping (e.g., admin). 
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


> Important - Please Note: We hear you grumbling. This bit could probably be simplified but we fear there would then be a loss of granularity and control. 
> It's a one-shot deal that in total shouldn't take you longer than 30 to 45 minutes. The benefit is worth it. Once all this is in place, it's just a question
> of adding more classes in the correct parent folders. 



4. "Okay. It took me closer to an hour but everything is in place. Now what?"
-----------------------------------------------------------------------------

Great. Glad to hear you've made it this far. Let's do a quick example.

+ Add a folder under wpezclasses called: admin.

+ Wihin the  admin folder install / clone: https://github.com/WPezClasses/class-wp-ezclasses-admin-ui-cleanup-1-presets-1.

+ Wihin the  admin folder install / clone: https://github.com/WPezClasses/class-wp-ezclasses-admin-ui-cleanup-1.

+ In your regular plugin folder install / clone: https://github.com/WPezPlugins/wp-ezplugins-admin-ui-cleanup-1. 

> Important - Please Note: Before you activate the plugin have a look at the plugin's code. Notice how much is NOT in the plugin. Now have a look at the two classes
> you installed / cloned into the wp-ezclasses / admin folder. 



5. "Wow. That's pretty cool. But what's up with the long class names?"
----------------------------------------------------------------------

Another great question. Glad you asked. Mainly it has to do with spl_autoload() and using the class name as a means to assist spl_autoload().

As an example, let's use class-wp-ezclasses-admin-ui-cleanup-1. 

Here's the segment by segment breakdown:

+ class - A WP coding standard requirement. (TODO: link to page in Codex).

+ wp-ezclasses - A unique identifier (of sorts) that tells the autoload plugin "this one!".

+ admin - The name of the subfolder under the wp-ezclasses parent folder where the class will be found.

+ ui-cleanup-1 - Finally, the name of the class (sans the previous necessities). 
