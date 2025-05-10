# CombiningStrategy

`SLIDING_WINDOW` groups sentences using a fixed-size window of consecutive sentences to create overlapping combined units. As the window slides forward one sentence at a time, it ensures smoother semantic transitions between chunks by maintaining context continuity.<br><br> `TUMBLING_WINDOW` groups sentences into fixed-size, non-overlapping combined units. Each group of sentences is used once without overlap, providing distinct, separate segments for comparison.<br><br> `ADJACENT_LINES` groups sentences with a fixed number of sentences before and after and moving one sentence ahead at a time. It creates overlapping combined units where each unit centers around a specific line, including a fixed number of neighboring lines as context.

## Enum

* `SLIDING_WINDOW` (value: `'SLIDING_WINDOW'`)

* `TUMBLING_WINDOW` (value: `'TUMBLING_WINDOW'`)

* `ADJACENT_LINES` (value: `'ADJACENT_LINES'`)

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


