### Schema force with Default

We will now make sure that missing values are defaulted to a certain value. From now on, the value of a given property of the schema object will be formed by an object with keys ```"type"``` and ```"default"```. The type-setting system of the previous exercise should work in the same way; with the exeption of the new syntax. If no default key is added then the given property will not be added if missing. If an input is not present or breaking an other of the schema rules, the value will be set to the default.

**Example:**

```jsx
schema = {
    name: {type: "string", default: "NoBody"},
    age: {type: "number"},
    married: {type: "boolean", default: false}
    }
DB = []

model("add", {id: 1, name: "pedro", age: "32", address: "Rue de la Science 23, Brussels")
DB // [{name: "Pedro", married: false}] => married set to default even if missing

model("add", {name: 43, married: "asdfasdf"})
DB /* [
        {name: "Pedro", married: false},
        {name: "NoBody", married: false}] => married and name set to default even wrong type */

model("add", {name: "43", married: true, age: 20})
DB /* [
        {name: "Pedro", married: false},
        {name: "NoBody", married: false},
        {name: "43", married: true, age: 20}] => married and name set to default even wrong type */


```