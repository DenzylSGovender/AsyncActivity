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

Expected Output (~6 seconds total)
