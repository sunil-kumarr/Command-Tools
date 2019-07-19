# JQ: JSON COMMAND LINE TOOL  
----------------------------------------
1. **Sort JSON based on a key:** [JQ Tutorial](http://bigdatums.net/2016/11/29/sorting-json-by-value-with-jq/)
Sorting JSON by value with jq can easily be done by using the sort_by() function. The main trick with using the sort_by()    function is that your JSON input must be in an array. There are different ways to do this in jq (if your data is not already like this), including using the -s or --slurp option. The --slurp option will read all JSON input into a JSON array. From this point the data can be sorted by value. You can use the .[] syntax to return all elements of the array.

    * `cat  filename.json | jq -s -c 'sort_by(.session_id) | .[]'`
   
2. **Get value for a specific json key using jq:** 

    * `jq .key filename.json`

3. **Get values from multiple json files for a specific key:**

    * `jq .key  file1.json file2.json file3.json`

4. **Get Difference for values of a specific key from 2 files:**
    * `diff  <(jq .mobui logs_8_h.json ) <(jq .mobui log8_hs.json)`
    * `vimdiff  <(jq .mobui logs_8_h.json ) <(jq .mobui log8_hs.json)`

5. **For better diff use multiple diff option as:**
    * `diff -u --color  <(jq .mobui logs_8_h.json ) <(jq .mobui log8_hs.json)`

6. **Get line by line comparision for values for a specific key from 2 files:**
    * `cmp  <(jq .mobui logs_8_h.json ) <(jq .mobui log8_hs.json)`

7. **Sort Json input based on a key && Get difference for a specific key:**
    * `diff -u --color <(jq .mobui <(jq -s -c 'sort_by(.session_id) | .[]'  logs_session7)) <(jq .mobui <(jq -s -c 'sort_by(.session_id) | .[]' logs_session8))`

8. **Get Comparsion line based for a specific key in json:**
    * `cmp  <(jq .mobui <(jq -s -c 'sort_by(.session_id) | .[]'  logs_session7)) <(jq .mobui <(jq -s -c 'sort_by(.session_id) | .[]' logs_session8))`
