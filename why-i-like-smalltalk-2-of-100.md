---
title: Why I like Smalltalk: Part 2 of 100 - Intention revealing names
---
# Why I like Smalltalk: Part 2 of 100 - Intention revealing names[^1]

A properly named message communicates well. The developer does not have to look for the implementation. 
This has more to do with design, but it has been in Smalltalk's genes since its inception.

What is an intention-revealing method? 
A message which
- Reveals intention
- Hides implementation
- Gives return type hint	

Intention revealing names answer `what` instead of `how`. 

Let's decide on a name for a method which looks up by a `key` in a `Dictionary`
- `binarySearchByKey:` - Bad, reveals how it works, doesn't hint at return type 
- `searchValueAt:` - Communicates what it does, Good
- `valueAt:` - Able to communicate while being shorter, Better
- `at:` - Best, takes Dictionary in context as key-value pairs

This might seem a very simple pattern, but If you can make this happen in your codebase, you are a god.

[^1]: https://wiki.c2.com/?IntentionRevealingNames
