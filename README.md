# Ethan Huynh's GitHub Page
## 3rd Year UCSD Student

How to find the shortest unweighted path from one vertex to another:
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