# 🌐 HTML Serializer
> A powerful C# HTML parsing library with CSS selector support

[![.NET](https://img.shields.io/badge/.NET-7.0-512BD4?logo=dotnet)](https://dotnet.microsoft.com/)
[![C#](https://img.shields.io/badge/C%23-Latest-239120?logo=csharp)](https://docs.microsoft.com/en-us/dotnet/csharp/)
[![HTML](https://img.shields.io/badge/HTML-Parser-E34F26?logo=html5)](https://html.spec.whatwg.org/)

**Transform HTML into structured C# objects with DOM tree building and CSS selector querying - no browser required!**

## 🌟 Features

- 🔍 **CSS Selector Support** - Query HTML elements using CSS selector syntax
- 🏗️ **DOM Tree Construction** - Build complete document object model from HTML
- ⚡ **Native HTML Parsing** - No external dependencies or browser requirements
- 🎯 **Intelligent Element Detection** - Regex-based parsing with proper hierarchy
- 🧩 **Web Scraping Ready** - Perfect foundation for crawler applications

## 🚀 Quick Start

```bash
# Clone the repository
git clone https://github.com/Batya19/html-serializer-project.git
cd html-serializer-project

# Build and run
dotnet build
dotnet run --project practicode2
```

## 📖 Usage

```csharp
// Parse HTML into DOM tree
string html = "<div class='container'><p id='text'>Hello World</p></div>";
var document = HtmlSerializer.Parse(html);

// Query elements using CSS selectors
var container = document.QuerySelector("div.container");
var text = document.QuerySelector("#text");
var allDivs = document.QuerySelectorAll("div");

// Navigate DOM tree
foreach (var element in document.Descendants())
{
    Console.WriteLine($"Tag: {element.TagName}, ID: {element.Id}");
}
```

## 🏗️ Project Structure

```
📦 html-serializer-project
├── 📄 practicode2.sln                 # Solution file
└── 📁 practicode2/                    # Main project
    ├── 📄 HtmlElement.cs              # DOM element representation
    ├── 📄 HtmlHelper.cs               # HTML validation utilities
    ├── 📄 HtmlSerializer.cs           # Main HTML parsing engine
    ├── 📄 Selector.cs                 # CSS selector implementation
    ├── 📄 Program.cs                  # Application entry point
    ├── 📄 HtmlTags.json               # Valid HTML tags list
    └── 📄 HtmlVoidTags.json           # Self-closing tags list
```

## 🔧 Core Components

### HtmlElement
```csharp
public class HtmlElement
{
    public string TagName { get; set; }
    public string Id { get; set; }
    public List<string> Classes { get; set; }
    public Dictionary<string, string> Attributes { get; set; }
    public string InnerHtml { get; set; }
    public HtmlElement Parent { get; set; }
    public List<HtmlElement> Children { get; set; }
    
    // Navigation methods
    public IEnumerable<HtmlElement> Descendants()
    public IEnumerable<HtmlElement> Ancestors()
}
```

### CSS Selectors
```csharp
// Tag selector
var divs = document.QuerySelectorAll("div");

// ID selector
var header = document.QuerySelector("#header");

// Class selector
var buttons = document.QuerySelectorAll(".btn");

// Combined selectors
var specificDiv = document.QuerySelector("div#main.container");

// Hierarchical selectors
var nestedElements = document.QuerySelectorAll("div .content span");
```

## 🎯 Use Cases

- 🕷️ **Web Scraping** - Extract data from websites without browser overhead
- 📊 **Content Analysis** - Analyze HTML structure and content patterns
- 🔍 **SEO Tools** - Parse meta tags, headings, and link structures
- 📰 **Data Extraction** - Process HTML documents for information mining

## 🛠️ Technical Details

- **Language:** C# with .NET 7.0
- **Parsing:** Regular expressions for HTML tokenization
- **Configuration:** JSON files for HTML tag validation (`HtmlTags.json`, `HtmlVoidTags.json`)
- **Architecture:** Singleton pattern for `HtmlHelper`, efficient DOM tree construction
- **Performance:** `HashSet` for duplicate prevention, `yield return` for memory efficiency

## 🔍 Browser Independence

Unlike browser-dependent solutions, this library:
- ✅ Parses HTML server-side without browser dependencies
- ✅ Works with static HTML content
- ✅ Lightweight and fast for batch processing
- ⚠️ Doesn't execute JavaScript (parses static HTML only)

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 👩‍💻 Author

**Batya Zilberberg** - [GitHub](https://github.com/Batya19)

---

<div align="center">

**Made with 💖 by a developer who believes in clean, efficient HTML parsing**

*Parse HTML like a pro, query like a boss! 🚀✨*

</div>