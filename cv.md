# CV
## My name is Yan Kozyrenko. I'm 18 years old.
I live in Russia, Rostov-on-Don. There are several ways to contact me: Phone - +7(928)635-01-32. E-mail - kopn48@mail.ru, or my github.
## My summary
I started to learn IT stuff around 8 months ago. I always liked this kind of activity, but i wasnt into this. Then i realized that i want to bond my life with programming.
Later i started to learn my second programming language `C#`. It's very simple unlike `C++`, so i falled in love with it. Now i understand and practice big stack of .NET technologies.
My goal is to learn more about `JS` and native technologies. RS School is a great opportunity to get this forbidden JavaScript knowledge.

## My Skills

As a **.NET developer** i practice 

* `Entity Framework (Core)`
* `WPF`
* `ASP.NET`
* `ADO.NET`
* `OOP` and `SOLID` principles

As a Frontend developer i practice

* `HTML5`
* `CSS3`
* `SCSS`
* a bit of `JS`
## Code Examples
Theres some examples from my `C#` repository. I dont have great experience in JavaScript to show it in CV.

This is example of Pagination Model for sites with lots of contents.
```c#
public static class PaginationModel
    {
        public static IHtmlContent GetArrow(this PageTagHelper tagHelper, ArrowType arrowType)
        {
            IUrlHelper urlHelper = tagHelper.helper.GetUrlHelper(tagHelper.ViewContext);
            TagBuilder li = new TagBuilder("li");
            if (arrowType == ArrowType.Next)
            {
                if (tagHelper.PageModel.CurrentPage == tagHelper.PageModel.TotalPages) return null;

                tagHelper.UrlValues["page"] = tagHelper.PageModel.CurrentPage + 1;

            }
            else
            {
                if (tagHelper.PageModel.CurrentPage == 1) return null;

                tagHelper.UrlValues["page"] = tagHelper.PageModel.CurrentPage - 1;
            }
            TagBuilder a = new TagBuilder("a");
            a.Attributes["href"] = urlHelper.Action("Index", tagHelper.UrlValues);
            if (arrowType == ArrowType.Next)
            {
                a.InnerHtml.Append(">");
            }
            else
            {
                a.InnerHtml.Append("<");
            }
            li.InnerHtml.AppendHtml(a);
            if (tagHelper.PageClassesEnabled) li.AddCssClass("page page_secondary");
            return li;
        }
        public static IHtmlContent GetPage(this PageTagHelper tagHelper, int page)
        {
            IUrlHelper urlHelper = tagHelper.helper.GetUrlHelper(tagHelper.ViewContext);
            TagBuilder li = new TagBuilder("li");
            tagHelper.UrlValues["page"] = page;
            TagBuilder a = new TagBuilder("a");
            a.Attributes["href"] = urlHelper.Action("Index", tagHelper.UrlValues);
            a.InnerHtml.Append($"{page}");
            li.InnerHtml.AppendHtml(a);
            if (tagHelper.PageClassesEnabled)
            {
                li.AddCssClass("page");
                if (tagHelper.PageModel.CurrentPage == page)
                {
                    li.AddCssClass("page_active");
                }
                else
                {
                    li.AddCssClass("page_secondary");
                }
            }
            return li;
        }
    }
```
