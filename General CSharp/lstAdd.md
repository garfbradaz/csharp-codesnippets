# lstAdd

**Note:** - I have created a code snippet based off Scott Allens <a href="http://odetocode.com/blogs/scott/archive/2013/03/11/dropdownlistfor-with-asp-net-mvc.aspx" target="_blank">blog post</a>. Check it out.

## Usage:

To allow you to quickly create a `List.Add(new object {})` for when you have lines of them to create. A good example is when you are creating a functioning to seed some data.

Example output when you type in `lstAdd` and tab twice in VS:

```c#
            ListName.Add(
                        new objToNew {/**/}
                        );
```

1. Replace `ListName` with your collection you have instantiated earlier in your code.
2. Replace `objToNew` with the class name you wish to add to your `List<objToNew>`

You should have something that looks like this:

```c#
             educationTypes.Add(
                new Education {Id = 1, RowStatus = "L", Description = "School Leaver" }
                );
```

## Seeding Data Usage

So a good use of this is to create a method whereby you can quickly and easily create data for your collection. Here is an example of why I created this snippet, so that I can create the code quickly:

```c#
public void SeedTestDataForMyEducationCollection()
{
    List<Education> educationTypes = new List<Education>();
    #region Education Seed
    educationTypes.Add(
                new Education {Id = 1, RowStatus = "L", Description = "School Leaver" }
                );
    educationTypes.Add(
                new Education {Id = 2, RowStatus = "L", Description = "GCSE" }
                );
    educationTypes.Add(
               new Education { Id = 3, RowStatus = "L", Description = "A-Level" }
               );
    educationTypes.Add(
               new Education { Id = 4, RowStatus = "L", Description = "Undergraduate" }
               );
    educationTypes.Add(
               new Education { Id = 5, RowStatus = "L", Description = "Post-Graduate" }
               );
    educationTypes.Add(
               new Education { Id = 6, RowStatus = "L", Description = "Doctorate" }
                 );
    educationTypes.Add(
               new Education { Id = 7, RowStatus = "L", Description = "Other" }
               );
}
```