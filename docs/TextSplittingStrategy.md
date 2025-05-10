# TextSplittingStrategy

`SENTENCE_DISAMBIGUATION` works only for english language and splits the input text into sentences using a linguistically aware sentence boundary detection algorithm, example `Mr.Kay`, `name@email.com`, `https://www.website.com` will not be split on period.<br><br> `SENTENCE_DELIMITER` splits on period (.), exclamation (!) and question (?), regardless of where they are found.

## Enum

* `SENTENCE_DISAMBIGUATION` (value: `'SENTENCE_DISAMBIGUATION'`)

* `SENTENCE_DELIMITER` (value: `'SENTENCE_DELIMITER'`)

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


