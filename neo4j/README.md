# Neo4j stuff

Cypher DB Stats:

```
MATCH (n) WHERE rand()<.1
MATCH (n)-[r]->(m)
RETURN labels(n), size((n)--()) AS dn, type(r), labels(m), size((m)--()) AS dm
```






