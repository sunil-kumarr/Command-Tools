# JQ: JSON COMMAND LINE TOOL  [JQ Github](https://stedolan.github.io/jq/manual/)
----------------------------------------
1. **Sort JSON based on a key:** [JQ Tutorial](http://bigdatums.net/2016/11/29/sorting-json-by-value-with-jq/)
Sorting JSON by value with jq can easily be done by using the sort_by() function. The main trick with using the sort_by()    function is that your JSON input must be in an array. There are different ways to do this in jq (if your data is not already like this), including using the -s or --slurp option. The --slurp option will read all JSON input into a JSON array. From this point the data can be sorted by value. You can use the .[] syntax to return all elements of the array.

    * `cat  filename.json | jq -s -c 'sort_by(.key1) | .[]'`
   
2. **Get value for a specific json key using jq:** 

    * `jq .key filename.json`

3. **Get values from multiple json files for a specific key:**

    * `jq .key  file1.json file2.json file3.json`

4. **Get Difference for values of a specific key from 2 files:**
    * `diff  <(jq .key file1.json ) <(jq .key file2.json)`
    * `vimdiff  <(jq .key file1.json ) <(jq .key file2.json)`

5. **For better diff use multiple diff option as:**
    * `diff -u --color  <(jq .key file1.json ) <(jq .key file2.json)`

6. **Get line by line comparision for values for a specific key from 2 files:**
    * `cmp  <(jq .key file1.json ) <(jq .key file2.json)`

7. **Sort Json input based on a key && Get difference for a specific key:**
    * `diff -u --color <(jq .key2 <(jq -s -c 'sort_by(.key1) | .[]' file1.json)) <(jq .key2 <(jq -s -c 'sort_by(.key1) | .[]' file2.json))`
    or 
    * `diff -u --color  <(jq -s -c 'sort_by(.key1) | .[] | .key2 ' file1.json) <(jq -s -c 'sort_by(.key1) | .[] | .key2' file2.json)`


8. **Get Comparsion line based for a specific key in json:**
    * `cmp  <(jq .key2 <(jq -s -c 'sort_by(.key1) | .[]' file1.json)) <(jq .key2 <(jq -s -c 'sort_by(.key1) | .[]' file2.json))`
    
9. **Creating new JSON from array of JSON: [{},{},{}] -> [{}] [Link](https://programminghistorian.org/en/lessons/json-and-jq)**
    * `js -s -c ' .[ ] | { newkey1: .key1 , newkey2: .key2}' filename.json`



