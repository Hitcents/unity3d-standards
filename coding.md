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

So our convention for public fields is to start with a lower case letter, and camel case the rest.

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

Always put `public`:

```C#
public class NicCage
{
  //Members here
}
```

