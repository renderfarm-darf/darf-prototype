## 🎯 SCATTER_POLICY

Defines how payloads are distributed across available nodes:

| Policy Name     | Description                                              |
|------------------|----------------------------------------------------------|
| `round_robin`    | Distribute jobs evenly across nodes in order             |
| `least_busy`     | Prioritize nodes with fewest active frames               |
| `weighted_random`| Random distribution based on node capacity weighting     |

If no policy is set, `round_robin` is used as the default.

