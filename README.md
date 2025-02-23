# Next.js 15 App Router Middleware Issue with Dynamic Routes

This repository demonstrates a bug encountered in Next.js 15's App Router when using middleware with dynamic routes.  The middleware functions unexpectedly, failing to correctly intercept requests to specific dynamic route segments.

## Issue Description

The problem arises when combining the use of the new App Router's `middleware.js` with pages using dynamic routes (e.g., `[...slug].js`). The middleware does not consistently apply its logic, leading to unexpected behavior.  The specific symptom is that requests to certain dynamic route segments bypass the middleware completely. This wasn't occurring as consistently in Next.js 13.

## Steps to Reproduce

1. Clone this repository.
2. Run `npm install`.
3. Run `npm run dev`.
4. Navigate to various dynamic routes.  Observe that middleware is sometimes applied and sometimes not, seemingly inconsistently based on the dynamic route segments.

## Expected Behavior

The middleware should consistently apply its logic, regardless of the dynamic route being accessed.

## Actual Behavior

The middleware behaves inconsistently and intermittently, bypassing its logic in certain cases.

## Workaround

For now, use traditional pages (using `pages` directory), but be aware of the issues listed in the solution.