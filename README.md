# Event

Easily define event types for an `EventTarget`. Credits to [this article](https://dev.to/marcogrcr/type-safe-eventtarget-subclasses-in-typescript-1nkf).

## Getting started

The following program defines `play` and `stop` events.

```ts
import { TypedEventTarget } from "@hydroper/event";

class MediaPlayer extends (EventTarget as TypedEventTarget<{
    play: CustomEvent<MediaPlayerEvent>;
    stop: CustomEvent<MediaPlayerEvent>;
}>) {}
```

> Note that event types must implement the `Event` interface, thus in the previous program `CustomEvent` is used; if there was no data, it could have just been `Event` itself.