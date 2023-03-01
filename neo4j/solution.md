# Neo4J Coursework
## Task 0
`MATCH (a)-[r:CONNECTS]->(a) return r`

`MATCH (a) WHERE SIZE([(a)-[:CONNECTS]-(b) WHERE a <> b|1]) = 0 RETURN a`
## Task 1
`CALL gds.graph.create('90266619-communities', 'zone', {CONNECTS: {orientation: 'UNDIRECTED'}}, {relationshipProperties: 'trips'})`

`CALL gds.louvain.stream('90266619-communities', {relationshipWeightProperty: 'trips'}) YIELD nodeId as zone_id, communityId as community_id`

`CALL gds.louvain.stats('90266619-communities', {relationshipWeightProperty: 'trips'})`
## Task 2
`CALL gds.graph.create('90266619-centrality', 'zone', {CONNECTS: {orientation: 'NATURAL'}}, {relationshipProperties: 'trips'})`

`CALL gds.pageRank.stream('90266619-centrality', {relationshipWeightProperty: 'trips', dampingFactor: 0.85}) YIELD nodeId as zone_id, score as centrality_score`

`CALL gds.pageRank.stats('90266619-centrality', {relationshipWeightProperty: 'trips', dampingFactor: 0.85})`
## Task 3
`MATCH (n:zone) RETURN n.id, n.community ORDER BY n.centrality DESC LIMIT 3`

`MATCH (a)-[r:IN]->(b) WHERE NOT b.name='Manhattan' RETURN a.id, a.community ORDER BY a.centrality DESC LIMIT 3`
