# Learnings tag map

Just an easy way to group all the learnings by tag and on which files they appear.

Use it to gather all the learnings about a topic and create new notes based on that knowledge.

```dataview 
TABLE WITHOUT ID Tags AS "Tag", rows.file.link AS "Files" 
FROM #learnings 
FLATTEN file.etags AS Tags 
WHERE contains(Tags, "#learnings/") 
GROUP BY Tags SORT Tags ASC
```