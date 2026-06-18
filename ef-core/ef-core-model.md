---
layout: default
title: DBContext
---

[← Back to EF Core]({{ '/ef-core/' | relative_url }})

#Build the EF Core Mental Model

##What is it?
The Ef Core mental model is built on four pillars
- The DB Context (a unit of work)
- Entities are tracked data, not just data
- LINQ is translated into SQL, not executed in memory
- Navigation properties define the shape of your relational world

##Why it matters?
Once you understand these four pillars, EF stops being magic

# DB Context

## Think of the DB Context as
- A session with the database
- A change tracker
- A query translator
- A transaction boundary 
it's not just a connection!

## DBConext does three things
- Tracks entities, it remembers every entity you load or attach
- Detects changes, it knows what properties have changed since loading
- Saves changes as a single transaction, All inserts/updates/deletes happen together

#Why this matters?
If you understand that the DBontext is a session, you undestand:
- why you don't use "using" in a REST API
- why you shouldn't keep the context alive too long
- why EF knows what to update without telling you
