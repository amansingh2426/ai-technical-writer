# 🌙 Building a Simple Dark Mode Toggle in Next.js


### 🧭 Overview

This repository provides a simple and flexible approach to implementing **Dark Mode** in a **Next.js** application.  
It covers two main methods:

1. **Using the `next-themes` library** (recommended for most projects)  
2. **Creating a custom theme toggle** without external dependencies  

Both methods work with **App Router (`app/`)** and **Pages Router (`pages/`)**.

---

## ⚙️ Prerequisites

Before starting, make sure your environment is ready:

- **Node.js 18+**
- **Next.js 13+**
- Basic understanding of **React** and **CSS**
- A CSS setup such as **Tailwind CSS** or your own custom stylesheet

---

## 🚀 Getting Started

1. **Clone the Repository**

   Clone this project to your local environment:
git clone https:(https://github.com/amansingh2426/ai-technical-write)
cd dark-mode-toggle-nextjs

markdown
Copy code

2. **Install Dependencies**

Use your preferred package manager:
npm install

nginx
Copy code
or  
yarn install

markdown
Copy code

3. **Run the Development Server**
npm run dev

yaml
Copy code
Then open [http://localhost:3000](http://localhost:3000) in your browser.

---

## 🌗 Option A — Using `next-themes` (Recommended)

This is the easiest and most reliable method.  
It automatically detects system preferences, manages dark/light switching, and persists user choice.

### What You’ll Set Up

- Install and configure `next-themes`
- Wrap your application with a `ThemeProvider`
- Create a theme toggle button for the UI
- Define your dark and light mode color variables (using Tailwind or CSS)
- Verify that the selected theme is saved across sessions

### How It Works

- The `ThemeProvider` injects a `dark` class on the `<html>` element.  
- Tailwind CSS or your own CSS variables respond to this class to change styles.  
- The user’s theme preference is stored in `localStorage`.  
- On page load, the saved preference (or system default) is applied before hydration.

---

## 🧰 Option B — Manual Dark Mode Toggle

If you prefer full control and want to avoid extra dependencies, you can manually toggle themes.

### What You’ll Do

- Create a state variable to store the current theme (`light` or `dark`)
- Apply or remove the `dark` class from the `<html>` element whenever the state changes
- Save the selected theme in `localStorage` for persistence
- Detect system preference using the `prefers-color-scheme` media query
- Optionally add a small inline script to apply the saved theme early during page load

### Key Notes

- Manual toggling offers full customization but requires more setup.  
- The inline initialization script prevents a “flash” of incorrect theme before React loads.  
- Keep class toggling consistent (`dark` class on `<html>` or `<body>`).

---

## 🎨 Styling Guidelines

You can manage your dark and light colors using:

- **Tailwind CSS:**  
Enable `darkMode: "class"` in your Tailwind configuration.  
Use `dark:` variants in your classes (e.g., `bg-white dark:bg-gray-900`).

- **Custom CSS Variables:**  
Define color variables for both light and dark themes, and switch them based on the `dark` class.

Example structure:
- Define variables in `:root` for light mode.
- Override them inside a `.dark` selector for dark mode.

---

## ♿ Accessibility & UX Recommendations

To make your dark mode toggle accessible and user-friendly:

- Always include an `aria-label` on toggle buttons (e.g., “Toggle dark mode”).  
- Use icons or visual indicators for theme state (sun/moon, light/dark text).  
- Maintain sufficient color contrast in both modes.  
- Allow the theme to follow the system preference when possible.  
- Ensure transitions between themes are smooth and don’t cause flashing.

---

## 🧪 Testing Checklist

When testing your implementation, verify the following:

- The theme toggle works correctly and updates immediately.  
- Refreshing the page keeps the same theme preference.  
- System preference (dark/light) is respected on first load.  
- No hydration or mismatch warnings appear in the console.  
- UI components look correct and readable in both themes.

---

## 🧱 Folder Structure

<img width="242" height="612" alt="image" src="https://github.com/user-attachments/assets/c0578f0c-a63c-4925-bf32-4e1759bff960" />



yaml
Copy code

---

## 🛠 Troubleshooting

| Problem | Possible Cause | Solution |
|----------|----------------|-----------|
| Theme flashes before load | HTML doesn’t have theme applied early | Add inline initialization script or use `next-themes` |
| Tailwind dark classes not working | `darkMode` not set in config | Enable `darkMode: "class"` in `tailwind.config.js` |
| Hydration warnings | Accessing `window` during SSR | Use `useEffect` to handle client-side theme detection |
| Theme not persisting | localStorage key missing or overridden | Check storage key and ensure write permissions |

---

## 💡 Best Practices

- Keep your dark mode logic minimal — let CSS handle color changes.  
- Test in both system themes before deployment.  
- For better performance, avoid transitions on the initial load.  
- If building for open-source, clearly document the theme setup for contributors.

---

## 🧩 When to Choose Each Approach

| Approach | Recommended For | Advantages |
|-----------|-----------------|-------------|
| **`next-themes`** | Most projects | Easy setup, system-aware, handles persistence |
| **Manual Toggle** | Lightweight or custom setups | Full control, zero dependencies |

---

## 🧑‍💻 Contributing

Contributions are welcome!  
If you find a bug or want to improve documentation, open an issue or submit a pull request.

Steps:
1. Fork this repository  
2. Create a new branch (`feature/your-feature`)  
3. Commit and push your changes  
4. Submit a pull request for review  

---

## 📜 License

This project is released under the **MIT License**.  
You’re free to use, modify, and distribute it for personal or commercial projects.

---

## ✨ Summary

By following this guide, you’ll have a **fully functional dark mode** setup in your Next.js project —  
either through `next-themes` for simplicity or a custom toggle for full control.

Both methods are production-ready, accessible, and user-friendly.
