# Migration

*Last updated: YYYY-MM-DD HH:MM*

*Only if there's existing data or an existing app to move from.*

---

## What exists now

<A spreadsheet? An old app? A database? Where is it, what shape is it in?>

## How much

<Rows, files, size. This decides whether it's a one-off script or a real job.>

## What comes over

| From | To | Notes |
|---|---|---|
| | | |

## What doesn't come over

<And what happens to it. Deleted? Archived? Left where it is?>

## Things that won't fit

<Data in the old thing that has nowhere to go in the new one. Every migration
has some. Decide now, not halfway through.>

## The plan

1. Copy the old data somewhere safe first. Never work on the only copy.
2. Move a handful of rows. Check them by hand.
3. Move the rest.
4. Check the counts match.
5. Keep the old copy for <how long> before deleting anything.

## If it goes wrong halfway

<Can it be run again safely? Does it need to be undone first?>

Rule: the migration must be safe to run twice. If running it twice doubles
everything, it isn't finished.
