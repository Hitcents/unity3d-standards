##C# Standards

Unity3d's APIs have some stange naming conventions. So we will have to modify ours at Hitcents a bit to make our code match them.

Everyone *must* follow these, I will make fun of you or slap you depending on the situation.

#Formatting

First and foremost, use Visual Studio always. If on a Mac, we will need to configure MonoDevelop to emulate Visual Studio settings.

By default Unity make a new script look like this:

```C#
public class NicCage : MonoBehaviour {

	// Use this for initialization
	void Start () {
	  //Code here
	}
}
```

Our formatting style is Microsoft's. Your first step in a file like this is to delete the end curly brace and retype it, so it formats the class like this:

```C#
public class NickCage : MonoBehaviour
{
  // Use this for initialization
  void Start()
  {
    //Code here
  }
}
```

#Comments

As in the above example, there is a stupid default comment made by Unity. If the comment is nonsense, *DELETE IT*!

Comments above methods should always use C# summaries, type three /// to generate them in VS:

```C#
public class NickCage : MonoBehaviour
{
  ///<summary>
  /// This is where I would put a meaningful comment about Nic Cage starting up.
  ///</summary>
  void Start()
  {
    //Code here
  }
}
```

If you can make Unity generate files like this by default, I will give you a cookie.

#Empty methods

Delete empty methods that are not conforming to a base class or interface. If it is a Unity method like `Start` or `Update` it will actually slow the game down if you do not remove them. If I see them, I will make fun of you.

#Commented code

If it is a quick hack you are going to fix later, it is OK to *temporarily* comment out code. If there is commented code that you are not sure what it does, or has been there a while, *DELETE IT*! We have source control, there is no reason to commit commented code long term.

#Classes and files

1 class per file! The only exception would be a file named `Enumerations.cs` or `Structs.cs` that contain many small enums or structs.

#Public fields

The main difference is for Unity's naming is public fields. Microsoft (or we) would name a public field like this:

```C#
public class NicCage
{
  public float Intensity;
  public string FirstName;
  public string LastName;
}
```

The problem is, Unity's APIs look like this:

```C#
public class NicCage
{
  public float intensity;
  public string firstName;
  public string lastName;
}
```

So our convention for public fields is to start with a lower case letter, and camel case the rest. What the Unity Editor will do is convert `firstName` to `First Name` in the menu, so camel casing is extremely important or it would say `Firstname`. I will slap you if I see menus named this way.

#Private fields

Our convention remains unchanged from standard C#, name private fields as such:

```C#
public class NicCage
{
  private float _intensity;
  private string _firstName;
  private string _lastName;
}
```

*ALWAYS* put the private keyword. It is way more readable. Also it can confuse past Java devs, C# defaults to private while Java defaults to public.

#Methods

These don't change from Microsoft/our conventions. They should look like this:

```C#
public class NicCage
{
  public void PunchSomeGuyInTheFace()
  {
    //Punch time
  }
}
```

#Class names

Don't name a class `StickmanBehavior` or `StickmanController`. Just name it `Stickman`.

#Class visibility

Always put the `public` keyword:

```C#
public class NicCage
{
  //Members here
}
```

If left off, it defaults to `internal`, and defaults to `private` if it is a nested class. We might not want that if we want to use the class in another project. If the class is actually `internal` or `private` use the keyword, also.

#Compiler warnings

Your C# code should *not* have warnings. If you are not using a variable, *DELETE IT*! I will be setting the build server to fail on warnings, so we can all make fun of you if your code has them.

