##C# Standards

Unity3d's APIs have some stange naming conventions. So we will have to modify ours at Hitcents a bit to make our code match them.

Everyone *must* follow these, I will make fun of you or slap you depending on the situation.

#Public fields

The main difference is the. Microsoft (or we) would name a public field like this:

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

So our convention for public fields is to start with a lower case letter, and camel case the rest. What the Unity Editor will do is convert `firstName` to `First Name` in the menu, so camel casing is extremely important or it would say `Firstname`.

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

#Class visibility

Always put the `public` keyword:

```C#
public class NicCage
{
  //Members here
}
```

If left off, it defaults to `internal`, and defaults to `private` if it is a nested class. We might not want that if we want to use the class in another project. If the class is actually `internal` or `private` use the keyword, also.

#Compiler Warnings

Your C# code should *not* have warnings. If you are not using a variable, delete it! I will be setting the build server to fail on warnings, so we can all make fun of you if your code has them.

