# Unity Events Framework
<img src="https://github.com/DevsDaddy/UnityEventFramework/blob/main/DevsDaddy/Shared/EventFramework/Preview.png?raw=true" alt="Unity Event Framework" style="width: 100%" /><br/>
**Unity Event Framework** is a simple and elegant way to handle events between your objects in Unity. 
The framework uses the PubSub pattern with current Payload states for easy access to previously sent events.

<a href="https://github.com/supermax/pubsub/tree/master">Inspired by the work of SuperMaxim</a>

## Why is that necessary?
There are several advantages to this approach, ranging from reducing cohesion in your project by not directly referencing objects to resolving asynchronous events within the project. You can also retrieve the state of an event at any time if it has been previously sent.

## Get Started
**Installation process:**
- Download and import <a href="https://github.com/DevsDaddy/UnityEventFramework/releases">latest release from this page</a>;
- See <a href="#usage">usage examples below</a>;

**Or add this URL to UPM:**
```
https://github.com/DevsDaddy/UnityEventFramework.git?path=/DevsDaddy/Shared/EventFramework/
```

## Usage
**Create Payload (Event Model) for your Events:**
```csharp
public class TestPayload : IPayload
{
    public string Message = "";
}
```

**To Subscribe for Payload (event) you can add listener via EventMessenger Class:**
```csharp
EventMessenger.Main.Subscribe<TestPayload>(payload => {
    Debug.Log(payload.Message);
});
```

**To Publish New Payload (Event) you can:***
```csharp
EventMessenger.Main.Publish(new TestPayload {
    Message = "Hello world!"
});
```

**Also you can get latest state for any early published payload (or null if not published yet):***
```csharp
TestPayload currentPayload = EventMessenger.Main.GetState<TestPayload>();
Debug.Log(currentPayload.Message);
```

## Examples
See framework usage examples in other projects:
* <a href="https://github.com/DevsDaddy/GameShield">Game Shield - Unity Game Security and Anti-Cheat Toolkit</a>;
* <a href="https://github.com/DevsDaddy/UIFramework">Simple UI Framework for management of your UI</a>;
* <a href="https://github.com/DevsDaddy/OneUIKit">OneUI Kit - Full-featured UI Kit for your applications and Games. Ready for MVC/MVP/MVVM</a>;

## Coming Soon (TO-DO)
**I plan to add the following functionality in the near future:**
- Reactive Fields with Auto-Resolving via EventMessenger Class;

## Join Community
- <a href="https://discord.gg/xuNTKRDebx">Discord Community</a>
- <a href="https://boosty.to/devsdaddy">Buy me a Beer (Boosty)</a>
