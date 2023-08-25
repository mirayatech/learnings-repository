# 🌐 Server Components

React Server Components (RSC) are a fresh idea in React 18. Next.js 13 now supports RSC in its app directory.

## 📃 Understanding SPA

A Single-Page Application (SPA) works by doing all the showing and getting of data right in your web browser. This makes the First Contentful Paint (FCP) take longer, which isn't great for how users feel about a website. So basically, it's an HTML-based router for a single-page application. Whenever we do routing, we switch out that div with another component, and the HTML page never goes back to the server to reload or refetch.

## 🚀 How SSR Helps

Server-Side Rendering (SSR) speeds up how fast the first page appears because it does the work on the server. It doesn't make you wait. But remember, the page won't respond right away when you click or type. Your browser needs to finish getting all the JavaScript before you can do stuff.

## 🌟 Meet RSC

React Server Components (RSC) offer a new way to do server-side rendering. They let website makers build parts of a website on the server and send them to your computer while they're being made.

In RSC, there are two types of parts: server parts (made on the server) and computer parts (made in your browser). Server parts don't need you to click or type, or use special tools like React's useState and useEffect.

The server creates these parts and sends them to your computer. It only sends the special JavaScript code your computer needs for those parts. This makes the JavaScript smaller and quicker to get. So, you can start using the website sooner, which is good.

## 🔄 RSC vs. SSR

Unlike SSR, which mostly does server-side work when you first go to a web page, RSC makes your computer do the work later. This means your computer only needs to get the JavaScript for the parts of the webpage you're using, kind of like a Single-Page Application (SPA). This is why RSC is better for making websites faster and nicer for you. 🚀📊
