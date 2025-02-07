# React Router Dom v6 Catch-All Route Issue

This repository demonstrates a common issue encountered when using catch-all routes (`/*`) in React Router Dom v6.  The catch-all route, intended to handle unmatched routes, is incorrectly matching even when other routes should be rendered.  This can lead to unexpected behavior and prevent proper navigation.

## Problem

The provided `App.js` demonstrates a simple React Router setup with three routes: `/`, `/about`, and a catch-all route `/*`. When navigating to `/` or `/about`, the catch-all route (`NotFound` component) is unexpectedly rendered instead of the corresponding component.  This happens because the catch-all route is too broadly defined and overrides other routes.

## Solution

The solution is in `AppSolution.js`. The catch-all route needs to be placed after other specific routes to allow them to be evaluated first.   If a route matches a path before the catch-all, it will take precedence over the catch-all. 