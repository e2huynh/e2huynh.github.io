# Ethan Huynh, 3rd Year UCSD Student

![This is me](pics/me.jpg)

> I'm built different.  

-Sun Tzu, *Art of War*

### How to find the shortest unweighted path from one vertex to another:
##### C++, BFS
```
while(!found && !q.empty()) {
        string node = q.front().first;
        int dist = q.front().second;
        q.pop();
        if(!visited.count(node)) {
            visited.insert(node);
            unordered_map<string, double> neighbors = adjList[node];
            for(auto entry : neighbors)
                if(!visited.count(entry.first)) {
                    //if the neighbor we are looking at isn't in the map
                    //or if the neighbor is in the map and we reached this neighbor through a shorter path
                    if(!prev.count(entry.first) || (prev.count(entry.first) && dist < prev[entry.first].second))
                        prev[entry.first] = make_pair(node, dist + 1);
                    if(entry.first == end_label) {
                        found = true;
                        break;
                    }
                    q.push(make_pair(entry.first, dist + 1));
                    
                }
        }
}
```

### Top 3 Upper Divison CSE Course (so far)
1. CSE 110
2. CSE 100
3. CSE 130

### Current Life Status:
- [x] Go to college
- [ ] Get intership
- [ ] Get job in the industry

[Part 1 and 2 repository](https://github.com/e2huynh/GitHub-Pages)

[Markdown cheatsheet](https://docs.github.com/en/free-pro-team@latest/github/writing-on-github/basic-writing-and-formatting-syntax#styling-text)

[secret](secret_sauce/secret.md)