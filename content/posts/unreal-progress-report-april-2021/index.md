---
title: Empires UE4 Progress, April 2021
author: RoyAwesome
date: "2021-05-02"
post_type: UE4
---


---

## Project Update
###### RoyAwesome

Hey everyone.  It’s been a while since our last update.  My bad. I kinda out for a few months between this project and work, and a healthy amount of seasonal depression, and Empires fell to the wayside.  Progress didn’t really stop, we just kind of stopped writing updates.  Given the all-volunteer nature of our team, this is pretty expected, and my major focus right now is to prevent the project from stalling if I or others burn out.

As I mentioned, it’s not that work stopped.  In the last few months, quite a few people have done some incredible work, and we are incredibly excited to show you what's been going on in the background.

To give a quick overview of the project as it stands right now, there are only 5 programming user stories left in the current milestone, and all of them have had work on them.  For those that aren’t aware of what a user story is, it’s a task entry that describes, as a user, what you will experience in the game.  For example, a user story is “As a player, I can aim down sights with my gun”.  That story gives us an idea what the feature we are creating is, and we can create tasks from it to make that story a reality.  

Right now, the remaining user stories for this milestone are:



*   As a player, I can interact with an ammo container to refill my ammo
*   As a player, when my team hits 0 tickets, they lose the game
*   As a player, I can aim down sights with my gun
*   As a developer, Grenades animate and are general enough to implement mines and throwables
*   As a developer, Bullets can be implemented on the ECS

We should be able to close out these stories by the end of next month, and have Milestone 2 in the bag! 

We’re starting to plan for Milestone 3, and it is my hope that we have a playable test sometime during that milestone’s development cycle.  It will probably be a kind of test weekend, where we test out the technical elements and start getting a feel for how some of the movement and gameplay plays in the UE4 version.  It probably won't have vehicles or commander mode, but we’ll try!

I am starting to search wider for more developers to assist on the project.  Recently, we brought on Dementei, who does level design and materials professionally, and I’m excited to work with him.  We also brought on Oktay and Pred007 to work on game design, like gun feel and balance.   We’ll be looking for more people in the coming months with the goal of accelerating the project and making sure things keep moving.  

---

## Project Compiling
###### RoyAwesome

One of the issues we kept running into was the fact that non-programmer developers would struggle to start the editor the first time.  This was because we use the source code version of the Unreal Engine, which requires Visual Studio and a bunch of other tools to even get it started.  

To solve this, I first set out to create a pre-compiled Unreal Editor, called an Installed Engine Build.  This is how Epic distributes Unreal Engine on their launcher.  Getting the Installed Engine Build to compile was an initial challenge, as I had to make some modifications to the engine’s Steam implementation for our project, and they did not compile in this mode.  After fixing that, I set out on the task of taking the now pre-compiled build and hosting it somewhere.  Big problem: it was 30 gigabytes and it’s hard to find free hosting for that.  

So, instead, I thought maybe it was easier to just write a script to automate compiling the engine, so non-programmers could just run it and it’ll work, no fussing with hosting.  I found out how to call Unreal Build Tool to compile the assorted programs, and now we have a mechanism for people to one-click set up the project with the source code of the Unreal Engine and it’s editor.  

We’ve already put this new process to use onboarding Oktay and Dementei, and it was a major hurdle for bringing new people onto the project that is now solved.    

---

## Gun Recoil
###### RoyAwesome

One of the goals of UE4 Empires is to create a modern Empires game on a modern game engine.  A big part of that is to bring Empire’s gunplay into the modern era, and that involves creating guns that feel interesting to shoot. 

Now, most modern shooters have entire teams of game designers, animators, programmers, and an army of QA to create amazingly feeling guns with controllable recoil and smart cone of fire.  We do not have that.  So, instead we just took the design from Battlefield 3, 4, and Planetside 2, as they all have nearly identical gun design systems.  How different stats go into different guns is extremely well documented for these games, and I was able to create it in just a few days.  

I also made all the recoil values attributes, so not only can we easily modify the recoil and cone of fire values per-gun, we can also modify them with skills and gameplay effects.  This modifiability will be the backbone of the stance system, so we can easily make accuracy get better when crouching or prone.

