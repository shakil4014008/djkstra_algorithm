# djkstra_algorithm


````Python
 #Function to find the shortest distance of all the vertices; from the source vertex S.
    
    def dijkstra(self, V, adj, S):
        #code here
         # [2 for i in range(5) == [2, 2, 2, 2, 2]]
        result = [float('inf') for node in range(V)] 
        q  = [S] # start the queue using S source
        result[S] = 0 # dist of S  = 0
       
        while q: # keep working until the queue is empty
            node  = q.pop() 
            
            # [[1, 9]] -- node, weight; neighbor of pop node adj list.
            for nei, w in adj[node]: 
                # the node which is popped, and current edge w
                if result[node] + w < result[nei]: 
                    result[nei] = result[node] + w 
                    # for each neighbor node from source, add in queue if new update
                    q.append(nei) 
        return result
````
