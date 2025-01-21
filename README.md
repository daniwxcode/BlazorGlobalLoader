# BlazorGlobalLoader
 BlazorGlobalLoader is a lightweight, customizable component for displaying a global loader during HTTP requests in Blazor WebAssembly and Server apps. With support for different indicator types (Spinner, Bar, Skeleton) and CSS customization, it enhances user experience by managing loading states easily. Simple integration and easy to use!

## Features

- **Automatic loader display** during HTTP requests
- **Customizable loading indicators** (Spinner, Bar, Skeleton)
- **CSS customization support**
- **Easy integration with Blazor WebAssembly and Blazor Server**
- **JavaScript interoperability for advanced animations**

## Installation

Install the package via NuGet:

```bash
dotnet add package BlazorGlobalLoader
```

## Usage

1. Add the service in `Program.cs`:

```csharp
builder.Services.AddScoped<LoadingService>();
```

2. Use the loader in `MainLayout.razor`:

```razor
<Loader IndicatorType="Spinner" />
```

3. Trigger the loader in a component:

```razor
@inject LoadingService LoadingService

<button @onclick="CallApi">Load Data</button>

@code {
    private async Task CallApi()
    {
        LoadingService.Show();
        await Task.Delay(3000); // Simulate an API call
        LoadingService.Hide();
    }
}
```

## Customization

### Indicator Types:

- **Spinner**
- **Bar**
- **Skeleton**

### CSS Customization Example:

```css
.global-loader {
    background: rgba(0, 0, 0, 0.5);
    animation: fadeIn 0.3s ease-in-out;
}
```

## Why Choose BlazorGlobalLoader?

- **Improved User Experience** with automatic loaders
- **Optimized for Blazor**: Lightweight and performant
- **Fully Customizable** to match your app's design
- **Simple Integration** with minimal setup

## License

This project is licensed under the MIT License.
