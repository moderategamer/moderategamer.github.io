---
layout: default
title: DBContext
---

# EF Core Mental Model

## What is DBContext 
A DBContext is a session that tracks entities, detects change, and saves everything in one transaction.

### Entities are tracked Objects
EF keeps original + current values and knows when something is Modified.

```csharp
  var user = await db.Users.FirstAsync();
  user.Name = "Moderate";
  await db.SaveChangesAsync();
```

Notice how EF was able to track the change to user model automatically before db.SaveChangesAsync() was called.

## LINQ Is translated into SQL
EF builds SQL - it does not run C# in memory 

### LINQ 

```csharp
  var active = await db.Users
      .Where(u => u.IsActive)
      .ToListAsync();

```

### translated SQL

```sql
SELECT * FROM Users WHERE IsActive = 1;
```

## Summary
- **DbContext = Unit of Work** → Tracks entities, detects changes, saves in one transaction.
- **Entities are tracked** → EF stores original/current values and marks Modified automatically.
- **LINQ becomes SQL** → EF translates expressions; avoid `.ToList()` too early.

