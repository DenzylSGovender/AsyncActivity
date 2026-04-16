# 🏗 Asynchronous Student Portal Activity

## Scenario Context
You are building a **Student Portal Dashboard** for a university. The portal retrieves data from multiple services:

1. Grades Service → returns student grades  
2. Notifications Service → returns messages  
3. Schedule Service → returns the student timetable  

Your task is to **optimize the portal using asynchronous programming**.

---

## Part 1: Understanding Asynchronous Calls

1. What is the difference between synchronous and asynchronous calls in C#?  
2. Why is asynchronous programming important in enterprise software applications?  
3. What is the effect of calling multiple independent services synchronously on performance?  
4. How does using `async` / `await` improve the responsiveness of an application?  

---

## Part 2: Applying Asynchronous Programming

5. Identify which services in the portal scenario can run **independently** and therefore benefit from async calls.  
6. How would you modify the portal to fetch grades, notifications, and schedule simultaneously?  
7. Explain how `Task.WhenAll()` or a similar approach can be used to optimise performance.  
8. What would be the expected improvement in execution time if the services are asynchronous rather than synchronous?  

---

## Part 3: Advanced Considerations

9. How can you handle errors or exceptions in multiple asynchronous service calls?  
10. What is a cancellation token, and how can it be used in this portal scenario?  
11. Explain how `Task.WhenAny()` could be used to display data **as soon as a service responds** instead of waiting for all services.  
12. How would scaling this solution work if the portal had **10 or more independent services**?  

---

## Part 4: Reflection / Scenario-Based Questions

13. Imagine the portal needs to fetch data from an external API for each service. How would async calls improve user experience?  
14. If the Grades Service fails while Notifications and Schedule succeed, how should the portal handle partial results?  
15. What trade-offs or risks exist when using asynchronous calls in an enterprise portal (e.g., race conditions, thread safety)?  

---

## Notes for Students

- **Answer all questions** in your own words; use examples where possible.  
- Consider **performance**, **user experience**, and **enterprise best practices** when answering.  
- This activity is intended to prepare you for **enterprise-level asynchronous application design**.  
