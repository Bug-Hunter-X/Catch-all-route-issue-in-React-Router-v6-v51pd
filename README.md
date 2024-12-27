# React Router v6 Catch-All Route Issue

This repository demonstrates a common issue encountered when using catch-all routes (`/*`) in React Router v6. The problem arises when a catch-all route unintentionally overrides more specific routes, leading to unexpected behavior. The issue and its solution are explained below.

## Issue Description

In the provided `App.js` file, we have defined three routes: a home route (`/`), an about route (`/about`), and a catch-all route (`/*`). The catch-all route is intended to handle 404 errors. However, due to the order of route definition and how React Router v6 processes routes, the catch-all route unexpectedly intercepts all other routes.  This means navigating to `/about` will redirect to the 404 page instead.

## Solution

The solution, shown in `AppSolution.js`, involves changing the order of routes. The catch-all route should always be defined last to correctly function as a 404 handler. React Router will match the most specific route first, and only if no other route matches will the catch-all route be used.