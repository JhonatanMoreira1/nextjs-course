# 📦 Fork for Pull Request - Fix Connectivity Issue

📁 Repository: A **fork** of the original project [burakorkmez/nextjs-course](https://github.com/burakorkmez/nextjs-course), created to submit a Pull Request addressing a connectivity error.  
🔗 Pull Request: [#4 - Fix connectivity error and failure to request data from the server](https://github.com/burakorkmez/nextjs-course/pull/4)  
🌿 Branch: [`fix-connectivity-check`](https://github.com/JhonatanMoreira1/nextjs-course/tree/fix-connectivity-check) – where the fix was implemented.

---

![Error Demonstration](https://private-user-images.githubusercontent.com/151602959/422135128-06631a0e-46b3-473b-a737-bc98b1813f0f.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3NDQ3NTk4OTYsIm5iZiI6MTc0NDc1OTU5NiwicGF0aCI6Ii8xNTE2MDI5NTkvNDIyMTM1MTI4LTA2NjMxYTBlLTQ2YjMtNDczYi1hNzM3LWJjOThiMTgxM2YwZi5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjUwNDE1JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI1MDQxNVQyMzI2MzZaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT1hZWRkNmU3N2RmM2Q1YzU0YWVlZDY4NGE1NDAxZmUzY2JkNjA3MDU4MGZjNWJjYzIwNTUwOTc4ODg1NmE0NTdjJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCJ9.iQuOQpA3C0ZEXInGK3kDldeVzQaYWnHrppFUmf6n8f8)

---

## ✅ What This PR Fixes

This Pull Request addresses a **server connectivity failure** issue that prevented the application from requesting the required data and caused crashes, directly impacting user experience.

---

## 🛠️ Technical Details of the Fix

### 🔄 `syncUser` Function (`user.action.ts`)
- Added **automatic retry logic**.
- If the data request fails, the function retries up to **3 times** with a **500ms delay** between attempts.
- If all attempts fail, the error is logged in the console.

### 🌐 `checkConnectivity` Function (`src/utils/checkConnectivity.ts`)
- New function to **check connectivity with NeonDB and Clerk**.
- It's called before syncing the user, ensuring requests are made only when connectivity is stable.

### ⚙️ Changes in `page.tsx`
- The `syncUser` function is now called inside a `Promise.all`, allowing **parallel requests**, speeding up page load time.

### 🧹 More Robust Error Handling
- If a request fails, the application now displays a **user-friendly message** indicating a connectivity issue.

---

## 📄 Summary of Fixes

- Failures to request data from the server during connectivity loss.
- Added auto-retry logic for user sync.
- Clearer error messages to improve user experience.

---

> This fork was created **exclusively** for submitting this Pull Request, and the changes can be viewed in the [`fix-connectivity-check`](https://github.com/JhonatanMoreira1/nextjs-course/tree/fix-connectivity-check) branch.

