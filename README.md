# SplashKit Tutorial: Install and Create a Simple Drawing

Welcome to this beginner-friendly tutorial on setting up SplashKit SDK and using C# to create a simple animation.

# Table of Contents
1. [Install MSYS2 Terminal](#install-msys2-terminal)
2. [Install SplashKit SDK](#install-splashkit-sdk)
3. [Install Visual Studio Code (VS Code)](#install-visual-studio-code-vs-code)
4. [Install C# Extensions in VS Code](#install-c-extensions-in-vs-code)
5. [Install .NET Core SDK](#install-net-core-sdk)
6. [Create and Set Up Your Project](#create-and-set-up-your-project)
7. [Write Your First Drawing Code](#write-your-first-drawing-code)
8. [Build and Run the Program](#build-and-run-the-program)



## Install MSYS2 Terminal
MSYS2 is a terminal required to set up SplashKit and build programs on Windows.

- Visit the [MSYS2 website](https://www.msys2.org/) and download the installer.
![image](https://github.com/user-attachments/assets/e1e156c8-0db8-4bf4-83f6-2766eab6879c)


- Run the installer and follow the on-screen instructions.
- After installation, update MSYS2 using:
  ```sh
  pacman -Syu
  ```

---

## Install SplashKit SDK
SplashKit is an all-purpose software toolkit for graphics and games.

- Download and install SplashKit from [here](https://www.splashkit.io/).
- Verify installation by running:
  ```sh
  skm
  ```
![image](https://github.com/user-attachments/assets/6d3df8ec-0955-48b5-89f1-a5f742c7aa35)

---

## Install Visual Studio Code (VS Code)
If you don’t already have VS Code:
- Download the installer from the [VS Code website](https://code.visualstudio.com/).
- Run the installer and follow the on-screen instructions.
![image](https://github.com/user-attachments/assets/d1900635-625b-4728-a288-a9f5aa22d7a9)

---

## Install C# Extensions in VS Code
To work with C# in VS Code:
1. Open VS Code.
2. Click on the **Extensions** button (left-hand toolbar).
3. Search for **C#** and install the extension published by Microsoft.
![image](https://github.com/user-attachments/assets/3fc29a01-8d11-4555-8149-fdd7eba3a107)

---

## Install .NET Core SDK
SplashKit works with the .NET Core framework. Install it as follows:

- Visit the [.NET Core download page](https://dotnet.microsoft.com/en-us/download/dotnet/7.0).
- Download the SDK version suitable for your system (Windows, macOS, or Linux).
- Run the installer and follow the instructions.
![image](https://github.com/user-attachments/assets/d515f3b7-483b-4982-a3cd-c4279d4d7a9c)

---

## Create and Set Up Your Project

1. Open the **MSYS2 terminal** and navigate to your desired folder:
   ```sh
   cd path/to/your/folder
   ```
2. Run this command to set up a new console project with SplashKit:
   ```sh
   dotnet new console -n MyDrawing
   ```
3. Restore the project’s dependencies:
   ```sh
   dotnet restore
   ```

---

## Write Your First Drawing Code
Create a basic drawing in C# using SplashKit:

```csharp
using System;
using SplashKitSDK;

class Program
{
    static void Main(string[] args)
    {
        // Open a window
        Window window = new Window("Fun Drawing for Beginners", 800, 600);

        // Clear the window with a sky-blue background
        window.Clear(Color.SkyBlue);

        // Draw grass (green rectangle at the bottom)
        window.FillRectangle(Color.Green, 0, 500, 800, 100);

        // Draw a tree (brown trunk, green leaves)
        window.FillRectangle(Color.Brown, 100, 400, 50, 100); // Trunk
        window.FillCircle(Color.DarkGreen, 125, 375, 50); // Leaves

        // Draw a house (red body, blue roof)
        window.FillRectangle(Color.Red, 300, 350, 200, 150);
        window.FillTriangle(Color.Blue, 300, 350, 400, 250, 500, 350);

        // Draw a smiley face (yellow circle, black eyes, and a smile)
        window.FillCircle(Color.Yellow, 600, 200, 50);
        window.FillCircle(Color.Black, 580, 185, 5);
        window.FillCircle(Color.Black, 620, 185, 5);
        for (int i = 0; i <= 180; i += 10)
        {
            double radians = i * (Math.PI / 180);
            double x1 = 600 + Math.Cos(radians) * 30;
            double y1 = 220 + Math.Sin(radians) * 20;
            double x2 = 600 + Math.Cos(radians + (10 * Math.PI / 180)) * 30;
            double y2 = 220 + Math.Sin(radians + (10 * Math.PI / 180)) * 20;
            SplashKit.DrawLine(Color.Black, x1, y1, x2, y2);
        }

        // Refresh the window to show the shapes
        window.Refresh();

        // Keep the window open for 10 seconds
        SplashKit.Delay(10000);
        window.Close();
    }
}
```

---

## Build and Run the Program

To compile and run your program, use these commands:

- **Build the project:**
  ```sh
  dotnet build
  ```
- **Run the project:**
  ```sh
  dotnet run
  ```

Now, you should see a simple drawing appear on the screen! 🎨✨
![image](https://github.com/user-attachments/assets/89899040-027a-408e-8878-af01f3c09a56)

---

## 🎉 Congratulations!
You’ve successfully set up SplashKit and created a simple drawing program. Feel free to modify the code and experiment with different shapes and colors!

Happy coding! 🚀

