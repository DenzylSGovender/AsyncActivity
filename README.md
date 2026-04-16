#  C# Activity: Asynchronous Student Portal Simulation

## Learning Outcome
Students will use **asynchronous programming** in C# to optimise application performance in a simulated enterprise portal.

---

## Scenario
You are building a **Student Portal Dashboard** for a university. The portal retrieves data from multiple services:

1. **Grades Service** → returns student grades  
2. **Notifications Service** → returns messages  
3. **Schedule Service** → returns timetable  

Initially, the portal runs these services **synchronously**, making it slow. Your task is to **convert the service calls to asynchronous** to improve responsiveness.

---

## Step 1: Setup Project
1. Open **Visual Studio 2026**  
2. Create a **Console App (.NET 8 or higher)** project  
3. Name it: `AsyncPortalDemo`

---

## Step 2: Starter Code (Synchronous Version)

```csharp
using System;
using System.Threading;

class Program
{
    static void Main()
    {
        Console.WriteLine("Fetching student portal data...");

        GetGrades();
        GetNotifications();
        GetSchedule();

        Console.WriteLine("All data fetched.");
    }

    static void GetGrades()
    {
        Thread.Sleep(2000); // Simulate delay
        Console.WriteLine("Grades loaded.");
    }

    static void GetNotifications()
    {
        Thread.Sleep(2000); // Simulate delay
        Console.WriteLine("Notifications loaded.");
    }

    static void GetSchedule()
    {
        Thread.Sleep(2000); // Simulate delay
        Console.WriteLine("Schedule loaded.");
    }
}
```
---
Expected Output (~6 seconds total)
---
Fetching student portal data...
Grades loaded.
Notifications loaded.
Schedule loaded.
All data fetched.
---
---
Step 3: Convert to Asynchronous Calls

Convert each service method to async Task
Replace Thread.Sleep() with await Task.Delay()
Make Main asynchronous: static async Task Main()
Run all tasks in parallel using Task.WhenAll()
---
```
using System;
using System.Diagnostics;
using System.Threading.Tasks;

class Program
{
    static async Task Main()
    {
        Console.WriteLine("Fetching student portal data...");

        Stopwatch sw = Stopwatch.StartNew();

        // Run tasks asynchronously
        Task gradesTask = GetGradesAsync();
        Task notificationsTask = GetNotificationsAsync();
        Task scheduleTask = GetScheduleAsync();

        await Task.WhenAll(gradesTask, notificationsTask, scheduleTask);

        sw.Stop();
        Console.WriteLine("All data fetched.");
        Console.WriteLine($"Total time: {sw.ElapsedMilliseconds} ms");
    }

    static async Task GetGradesAsync()
    {
        await Task.Delay(2000); // Simulate network delay
        Console.WriteLine("Grades loaded.");
    }

    static async Task GetNotificationsAsync()
    {
        await Task.Delay(2000); // Simulate network delay
        Console.WriteLine("Notifications loaded.");
    }

    static async Task GetScheduleAsync()
    {
        await Task.Delay(2000); // Simulate network delay
        Console.WriteLine("Schedule loaded.");
    }
}
```
---
Expected Output (~2 seconds total)
---
Fetching student portal data...
Grades loaded.
Notifications loaded.
Schedule loaded.
All data fetched.
Total time: 2010 ms
---
