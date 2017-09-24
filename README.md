# JSONParser
usage:

```
$ cabal install JSONParser
$ ghci
Prelude> :m + Text.JSONParser Text.Parsec 
Prelude Text.JSONParser Text.Parsec> map (parse parser "") ["{ \"a\t\n\\u007F\" : [true] ,false:{null: -3.2e-5 }}"]
[Right (JObject [(JKeyString "a\t\n\DEL",JList [JSingle (JKeyBool True)]),(JKeyBool False,JObject [(JKeyNull,JSingle (JKeyNum (JNumFraction (-3.2000000000000005e-5))))])])]
```
