## Static analysis that reads a repository's git history instead of its source.

**Live at [debtzero.dev](https://debtzero.dev)** · Kotlin · Spring Boot

---

## What it does

Most static analysis looks at code as it is today. debtzero looks at how the
code got there. Churn, authorship and change patterns across a repository's
history show things a snapshot can't: which files keep breaking, which files
are quietly tied together, and which parts of the system only one person
understands.

### It reports four things.

**Hotspots** — files ranked by how often they change, weighted against how
complex they are. A complex file nobody touches isn't urgent. A complex file
that changes every week is where the time goes. The score follows Adam
Tornhill's method: `log(1 + churn) × complexity`.

**Co-change coupling** — files that keep getting committed together. When two
files change in tandem with no visible dependency between them, that's a
hidden coupling, and it's the kind that breaks when someone edits one and
forgets the other.

**Knowledge concentration** — how authorship is spread across each file. A
file with a single author is a bus-factor risk; this shows where those sit.

**TODO age** — how long each TODO has survived, dated from the commit that
introduced it. A TODO from three years ago isn't a plan.

---

## Screenshots

(coming soon...)

