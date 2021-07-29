# datawarp
### by Alex Merced

The datawarp library allows you to pass data in and out scopes where it may be difficult to pass data. Works similar to "context" in React but can be used in any framework or with no framework at all.

*NOTE* This library is of type module so may not work with older versions of node.

## How does it work

1. Create a sender and receiver

You can change the name of the two functions, but the sender is always the first item and the receiver is always the second item in the array returned by datawarp().

```js
import {datawarp} from "datawarp"

export const [sender, receiver] = datawarp()
```

2. Send data

User sender at any point to update the data it is sending

```js
import {sender} from "..."

sender({mode: "dark"})
```

3. Receive data

Invoke receiver to receive the most recently sent data, that's it!

```js
import {receiver} from "..."

const settings = receiver()

if (settings.mode == "dark"){

}
```