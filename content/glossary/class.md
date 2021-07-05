---
title: "Class"
date: 2021-06-20T21:37:46-07:00
draft: false
tags:
    - language construct
    - language design
    - oop
short: Related to object-oriented programming. A way to bind data to actions.
resources:
    - { url: https://simple.wikipedia.org/wiki/Class_(programming), name: Wikipedia }
    - { url: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes, name: MDN }
---

Related to [object-oriented programming](/glossary/object-oriented-programming). A class is a language construct that allows binding data to methods.

## Example

Below is an example class for a game, written in [Kotlin](https://kotlinlang.org/). In this example, QuestService handles responsibilities related to questing. The class initializes with a list of possible quests. Most [methods](/glossary/method) scope to a PlayerMob, meaning those particular methods concern only a single player's quests.

```kotlin
class QuestService(private val quests: List<Quest>) {
    fun findByType(type: QuestType): Quest? {
        return quests.find { it.type == type }
    }

    fun getAcceptableQuestsForMob(mob: PlayerMob): List<Quest> {
        return quests.filter {
            val notSatisfied = it.acceptConditions.find { req -> !req.doesSatisfy(mob) }
            !mob.quests.containsKey(it.type) && notSatisfied == null
        }
    }

    fun getAcceptedQuestsForMob(mob: PlayerMob): List<Quest> {
        return quests.filter { 
            mob.quests.containsKey(it.type) 
                && mob.quests[it.type]?.status != QuestStatus.SUBMITTED 
        }
    }

    fun getSubmittableQuestsForMob(mob: PlayerMob): List<Quest> {
        return quests.filter {
            val notSatisfied = it.submitConditions.find { req -> !req.doesSatisfy(mob) }
            mob.quests.containsKey(it.type) && notSatisfied == null
        }
    }

    fun submit(mob: PlayerMob, quest: Quest) {
        mob.quests[quest.type]?.let {
            it.status = QuestStatus.SUBMITTED
        }
        reward(mob, quest)
    }

    fun accept(mob: PlayerMob, quest: Quest) {
        mob.quests[quest.type] = QuestModel()
    }

    fun abandon(mob: PlayerMob, quest: Quest) {
        mob.quests.remove(quest.type)
    }

    fun reward(mob: PlayerMob, quest: Quest) {
        quest.rewards.forEach {
            RewardService(mob).award(it)
        }
    }

    fun getLog(mob: PlayerMob): List<Quest> {
        return quests.filter { mob.quests[it.type] !== null }.sortedBy { it.level }
    }
}
```

When considering the definition at the top of the page, the quests passed in to QuestService on line 1 are the data being bound to the class, and each method either operates on the bound data or on an argument passed in to it.
