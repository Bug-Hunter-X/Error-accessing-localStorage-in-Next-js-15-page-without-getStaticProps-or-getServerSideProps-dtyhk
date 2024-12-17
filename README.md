# Next.js 15 - localStorage Error in Static Site Generation

This repository demonstrates a common error encountered in Next.js 15 applications when attempting to access `localStorage` within a page component that doesn't utilize `getStaticProps` or `getServerSideProps`.  The issue arises because `localStorage` is not available during the static site generation (SSG) process.

## Problem

The `about.js` file attempts to read user data from `localStorage`.  Because this page doesn't employ `getStaticProps` or `getServerSideProps`, Next.js attempts to render it during the SSG phase. This leads to an error, as `localStorage` is unavailable in this context.

## Solution

The `aboutSolution.js` demonstrates the correct way to handle this situation.  It uses `getServerSideProps` to fetch data at request time. This allows access to `localStorage` after the user's browser has rendered the page and set the data in `localStorage`.

This ensures the data is available to render the page.