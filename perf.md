# Linux Perf-Events

#### monitor top-N CPU usage
```perf record -F 99 -p `pidof mongod` -g -- sleep 20```

#### monitor context-switching
```perf record -e cs -g -p `pidof mongod mongos` sleep 5```

### References
- https://perf.wiki.kernel.org/index.php/Tutorial
- http://article.gmane.org/gmane.linux.kernel.perf.user/770/match=perf+lock  & http://comments.gmane.org/gmane.linux.kernel.perf.user/1524
- http://thread.gmane.org/gmane.comp.version-control.git/172286 : debug git gc with perf
- http://mechanical-sympathy.blogspot.co.uk/2012/08/memory-access-patterns-are-important.html -- memory access pattern

# /proc
#### to watch stats file change
```watch -tdn1 cat /proc/`pidof mongod`/status```

#### to watch interrupts changes, for context switching
```watch -tdn1 cat /proc/interrupts```
