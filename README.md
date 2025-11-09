# 🌙 Building a Simple Dark Mode Toggle in Next.js

## 🧭 Overview

This guide explains two simple ways to add a **Dark Mode toggle** to your Next.js app:

1. **Easiest:** Using the [`next-themes`](https://github.com/pacocoursey/next-themes) library  
2. **Custom:** Toggling a CSS class manually and saving the preference

Both approaches work with the **App Router (`app/`)** and the **Pages Router (`pages/`)**.  
The examples below use the **App Router**, but you can easily adapt them.

---

## ⚙️ Prerequisites

Before you begin, make sure you have:

- **Next.js 13+** (works on earlier versions too)
- **Basic React knowledge**
- A CSS setup (recommended: **Tailwind CSS**, or your own CSS variables)

---

## 🌗 Option A — Dark Mode with `next-themes` (Recommended)

`next-themes` handles:

- Detecting system color preference  
- SSR-friendly class toggling  
- Local storage persistence  
- A React hook for easy theme switching  

---

### 🧩 Step 1: Install

```bash
npm install next-themes
