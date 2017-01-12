# mvcSelect

**Note:** - I have created a code snippet based off Scott Allens <a href="http://odetocode.com/blogs/scott/archive/2013/03/11/dropdownlistfor-with-asp-net-mvc.aspx" target="_blank">blog post</a>. Check it out.

## Usage:

To allow you to build easily the plumbing necessary to create Drop Down Select lists for MVC Razor view pages.

Example output when you type in `mvcSelect` and tab twice in VS:

```c#
        #region ModelName (Select)
        private readonly List<ModelName> modelNames;

        [Display(Name = "ModelName")]
        public int SelectedModelNameId { get; set; }
        public IEnumerable<SelectListItem> ModelNameItems
        {
            get
            {
                var allModelNames = modelNames.Select(g => new SelectListItem
                {
                    Value = g.Id.ToString(),
                    Text = g.Description
                });
                return allModelNames;
            }
        }
        #endregion
```

1. Replace `ModelName` with your public name of your model class. Example if you have a class that represents a school called `School.cs` then replace `ModelName` with `School`.
2. Replace `modelName` with the private name of your model class. Example if you have a class that represents a school called `School.cs` then replace `modelName` with `school`.

You should have something that looks like this:

```c#
        #region School (Select)
        private readonly List<School> schools;

        [Display(Name = "School")]
        public int SelectedSchoolId { get; set; }
        public IEnumerable<SelectListItem> SchoolItems
        {
            get
            {
                var allSchools = schools.Select(g => new SelectListItem
                {
                    Value = g.Id.ToString(),
                    Text = g.Description
                });
                return allSchools;
            }
        }
        #endregion
```