After creating the system, I handed it off to our designers to make guns feel good, and they are well at work going through all of the guns and making them fun to shoot.  

 <video controls>
  <source src="https://cdn.discordapp.com/attachments/698655659193008208/799509364346978344/2021-01-14_21-23-28.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video> 

---

## Cleanup and Polishing
###### RoyAwesome

Back in December, I showed off Empires to a few people outside of the Empires community.  I wanted to get feedback from people who barely know what Empires is early on so I can be sure that systems like Spawning, Selecting class and Items, and general gameplay systems make sense and are easily expressed to new players.  Of the course of showing it off, I filed like 30 bugs with the current project.  I fixed them all, making the game way more playable and functional.

I also added a Spawn Checklist that shows you what you are missing when trying to spawn.  


{{< image-proc spawnchecklist.png Resize "1100x" >}}

---

## NF Engineer & Grenadier Model
###### Mayama

I finally finished the last two remaining NF infantry high poly models. The engineer and the grenadier. I actually wanted to make the low polys and start to texture those next but we are discussing right now if we want to use UE4’s metahumans to make realistic faces. It would take a bit longer but saves a lot of time in the long run (and I don't need to model faces which is a plus for you and me, trust me). Until that is sorted out I focus on other stuff. The downside is that it doesn't make much sense to low poly anything else and put it into the game before the infantry models are in the engine. You need those to make sure guns don't clip through the model and you need the infantry models as a way to find out how high walls, buildings etc. should be. 

Both models are rather self explanatory, the engineer has some steam-punkish (or diesel punk?) gadgets and a battery pack on his back. The grenadier has an anti explosive vest and those 3 metal stripes are a homage to the source NF soldier model. The beret on the engis head does not 100% look like one but I think it's for the better because the uniform is already kinda real life-ish.

{{< triple-image-thumbnail "NF_engi_big.png" "NF_engi_small_1.png" "NF_engi_small_2.png" >}}

{{< triple-image-thumbnail "NF_gren_big.png" "NF_gren_small_1.png" "NF_gren_small_2.png" >}}

---

## BE Gun
###### Mayama

I started to play around with BE weapon concepts because we need to figure things out before I can low poly the NF soldier models. This is the first concept with which i'm happy. It's a simple SMG model. The design is somewhere between 80ies high tech and 90ies cheap plastic electronics. I wanted to make models that are artistically closer to the “angled stealth fighter look” that BE tanks have than what we have in source empires. The model needs some smaller details, especially the sight and I'm not quite happy with the detail on the shock absorbing stock.

{{< image-proc BE_SMG_concept.png Resize "1100x" >}}

---

## Refactoring Grenades into Throwables
###### RoyAwesome

Late last year, Megafunk prototyped out Grenades, and it was a great initial implementation.  However, in Milestone 3, one of our goals is to have every single infantry item implemented, and while this initial prototype covered simple grenades, I needed it to work with anything that can be thrown.  

So I refactored it into a “Generic Throwable” system.  Now it supports Grenades and Mines, as well as a C4 type that I plan on creating and finding a use for in the game.  

I also added tweakable attributes and hooked up animations, as well as more mechanics like Holding a grenade throw and sticky grenades.  Mines will come in the next milestone, but they should be pretty quick to implement.  

 <video controls>
  <source src="https://cdn.discordapp.com/attachments/698655659193008208/836845413532434462/2021-04-27_23-04-24.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video> 


 <video controls>
  <source src="https://cdn.discordapp.com/attachments/698655659193008208/837949328441868288/2021-05-01_00-11-03.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video> 


 <video controls>
  <source src="https://cdn.discordapp.com/attachments/698655659193008208/837859254995779594/2021-04-30_18-12-55.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video> 

---

## Ammo and Resupply
###### RoyAwesome

Ammo and Health boxes are an important part of Empires, and resupply was an important part of milestone two.  Since we use Unreal Engine’s Gameplay Ability System and Ammo is an attribute, resupplying ammo is relatively trivial.  So, I took the imported ammo box mesh and made it apply a gameplay effect to refill ammo.  

Once the basic ammo supply is in, health resupply was also pretty straightforward.  

All that remains now is to refill guns that aren’t active, and make sure we only resupply people on the same team to use the box.
