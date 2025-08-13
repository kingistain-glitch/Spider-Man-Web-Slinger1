<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Spider-Man: Web Slinger - A side-scrolling web shooting game with improved level design">
    <title>Spider-Man: Web Slinger</title>
    <style>
/* inlined from style.css */
:root {
  /* Primitive Color Tokens */
  --color-white: rgba(255, 255, 255, 1);
  --color-black: rgba(0, 0, 0, 1);
  --color-cream-50: rgba(252, 252, 249, 1);
  --color-cream-100: rgba(255, 255, 253, 1);
  --color-gray-200: rgba(245, 245, 245, 1);
  --color-gray-300: rgba(167, 169, 169, 1);
  --color-gray-400: rgba(119, 124, 124, 1);
  --color-slate-500: rgba(98, 108, 113, 1);
  --color-brown-600: rgba(94, 82, 64, 1);
  --color-charcoal-700: rgba(31, 33, 33, 1);
  --color-charcoal-800: rgba(38, 40, 40, 1);
  --color-slate-900: rgba(19, 52, 59, 1);
  --color-teal-300: rgba(50, 184, 198, 1);
  --color-teal-400: rgba(45, 166, 178, 1);
  --color-teal-500: rgba(33, 128, 141, 1);
  --color-teal-600: rgba(29, 116, 128, 1);
  --color-teal-700: rgba(26, 104, 115, 1);
  --color-teal-800: rgba(41, 150, 161, 1);
  --color-red-400: rgba(255, 84, 89, 1);
  --color-red-500: rgba(192, 21, 47, 1);
  --color-orange-400: rgba(230, 129, 97, 1);
  --color-orange-500: rgba(168, 75, 47, 1);

  /* RGB versions for opacity control */
  --color-brown-600-rgb: 94, 82, 64;
  --color-teal-500-rgb: 33, 128, 141;
  --color-slate-900-rgb: 19, 52, 59;
  --color-slate-500-rgb: 98, 108, 113;
  --color-red-500-rgb: 192, 21, 47;
  --color-red-400-rgb: 255, 84, 89;
  --color-orange-500-rgb: 168, 75, 47;
  --color-orange-400-rgb: 230, 129, 97;

  /* Background color tokens (Light Mode) */
  --color-bg-1: rgba(59, 130, 246, 0.08); /* Light blue */
  --color-bg-2: rgba(245, 158, 11, 0.08); /* Light yellow */
  --color-bg-3: rgba(34, 197, 94, 0.08); /* Light green */
  --color-bg-4: rgba(239, 68, 68, 0.08); /* Light red */
  --color-bg-5: rgba(147, 51, 234, 0.08); /* Light purple */
  --color-bg-6: rgba(249, 115, 22, 0.08); /* Light orange */
  --color-bg-7: rgba(236, 72, 153, 0.08); /* Light pink */
  --color-bg-8: rgba(6, 182, 212, 0.08); /* Light cyan */

  /* Semantic Color Tokens (Light Mode) */
  --color-background: var(--color-cream-50);
  --color-surface: var(--color-cream-100);
  --color-text: var(--color-slate-900);
  --color-text-secondary: var(--color-slate-500);
  --color-primary: var(--color-teal-500);
  --color-primary-hover: var(--color-teal-600);
  --color-primary-active: var(--color-teal-700);
  --color-secondary: rgba(var(--color-brown-600-rgb), 0.12);
  --color-secondary-hover: rgba(var(--color-brown-600-rgb), 0.2);
  --color-secondary-active: rgba(var(--color-brown-600-rgb), 0.25);
  --color-border: rgba(var(--color-brown-600-rgb), 0.2);
  --color-btn-primary-text: var(--color-cream-50);
  --color-card-border: rgba(var(--color-brown-600-rgb), 0.12);
  --color-card-border-inner: rgba(var(--color-brown-600-rgb), 0.12);
  --color-error: var(--color-red-500);
  --color-success: var(--color-teal-500);
  --color-warning: var(--color-orange-500);
  --color-info: var(--color-slate-500);
  --color-focus-ring: rgba(var(--color-teal-500-rgb), 0.4);
  --color-select-caret: rgba(var(--color-slate-900-rgb), 0.8);

  /* Common style patterns */
  --focus-ring: 0 0 0 3px var(--color-focus-ring);
  --focus-outline: 2px solid var(--color-primary);
  --status-bg-opacity: 0.15;
  --status-border-opacity: 0.25;
  --select-caret-light: url('data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='16' height='16' viewBox='0 0 24 24' fill='none' stroke='%23134252' stroke-width='2' stroke-linecap='round' stroke-linejoin='round'%3E%3Cpolyline points='6 9 12 15 18 9'%3E%3C/polyline%3E%3C/svg%3E');
  --select-caret-dark: url('data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='16' height='16' viewBox='0 0 24 24' fill='none' stroke='%23f5f5f5' stroke-width='2' stroke-linecap='round' stroke-linejoin='round'%3E%3Cpolyline points='6 9 12 15 18 9'%3E%3C/polyline%3E%3C/svg%3E');

  /* RGB versions for opacity control */
  --color-success-rgb: 33, 128, 141;
  --color-error-rgb: 192, 21, 47;
  --color-warning-rgb: 168, 75, 47;
  --color-info-rgb: 98, 108, 113;

  /* Typography */
  --font-family-base: "FKGroteskNeue", "Geist", "Inter", -apple-system,
    BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
  --font-family-mono: "Berkeley Mono", ui-monospace, SFMono-Regular, Menlo,
    Monaco, Consolas, monospace;
  --font-size-xs: 11px;
  --font-size-sm: 12px;
  --font-size-base: 14px;
  --font-size-md: 14px;
  --font-size-lg: 16px;
  --font-size-xl: 18px;
  --font-size-2xl: 20px;
  --font-size-3xl: 24px;
  --font-size-4xl: 30px;
  --font-weight-normal: 400;
  --font-weight-medium: 500;
  --font-weight-semibold: 550;
  --font-weight-bold: 600;
  --line-height-tight: 1.2;
  --line-height-normal: 1.5;
  --letter-spacing-tight: -0.01em;

  /* Spacing */
  --space-0: 0;
  --space-1: 1px;
  --space-2: 2px;
  --space-4: 4px;
  --space-6: 6px;
  --space-8: 8px;
  --space-10: 10px;
  --space-12: 12px;
  --space-16: 16px;
  --space-20: 20px;
  --space-24: 24px;
  --space-32: 32px;

  /* Border Radius */
  --radius-sm: 6px;
  --radius-base: 8px;
  --radius-md: 10px;
  --radius-lg: 12px;
  --radius-full: 9999px;

  /* Shadows */
  --shadow-xs: 0 1px 2px rgba(0, 0, 0, 0.02);
  --shadow-sm: 0 1px 3px rgba(0, 0, 0, 0.04), 0 1px 2px rgba(0, 0, 0, 0.02);
  --shadow-md: 0 4px 6px -1px rgba(0, 0, 0, 0.04),
    0 2px 4px -1px rgba(0, 0, 0, 0.02);
  --shadow-lg: 0 10px 15px -3px rgba(0, 0, 0, 0.04),
    0 4px 6px -2px rgba(0, 0, 0, 0.02);
  --shadow-inset-sm: inset 0 1px 0 rgba(255, 255, 255, 0.15),
    inset 0 -1px 0 rgba(0, 0, 0, 0.03);

  /* Animation */
  --duration-fast: 150ms;
  --duration-normal: 250ms;
  --ease-standard: cubic-bezier(0.16, 1, 0.3, 1);

  /* Layout */
  --container-sm: 640px;
  --container-md: 768px;
  --container-lg: 1024px;
  --container-xl: 1280px;
}

/* Dark mode colors */
@media (prefers-color-scheme: dark) {
  :root {
    /* RGB versions for opacity control (Dark Mode) */
    --color-gray-400-rgb: 119, 124, 124;
    --color-teal-300-rgb: 50, 184, 198;
    --color-gray-300-rgb: 167, 169, 169;
    --color-gray-200-rgb: 245, 245, 245;

    /* Background color tokens (Dark Mode) */
    --color-bg-1: rgba(29, 78, 216, 0.15); /* Dark blue */
    --color-bg-2: rgba(180, 83, 9, 0.15); /* Dark yellow */
    --color-bg-3: rgba(21, 128, 61, 0.15); /* Dark green */
    --color-bg-4: rgba(185, 28, 28, 0.15); /* Dark red */
    --color-bg-5: rgba(107, 33, 168, 0.15); /* Dark purple */
    --color-bg-6: rgba(194, 65, 12, 0.15); /* Dark orange */
    --color-bg-7: rgba(190, 24, 93, 0.15); /* Dark pink */
    --color-bg-8: rgba(8, 145, 178, 0.15); /* Dark cyan */
    
    /* Semantic Color Tokens (Dark Mode) */
    --color-background: var(--color-charcoal-700);
    --color-surface: var(--color-charcoal-800);
    --color-text: var(--color-gray-200);
    --color-text-secondary: rgba(var(--color-gray-300-rgb), 0.7);
    --color-primary: var(--color-teal-300);
    --color-primary-hover: var(--color-teal-400);
    --color-primary-active: var(--color-teal-800);
    --color-secondary: rgba(var(--color-gray-400-rgb), 0.15);
    --color-secondary-hover: rgba(var(--color-gray-400-rgb), 0.25);
    --color-secondary-active: rgba(var(--color-gray-400-rgb), 0.3);
    --color-border: rgba(var(--color-gray-400-rgb), 0.3);
    --color-error: var(--color-red-400);
    --color-success: var(--color-teal-300);
    --color-warning: var(--color-orange-400);
    --color-info: var(--color-gray-300);
    --color-focus-ring: rgba(var(--color-teal-300-rgb), 0.4);
    --color-btn-primary-text: var(--color-slate-900);
    --color-card-border: rgba(var(--color-gray-400-rgb), 0.2);
    --color-card-border-inner: rgba(var(--color-gray-400-rgb), 0.15);
    --shadow-inset-sm: inset 0 1px 0 rgba(255, 255, 255, 0.1),
      inset 0 -1px 0 rgba(0, 0, 0, 0.15);
    --button-border-secondary: rgba(var(--color-gray-400-rgb), 0.2);
    --color-border-secondary: rgba(var(--color-gray-400-rgb), 0.2);
    --color-select-caret: rgba(var(--color-gray-200-rgb), 0.8);

    /* Common style patterns - updated for dark mode */
    --focus-ring: 0 0 0 3px var(--color-focus-ring);
    --focus-outline: 2px solid var(--color-primary);
    --status-bg-opacity: 0.15;
    --status-border-opacity: 0.25;
    --select-caret-light: url('data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='16' height='16' viewBox='0 0 24 24' fill='none' stroke='%23134252' stroke-width='2' stroke-linecap='round' stroke-linejoin='round'%3E%3Cpolyline points='6 9 12 15 18 9'%3E%3C/polyline%3E%3C/svg%3E');
    --select-caret-dark: url('data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='16' height='16' viewBox='0 0 24 24' fill='none' stroke='%23f5f5f5' stroke-width='2' stroke-linecap='round' stroke-linejoin='round'%3E%3Cpolyline points='6 9 12 15 18 9'%3E%3C/polyline%3E%3C/svg%3E');

    /* RGB versions for dark mode */
    --color-success-rgb: var(--color-teal-300-rgb);
    --color-error-rgb: var(--color-red-400-rgb);
    --color-warning-rgb: var(--color-orange-400-rgb);
    --color-info-rgb: var(--color-gray-300-rgb);
  }
}

/* Data attribute for manual theme switching */
[data-color-scheme="dark"] {
  /* RGB versions for opacity control (dark mode) */
  --color-gray-400-rgb: 119, 124, 124;
  --color-teal-300-rgb: 50, 184, 198;
  --color-gray-300-rgb: 167, 169, 169;
  --color-gray-200-rgb: 245, 245, 245;

  /* Colorful background palette - Dark Mode */
  --color-bg-1: rgba(29, 78, 216, 0.15); /* Dark blue */
  --color-bg-2: rgba(180, 83, 9, 0.15); /* Dark yellow */
  --color-bg-3: rgba(21, 128, 61, 0.15); /* Dark green */
  --color-bg-4: rgba(185, 28, 28, 0.15); /* Dark red */
  --color-bg-5: rgba(107, 33, 168, 0.15); /* Dark purple */
  --color-bg-6: rgba(194, 65, 12, 0.15); /* Dark orange */
  --color-bg-7: rgba(190, 24, 93, 0.15); /* Dark pink */
  --color-bg-8: rgba(8, 145, 178, 0.15); /* Dark cyan */
  
  /* Semantic Color Tokens (Dark Mode) */
  --color-background: var(--color-charcoal-700);
  --color-surface: var(--color-charcoal-800);
  --color-text: var(--color-gray-200);
  --color-text-secondary: rgba(var(--color-gray-300-rgb), 0.7);
  --color-primary: var(--color-teal-300);
  --color-primary-hover: var(--color-teal-400);
  --color-primary-active: var(--color-teal-800);
  --color-secondary: rgba(var(--color-gray-400-rgb), 0.15);
  --color-secondary-hover: rgba(var(--color-gray-400-rgb), 0.25);
  --color-secondary-active: rgba(var(--color-gray-400-rgb), 0.3);
  --color-border: rgba(var(--color-gray-400-rgb), 0.3);
  --color-error: var(--color-red-400);
  --color-success: var(--color-teal-300);
  --color-warning: var(--color-orange-400);
  --color-info: var(--color-gray-300);
  --color-focus-ring: rgba(var(--color-teal-300-rgb), 0.4);
  --color-btn-primary-text: var(--color-slate-900);
  --color-card-border: rgba(var(--color-gray-400-rgb), 0.15);
  --color-card-border-inner: rgba(var(--color-gray-400-rgb), 0.15);
  --shadow-inset-sm: inset 0 1px 0 rgba(255, 255, 255, 0.1),
    inset 0 -1px 0 rgba(0, 0, 0, 0.15);
  --color-border-secondary: rgba(var(--color-gray-400-rgb), 0.2);
  --color-select-caret: rgba(var(--color-gray-200-rgb), 0.8);

  /* Common style patterns - updated for dark mode */
  --focus-ring: 0 0 0 3px var(--color-focus-ring);
  --focus-outline: 2px solid var(--color-primary);
  --status-bg-opacity: 0.15;
  --status-border-opacity: 0.25;
  --select-caret-light: url('data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='16' height='16' viewBox='0 0 24 24' fill='none' stroke='%23134252' stroke-width='2' stroke-linecap='round' stroke-linejoin='round'%3E%3Cpolyline points='6 9 12 15 18 9'%3E%3C/polyline%3E%3C/svg%3E');
  --select-caret-dark: url('data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='16' height='16' viewBox='0 0 24 24' fill='none' stroke='%23f5f5f5' stroke-width='2' stroke-linecap='round' stroke-linejoin='round'%3E%3Cpolyline points='6 9 12 15 18 9'%3E%3C/polyline%3E%3C/svg%3E');

  /* RGB versions for dark mode */
  --color-success-rgb: var(--color-teal-300-rgb);
  --color-error-rgb: var(--color-red-400-rgb);
  --color-warning-rgb: var(--color-orange-400-rgb);
  --color-info-rgb: var(--color-gray-300-rgb);
}

[data-color-scheme="light"] {
  /* RGB versions for opacity control (light mode) */
  --color-brown-600-rgb: 94, 82, 64;
  --color-teal-500-rgb: 33, 128, 141;
  --color-slate-900-rgb: 19, 52, 59;
  
  /* Semantic Color Tokens (Light Mode) */
  --color-background: var(--color-cream-50);
  --color-surface: var(--color-cream-100);
  --color-text: var(--color-slate-900);
  --color-text-secondary: var(--color-slate-500);
  --color-primary: var(--color-teal-500);
  --color-primary-hover: var(--color-teal-600);
  --color-primary-active: var(--color-teal-700);
  --color-secondary: rgba(var(--color-brown-600-rgb), 0.12);
  --color-secondary-hover: rgba(var(--color-brown-600-rgb), 0.2);
  --color-secondary-active: rgba(var(--color-brown-600-rgb), 0.25);
  --color-border: rgba(var(--color-brown-600-rgb), 0.2);
  --color-btn-primary-text: var(--color-cream-50);
  --color-card-border: rgba(var(--color-brown-600-rgb), 0.12);
  --color-card-border-inner: rgba(var(--color-brown-600-rgb), 0.12);
  --color-error: var(--color-red-500);
  --color-success: var(--color-teal-500);
  --color-warning: var(--color-orange-500);
  --color-info: var(--color-slate-500);
  --color-focus-ring: rgba(var(--color-teal-500-rgb), 0.4);

  /* RGB versions for light mode */
  --color-success-rgb: var(--color-teal-500-rgb);
  --color-error-rgb: var(--color-red-500-rgb);
  --color-warning-rgb: var(--color-orange-500-rgb);
  --color-info-rgb: var(--color-slate-500-rgb);
}

/* Base styles */
html {
  font-size: var(--font-size-base);
  font-family: var(--font-family-base);
  line-height: var(--line-height-normal);
  color: var(--color-text);
  background-color: var(--color-background);
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

body {
  margin: 0;
  padding: 0;
}

*,
*::before,
*::after {
  box-sizing: inherit;
}

/* Typography */
h1,
h2,
h3,
h4,
h5,
h6 {
  margin: 0;
  font-weight: var(--font-weight-semibold);
  line-height: var(--line-height-tight);
  color: var(--color-text);
  letter-spacing: var(--letter-spacing-tight);
}

h1 {
  font-size: var(--font-size-4xl);
}
h2 {
  font-size: var(--font-size-3xl);
}
h3 {
  font-size: var(--font-size-2xl);
}
h4 {
  font-size: var(--font-size-xl);
}
h5 {
  font-size: var(--font-size-lg);
}
h6 {
  font-size: var(--font-size-md);
}

p {
  margin: 0 0 var(--space-16) 0;
}

a {
  color: var(--color-primary);
  text-decoration: none;
  transition: color var(--duration-fast) var(--ease-standard);
}

a:hover {
  color: var(--color-primary-hover);
}

code,
pre {
  font-family: var(--font-family-mono);
  font-size: calc(var(--font-size-base) * 0.95);
  background-color: var(--color-secondary);
  border-radius: var(--radius-sm);
}

code {
  padding: var(--space-1) var(--space-4);
}

pre {
  padding: var(--space-16);
  margin: var(--space-16) 0;
  overflow: auto;
  border: 1px solid var(--color-border);
}

pre code {
  background: none;
  padding: 0;
}

/* Buttons */
.btn {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  padding: var(--space-8) var(--space-16);
  border-radius: var(--radius-base);
  font-size: var(--font-size-base);
  font-weight: 500;
  line-height: 1.5;
  cursor: pointer;
  transition: all var(--duration-normal) var(--ease-standard);
  border: none;
  text-decoration: none;
  position: relative;
}

.btn:focus-visible {
  outline: none;
  box-shadow: var(--focus-ring);
}

.btn--primary {
  background: var(--color-primary);
  color: var(--color-btn-primary-text);
}

.btn--primary:hover {
  background: var(--color-primary-hover);
}

.btn--primary:active {
  background: var(--color-primary-active);
}

.btn--secondary {
  background: var(--color-secondary);
  color: var(--color-text);
}

.btn--secondary:hover {
  background: var(--color-secondary-hover);
}

.btn--secondary:active {
  background: var(--color-secondary-active);
}

.btn--outline {
  background: transparent;
  border: 1px solid var(--color-border);
  color: var(--color-text);
}

.btn--outline:hover {
  background: var(--color-secondary);
}

.btn--sm {
  padding: var(--space-4) var(--space-12);
  font-size: var(--font-size-sm);
  border-radius: var(--radius-sm);
}

.btn--lg {
  padding: var(--space-10) var(--space-20);
  font-size: var(--font-size-lg);
  border-radius: var(--radius-md);
}

.btn--full-width {
  width: 100%;
}

.btn:disabled {
  opacity: 0.5;
  cursor: not-allowed;
}

/* Form elements */
.form-control {
  display: block;
  width: 100%;
  padding: var(--space-8) var(--space-12);
  font-size: var(--font-size-md);
  line-height: 1.5;
  color: var(--color-text);
  background-color: var(--color-surface);
  border: 1px solid var(--color-border);
  border-radius: var(--radius-base);
  transition: border-color var(--duration-fast) var(--ease-standard),
    box-shadow var(--duration-fast) var(--ease-standard);
}

textarea.form-control {
  font-family: var(--font-family-base);
  font-size: var(--font-size-base);
}

select.form-control {
  padding: var(--space-8) var(--space-12);
  -webkit-appearance: none;
  -moz-appearance: none;
  appearance: none;
  background-image: var(--select-caret-light);
  background-repeat: no-repeat;
  background-position: right var(--space-12) center;
  background-size: 16px;
  padding-right: var(--space-32);
}

/* Add a dark mode specific caret */
@media (prefers-color-scheme: dark) {
  select.form-control {
    background-image: var(--select-caret-dark);
  }
}

/* Also handle data-color-scheme */
[data-color-scheme="dark"] select.form-control {
  background-image: var(--select-caret-dark);
}

[data-color-scheme="light"] select.form-control {
  background-image: var(--select-caret-light);
}

.form-control:focus {
  border-color: var(--color-primary);
  outline: var(--focus-outline);
}

.form-label {
  display: block;
  margin-bottom: var(--space-8);
  font-weight: var(--font-weight-medium);
  font-size: var(--font-size-sm);
}

.form-group {
  margin-bottom: var(--space-16);
}

/* Card component */
.card {
  background-color: var(--color-surface);
  border-radius: var(--radius-lg);
  border: 1px solid var(--color-card-border);
  box-shadow: var(--shadow-sm);
  overflow: hidden;
  transition: box-shadow var(--duration-normal) var(--ease-standard);
}

.card:hover {
  box-shadow: var(--shadow-md);
}

.card__body {
  padding: var(--space-16);
}

.card__header,
.card__footer {
  padding: var(--space-16);
  border-bottom: 1px solid var(--color-card-border-inner);
}

/* Status indicators - simplified with CSS variables */
.status {
  display: inline-flex;
  align-items: center;
  padding: var(--space-6) var(--space-12);
  border-radius: var(--radius-full);
  font-weight: var(--font-weight-medium);
  font-size: var(--font-size-sm);
}

.status--success {
  background-color: rgba(
    var(--color-success-rgb, 33, 128, 141),
    var(--status-bg-opacity)
  );
  color: var(--color-success);
  border: 1px solid
    rgba(var(--color-success-rgb, 33, 128, 141), var(--status-border-opacity));
}

.status--error {
  background-color: rgba(
    var(--color-error-rgb, 192, 21, 47),
    var(--status-bg-opacity)
  );
  color: var(--color-error);
  border: 1px solid
    rgba(var(--color-error-rgb, 192, 21, 47), var(--status-border-opacity));
}

.status--warning {
  background-color: rgba(
    var(--color-warning-rgb, 168, 75, 47),
    var(--status-bg-opacity)
  );
  color: var(--color-warning);
  border: 1px solid
    rgba(var(--color-warning-rgb, 168, 75, 47), var(--status-border-opacity));
}

.status--info {
  background-color: rgba(
    var(--color-info-rgb, 98, 108, 113),
    var(--status-bg-opacity)
  );
  color: var(--color-info);
  border: 1px solid
    rgba(var(--color-info-rgb, 98, 108, 113), var(--status-border-opacity));
}

/* Container layout */
.container {
  width: 100%;
  margin-right: auto;
  margin-left: auto;
  padding-right: var(--space-16);
  padding-left: var(--space-16);
}

@media (min-width: 640px) {
  .container {
    max-width: var(--container-sm);
  }
}
@media (min-width: 768px) {
  .container {
    max-width: var(--container-md);
  }
}
@media (min-width: 1024px) {
  .container {
    max-width: var(--container-lg);
  }
}
@media (min-width: 1280px) {
  .container {
    max-width: var(--container-xl);
  }
}

/* Utility classes */
.flex {
  display: flex;
}
.flex-col {
  flex-direction: column;
}
.items-center {
  align-items: center;
}
.justify-center {
  justify-content: center;
}
.justify-between {
  justify-content: space-between;
}
.gap-4 {
  gap: var(--space-4);
}
.gap-8 {
  gap: var(--space-8);
}
.gap-16 {
  gap: var(--space-16);
}

.m-0 {
  margin: 0;
}
.mt-8 {
  margin-top: var(--space-8);
}
.mb-8 {
  margin-bottom: var(--space-8);
}
.mx-8 {
  margin-left: var(--space-8);
  margin-right: var(--space-8);
}
.my-8 {
  margin-top: var(--space-8);
  margin-bottom: var(--space-8);
}

.p-0 {
  padding: 0;
}
.py-8 {
  padding-top: var(--space-8);
  padding-bottom: var(--space-8);
}
.px-8 {
  padding-left: var(--space-8);
  padding-right: var(--space-8);
}
.py-16 {
  padding-top: var(--space-16);
  padding-bottom: var(--space-16);
}
.px-16 {
  padding-left: var(--space-16);
  padding-right: var(--space-16);
}

.block {
  display: block;
}
.hidden {
  display: none;
}

/* Accessibility */
.sr-only {
  position: absolute;
  width: 1px;
  height: 1px;
  padding: 0;
  margin: -1px;
  overflow: hidden;
  clip: rect(0, 0, 0, 0);
  white-space: nowrap;
  border-width: 0;
}

:focus-visible {
  outline: var(--focus-outline);
  outline-offset: 2px;
}

/* Dark mode specifics */
[data-color-scheme="dark"] .btn--outline {
  border: 1px solid var(--color-border-secondary);
}

@font-face {
  font-family: 'FKGroteskNeue';
  src: url('https://r2cdn.perplexity.ai/fonts/FKGroteskNeue.woff2')
    format('woff2');
}

/* END PERPLEXITY DESIGN SYSTEM */
/* Custom variables */
:root {
  --neon-blue: #00BFFF;
  --neon-red: #FF1744;
  --crimson: #DC143C;
  --dark-blue: #001122;
  --particle-color: rgba(0, 191, 255, 0.6);
  --ground-color: #8B4513;
  --building-color: #696969;
  --special-color: #4169E1;
}

/* Base reset and styles */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: var(--font-family-base);
  background: radial-gradient(circle at center, var(--dark-blue) 0%, var(--color-slate-900) 100%);
  color: var(--color-text);
  overflow: hidden;
  height: 100vh;
  width: 100vw;
  position: relative;
}

/* Canvas styles */
#gameCanvas {
  position: absolute;
  top: 0;
  left: 0;
  z-index: 1;
  background: transparent;
  image-rendering: pixelated;
}

/* Particles background */
.particles {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: 0;
  pointer-events: none;
}

.particle {
  position: absolute;
  width: 2px;
  height: 2px;
  background: var(--particle-color);
  border-radius: 50%;
  animation: float 6s ease-in-out infinite;
}

@keyframes float {
  0%, 100% { 
    transform: translateY(0px) scale(1);
    opacity: 0.3;
  }
  50% { 
    transform: translateY(-20px) scale(1.2);
    opacity: 0.7;
  }
}

/* Menu overlays */
.menu-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  background: rgba(0, 0, 0, 0.9);
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 1000;
}

.menu-content {
  text-align: center;
  padding: var(--space-32);
  max-width: 600px;
  width: 90%;
}

.game-title {
  font-size: 3rem;
  font-weight: var(--font-weight-bold);
  margin-bottom: var(--space-32);
  color: var(--neon-blue);
  text-shadow: 0 0 20px var(--neon-blue);
  animation: glow 2s ease-in-out infinite alternate;
}

@keyframes glow {
  from { text-shadow: 0 0 20px var(--neon-blue); }
  to { text-shadow: 0 0 30px var(--neon-blue), 0 0 40px var(--neon-blue); }
}

.menu-buttons {
  display: flex;
  flex-direction: column;
  gap: var(--space-16);
  align-items: center;
}

/* Enhanced button styles */
.btn {
  position: relative;
  background: linear-gradient(45deg, var(--neon-red), var(--crimson));
  border: 2px solid transparent;
  color: var(--color-white);
  padding: var(--space-12) var(--space-24);
  font-size: var(--font-size-lg);
  font-weight: var(--font-weight-semibold);
  border-radius: var(--radius-lg);
  cursor: pointer;
  transition: all var(--duration-normal) var(--ease-standard);
  text-transform: uppercase;
  letter-spacing: 1px;
  min-width: 150px;
}

.btn:hover {
  transform: translateY(-2px);
  box-shadow: 0 10px 25px rgba(220, 20, 60, 0.4);
}

.btn--secondary {
  background: transparent;
  border: 2px solid var(--neon-blue);
  color: var(--neon-blue);
}

.btn--secondary:hover {
  background: var(--neon-blue);
  color: var(--color-slate-900);
  box-shadow: 0 10px 25px rgba(0, 191, 255, 0.4);
}

.btn--outline {
  background: transparent;
  border: 2px solid var(--color-gray-300);
  color: var(--color-gray-300);
}

.btn--outline:hover {
  background: var(--color-gray-300);
  color: var(--color-slate-900);
}

/* Level selection enhancements */
.level-info {
  margin: var(--space-16) 0;
  color: var(--color-text-secondary);
  font-size: var(--font-size-base);
}

.level-grid {
  display: grid;
  grid-template-columns: repeat(5, 1fr);
  gap: var(--space-16);
  margin: var(--space-24) 0;
}

.level-btn {
  width: 60px;
  height: 60px;
  border: 2px solid var(--neon-blue);
  background: transparent;
  color: var(--neon-blue);
  font-size: var(--font-size-xl);
  font-weight: var(--font-weight-bold);
  border-radius: var(--radius-base);
  cursor: pointer;
  transition: all var(--duration-fast) var(--ease-standard);
  position: relative;
}

.level-btn:hover {
  background: var(--neon-blue);
  color: var(--color-slate-900);
  transform: scale(1.1);
}

.level-btn::after {
  content: attr(data-level-name);
  position: absolute;
  top: -30px;
  left: 50%;
  transform: translateX(-50%);
  font-size: var(--font-size-xs);
  color: var(--color-text-secondary);
  white-space: nowrap;
  opacity: 0;
  transition: opacity var(--duration-fast);
}

.level-btn:hover::after {
  opacity: 1;
}

/* Platform type legend */
.level-legend {
  display: flex;
  justify-content: center;
  gap: var(--space-24);
  margin: var(--space-20) 0;
  flex-wrap: wrap;
}

.legend-item {
  display: flex;
  align-items: center;
  gap: var(--space-8);
  color: var(--color-text-secondary);
  font-size: var(--font-size-sm);
}

.platform-demo {
  width: 30px;
  height: 12px;
  border: 1px solid var(--color-white);
  border-radius: var(--radius-sm);
}

.platform-demo.ground {
  background: var(--ground-color);
}

.platform-demo.building {
  background: var(--building-color);
}

.platform-demo.special {
  background: var(--special-color);
}

/* HUD styles */
.hud {
  position: fixed;
  top: var(--space-16);
  left: var(--space-16);
  right: var(--space-16);
  display: flex;
  justify-content: space-between;
  align-items: center;
  z-index: 100;
  color: var(--color-white);
  font-weight: var(--font-weight-semibold);
}

.hud-left {
  background: rgba(0, 0, 0, 0.7);
  padding: var(--space-8) var(--space-16);
  border-radius: var(--radius-base);
  border: 1px solid var(--neon-blue);
  display: flex;
  flex-direction: column;
  gap: var(--space-4);
}

.level-name {
  font-size: var(--font-size-sm);
  color: var(--neon-blue);
  opacity: 0.8;
}

.hud-right {
  display: flex;
  gap: var(--space-8);
}

.hud-btn {
  width: 40px;
  height: 40px;
  background: rgba(0, 0, 0, 0.7);
  border: 1px solid var(--neon-blue);
  color: var(--neon-blue);
  border-radius: var(--radius-base);
  cursor: pointer;
  font-size: var(--font-size-lg);
  display: flex;
  align-items: center;
  justify-content: center;
  transition: all var(--duration-fast) var(--ease-standard);
}

.hud-btn:hover {
  background: var(--neon-blue);
  color: var(--color-slate-900);
}

/* Victory overlay enhancements */
.victory-stats {
  margin: var(--space-16) 0;
  color: var(--color-text-secondary);
}

.victory-buttons {
  display: flex;
  flex-direction: column;
  gap: var(--space-16);
  align-items: center;
  margin-top: var(--space-24);
}

/* Mobile controls enhancements */
.mobile-controls {
  position: fixed;
  bottom: var(--space-16);
  left: var(--space-16);
  right: var(--space-16);
  display: flex;
  justify-content: space-between;
  align-items: flex-end;
  z-index: 200;
  pointer-events: none;
}

.control-left,
.control-right {
  display: flex;
  gap: var(--space-8);
  pointer-events: all;
}

.control-center {
  display: flex;
  flex-direction: column;
  align-items: center;
  pointer-events: none;
}

.control-tips {
  background: rgba(0, 0, 0, 0.8);
  color: var(--neon-blue);
  padding: var(--space-6) var(--space-12);
  border-radius: var(--radius-base);
  font-size: var(--font-size-sm);
  margin-bottom: var(--space-8);
  border: 1px solid var(--neon-blue);
  animation: tipPulse 3s ease-in-out infinite;
}

@keyframes tipPulse {
  0%, 100% { opacity: 0.7; }
  50% { opacity: 1; }
}

.control-btn {
  width: 60px;
  height: 60px;
  background: rgba(0, 0, 0, 0.8);
  border: 2px solid var(--neon-blue);
  color: var(--neon-blue);
  border-radius: 50%;
  font-size: var(--font-size-2xl);
  font-weight: var(--font-weight-bold);
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  transition: all var(--duration-fast) var(--ease-standard);
  user-select: none;
  -webkit-user-select: none;
  -webkit-tap-highlight-color: transparent;
}

.control-btn:active,
.control-btn.active {
  background: var(--neon-blue);
  color: var(--color-slate-900);
  transform: scale(0.95);
}

/* Instructions hint */
.instructions-hint {
  position: fixed;
  top: 70px;
  left: 50%;
  transform: translateX(-50%);
  z-index: 150;
  animation: slideInDown 0.5s ease-out;
}

@keyframes slideInDown {
  from {
    opacity: 0;
    transform: translateX(-50%) translateY(-20px);
  }
  to {
    opacity: 1;
    transform: translateX(-50%) translateY(0);
  }
}

.hint-content {
  background: rgba(0, 0, 0, 0.9);
  color: var(--color-white);
  padding: var(--space-12) var(--space-20);
  border-radius: var(--radius-base);
  border: 1px solid var(--neon-blue);
  font-size: var(--font-size-sm);
  max-width: 300px;
  position: relative;
}

.close-hint {
  position: absolute;
  top: var(--space-4);
  right: var(--space-8);
  background: none;
  border: none;
  color: var(--neon-blue);
  cursor: pointer;
  font-size: var(--font-size-lg);
  line-height: 1;
  padding: 0;
  width: 20px;
  height: 20px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.close-hint:hover {
  color: var(--color-white);
}

/* Utility classes */
.hidden {
  display: none !important;
}

/* Responsive design */
@media (max-width: 768px) {
  .game-title {
    font-size: 2rem;
  }
  
  .menu-content {
    padding: var(--space-16);
  }
  
  .btn {
    font-size: var(--font-size-base);
    padding: var(--space-10) var(--space-20);
  }
  
  .level-btn {
    width: 50px;
    height: 50px;
    font-size: var(--font-size-lg);
  }
  
  .level-grid {
    gap: var(--space-12);
  }
  
  .level-legend {
    gap: var(--space-16);
  }
  
  .legend-item {
    font-size: var(--font-size-xs);
  }
  
  .platform-demo {
    width: 25px;
    height: 10px;
  }
  
  .control-tips {
    font-size: var(--font-size-xs);
    padding: var(--space-4) var(--space-8);
  }
}

@media (max-width: 480px) {
  .game-title {
    font-size: 1.5rem;
  }
  
  .control-btn {
    width: 50px;
    height: 50px;
    font-size: var(--font-size-xl);
  }
  
  .hud-btn {
    width: 35px;
    height: 35px;
    font-size: var(--font-size-base);
  }
  
  .level-legend {
    flex-direction: column;
    gap: var(--space-8);
    align-items: center;
  }
  
  .instructions-hint {
    left: var(--space-8);
    right: var(--space-8);
    transform: none;
  }
  
  .hint-content {
    max-width: none;
    width: 100%;
  }
}

@media (orientation: landscape) and (max-height: 500px) {
  .mobile-controls {
    bottom: var(--space-8);
  }
  
  .control-btn {
    width: 45px;
    height: 45px;
    font-size: var(--font-size-lg);
  }
  
  .hud {
    top: var(--space-8);
  }
  
  .instructions-hint {
    top: 50px;
  }
}

/* High contrast for accessibility */
@media (prefers-contrast: high) {
  .btn {
    border-width: 3px;
  }
  
  .control-btn {
    border-width: 3px;
  }
  
  .hud-btn {
    border-width: 2px;
  }
  
  .platform-demo {
    border-width: 2px;
  }
}

/* Reduced motion for accessibility */
@media (prefers-reduced-motion: reduce) {
  .game-title {
    animation: none;
  }
  
  .particle {
    animation: none;
  }
  
  .control-tips {
    animation: none;
  }
  
  .instructions-hint {
    animation: none;
  }
  
  .btn:hover {
    transform: none;
  }
  
  .level-btn:hover {
    transform: none;
  }
}
</style>
</head>
<body>
    <!-- Particle Background -->
    <div class="particles" id="particles"></div>

    <!-- Game Canvas -->
    <canvas id="gameCanvas"></canvas>

    <!-- Main Menu -->
    <div id="mainMenu" class="menu-overlay">
        <div class="menu-content">
            <h1 class="game-title">Spider-Man: Web Slinger</h1>
            <div class="menu-buttons">
                <button id="playButton" class="btn btn--primary btn--lg">PLAY</button>
                <button id="levelsButton" class="btn btn--secondary btn--lg">LEVELS</button>
                <button id="audioButton" class="btn btn--secondary btn--lg">ðŸ”Š MUSIC</button>
            </div>
        </div>
    </div>

    <!-- Level Select Menu -->
    <div id="levelMenu" class="menu-overlay hidden">
        <div class="menu-content">
            <h2>Select Level</h2>
            <div class="level-info">
                <p>Game designed by Bapi:) with AI</p>
            </div>
            <div class="level-grid">
                <button class="level-btn" data-level="1" title="Tutorial - Easy horizontal progression">1</button>
                <button class="level-btn" data-level="2" data-level-name="Stepping Up">2</button>
                <button class="level-btn" data-level="3" data-level-name="Zigzag Challenge">3</button>
                <button class="level-btn" data-level="4" data-level-name="Tower Climb">4</button>
                <button class="level-btn" data-level="5" data-level-name="Complex Maze">5</button>
            </div>
            <div class="level-legend">
                <div class="legend-item">
                    <div class="platform-demo ground"></div>
                    <span>Ground Platforms</span>
                </div>
                <div class="legend-item">
                    <div class="platform-demo building"></div>
                    <span>Building Platforms</span>
                </div>
                <div class="legend-item">
                    <div class="platform-demo special"></div>
                    <span>Special Platforms</span>
                </div>
            </div>
            <button id="backToMenuButton" class="btn btn--outline">Back</button>
        </div>
    </div>

    <!-- In-Game HUD -->
    <div id="gameHUD" class="hud hidden">
        <div class="hud-left">
            <span id="targetsRemaining">Targets: 0</span>
            <span id="levelName" class="level-name"></span>
        </div>
        <div class="hud-right">
            <button id="menuButton" class="hud-btn" aria-label="Menu">â˜°</button>
            <button id="audioToggle" class="hud-btn" aria-label="Toggle Audio">ðŸ”Š</button>
        </div>
    </div>

    <!-- Victory Overlay -->
    <div id="victoryOverlay" class="menu-overlay hidden">
        <div class="menu-content">
            <h2>Level Complete!</h2>
            <div class="victory-stats">
                <p id="levelCompleteMessage">Great job navigating the platforms!</p>
            </div>
            <div class="victory-buttons">
                <button id="nextLevelButton" class="btn btn--primary">Next Level</button>
                <button id="playAgainButton" class="btn btn--secondary">Play Again</button>
                <button id="backToMenuFromVictory" class="btn btn--outline">Main Menu</button>
            </div>
        </div>
    </div>

    <!-- Mobile Controls -->
    <div id="mobileControls" class="mobile-controls hidden">
        <div class="control-left">
            <button class="control-btn" id="leftButton" aria-label="Move Left">â†</button>
            <button class="control-btn" id="rightButton" aria-label="Move Right">â†’</button>
        </div>
        <div class="control-center">
           
        </div>
        <div class="control-right">
            <button class="control-btn" id="jumpButton" aria-label="Jump">â†‘</button>
            <button class="control-btn" id="shootButton" aria-label="Shoot Web">â­˜</button>
        </div>
    </div>

    <!-- Instructions Overlay -->
    <div id="instructionsHint" class="instructions-hint hidden">
        <div class="hint-content">
            <p>ðŸ’¡ <strong>Pro Tip:</strong> All platforms are reachable! Look for the path between platforms.</p>
            <button class="close-hint" onclick="this.parentElement.parentElement.style.display='none'">Ã—</button>
        </div>
    </div>

    <script>
/* inlined from app.js */
// Game Constants
const WORLD_WIDTH = 5000;
const WORLD_HEIGHT = 1000;
const GRAVITY = 0.6; // Reduced gravity for better jump control
const JUMP_FORCE = -18; // Increased jump force
const MOVE_SPEED = 6; // Increased move speed
const WEB_SPEED = 8;
const WEB_COOLDOWN = 250;
const MAX_WEBS = 50;
const MAX_PARTICLES = 200;

// Predefined Level Layouts - Adjusted for better reachability
const LEVEL_LAYOUTS = {
    1: {
        name: "DragonBeast",
        platforms: [
            {x: 0, y: 960, width: 200, height: 40, type: "ground"},
            {x: 220, y: 860, width: 120, height: 20, type: "building"}, // Closer gap
            {x: 380, y: 780, width: 140, height: 20, type: "building"}, // Better spacing
            {x: 560, y: 860, width: 120, height: 20, type: "building"}, // Stepped down
            {x: 720, y: 960, width: 180, height: 40, type: "ground"}, // Safe landing
            {x: 940, y: 880, width: 120, height: 20, type: "building"},
            {x: 1100, y: 800, width: 140, height: 20, type: "building"},
            {x: 1280, y: 960, width: 200, height: 40, type: "ground"}
        ],
        targets: [
            {platformIndex: 1, offset: 50},
            {platformIndex: 2, offset: 60},
            {platformIndex: 3, offset: 50},
            {platformIndex: 5, offset: 50},
            {platformIndex: 6, offset: 60}
        ]
    },
    2: {
        name: "Stepping Up",
        platforms: [
            {x: 0, y: 960, width: 180, height: 40, type: "ground"},
            {x: 200, y: 880, width: 100, height: 20, type: "building"},
            {x: 340, y: 820, width: 110, height: 20, type: "building"},
            {x: 490, y: 760, width: 120, height: 20, type: "building"},
            {x: 650, y: 820, width: 100, height: 20, type: "building"},
            {x: 790, y: 880, width: 110, height: 20, type: "building"},
            {x: 940, y: 960, width: 200, height: 40, type: "ground"},
            {x: 1180, y: 860, width: 120, height: 20, type: "building"},
            {x: 1340, y: 800, width: 130, height: 20, type: "building"},
            {x: 1510, y: 860, width: 120, height: 20, type: "building"}
        ],
        targets: [
            {platformIndex: 1, offset: 40},
            {platformIndex: 2, offset: 50},
            {platformIndex: 3, offset: 60},
            {platformIndex: 4, offset: 40},
            {platformIndex: 5, offset: 50},
            {platformIndex: 7, offset: 60},
            {platformIndex: 8, offset: 65}
        ]
    },
    3: {
        name: "Zigzag Challenge",
        platforms: [
            {x: 0, y: 960, width: 150, height: 40, type: "ground"},
            {x: 180, y: 860, width: 110, height: 20, type: "building"},
            {x: 330, y: 760, width: 100, height: 20, type: "building"},
            {x: 470, y: 680, width: 110, height: 20, type: "building"},
            {x: 620, y: 760, width: 100, height: 20, type: "building"},
            {x: 760, y: 860, width: 110, height: 20, type: "building"},
            {x: 910, y: 760, width: 100, height: 20, type: "building"},
            {x: 1050, y: 680, width: 110, height: 20, type: "building"},
            {x: 1200, y: 760, width: 100, height: 20, type: "building"},
            {x: 1340, y: 860, width: 110, height: 20, type: "building"},
            {x: 1490, y: 960, width: 180, height: 40, type: "ground"},
            {x: 1710, y: 880, width: 100, height: 20, type: "building"},
            {x: 1850, y: 820, width: 110, height: 20, type: "building"}
        ],
        targets: [
            {platformIndex: 1, offset: 55},
            {platformIndex: 2, offset: 50},
            {platformIndex: 3, offset: 55},
            {platformIndex: 4, offset: 50},
            {platformIndex: 5, offset: 55},
            {platformIndex: 6, offset: 50},
            {platformIndex: 7, offset: 55},
            {platformIndex: 8, offset: 50},
            {platformIndex: 9, offset: 55},
            {platformIndex: 11, offset: 50}
        ]
    },
    4: {
        name: "Tower Climb",
        platforms: [
            {x: 0, y: 960, width: 200, height: 40, type: "ground"},
            {x: 240, y: 880, width: 110, height: 20, type: "building"},
            {x: 390, y: 820, width: 100, height: 20, type: "building"},
            {x: 530, y: 760, width: 110, height: 20, type: "building"},
            {x: 680, y: 700, width: 100, height: 20, type: "building"},
            {x: 820, y: 640, width: 110, height: 20, type: "building"},
            {x: 970, y: 580, width: 100, height: 15, type: "special"},
            {x: 1110, y: 640, width: 110, height: 20, type: "building"},
            {x: 1260, y: 700, width: 100, height: 20, type: "building"},
            {x: 1400, y: 760, width: 110, height: 20, type: "building"},
            {x: 1550, y: 820, width: 100, height: 20, type: "building"},
            {x: 1690, y: 880, width: 120, height: 20, type: "building"},
            {x: 1850, y: 960, width: 200, height: 40, type: "ground"},
            {x: 2090, y: 860, width: 110, height: 20, type: "building"},
            {x: 2240, y: 780, width: 100, height: 20, type: "building"}
        ],
        targets: [
            {platformIndex: 1, offset: 55},
            {platformIndex: 2, offset: 50},
            {platformIndex: 3, offset: 55},
            {platformIndex: 4, offset: 50},
            {platformIndex: 5, offset: 55},
            {platformIndex: 6, offset: 50},
            {platformIndex: 7, offset: 55},
            {platformIndex: 8, offset: 50},
            {platformIndex: 9, offset: 55},
            {platformIndex: 10, offset: 50},
            {platformIndex: 11, offset: 60},
            {platformIndex: 13, offset: 55}
        ]
    },
    5: {
        name: "Complex Maze",
        platforms: [
            {x: 0, y: 960, width: 150, height: 40, type: "ground"},
            {x: 180, y: 880, width: 100, height: 20, type: "building"},
            {x: 320, y: 800, width: 110, height: 20, type: "building"},
            {x: 470, y: 720, width: 100, height: 15, type: "special"},
            {x: 610, y: 640, width: 110, height: 15, type: "special"},
            {x: 760, y: 560, width: 100, height: 15, type: "special"},
            {x: 900, y: 640, width: 110, height: 15, type: "special"},
            {x: 1050, y: 720, width: 100, height: 20, type: "building"},
            {x: 1190, y: 800, width: 110, height: 20, type: "building"},
            {x: 1340, y: 880, width: 100, height: 20, type: "building"},
            {x: 1480, y: 960, width: 180, height: 40, type: "ground"},
            {x: 1700, y: 880, width: 100, height: 20, type: "building"},
            {x: 1840, y: 820, width: 110, height: 20, type: "building"},
            {x: 1990, y: 760, width: 100, height: 20, type: "building"},
            {x: 2130, y: 700, width: 110, height: 15, type: "special"},
            {x: 2280, y: 760, width: 100, height: 20, type: "building"},
            {x: 2420, y: 820, width: 110, height: 20, type: "building"},
            {x: 2570, y: 880, width: 100, height: 20, type: "building"},
            {x: 2710, y: 960, width: 200, height: 40, type: "ground"}
        ],
        targets: [
            {platformIndex: 1, offset: 50},
            {platformIndex: 2, offset: 55},
            {platformIndex: 3, offset: 50},
            {platformIndex: 4, offset: 55},
            {platformIndex: 5, offset: 50},
            {platformIndex: 6, offset: 55},
            {platformIndex: 7, offset: 50},
            {platformIndex: 8, offset: 55},
            {platformIndex: 9, offset: 50},
            {platformIndex: 11, offset: 50},
            {platformIndex: 12, offset: 55},
            {platformIndex: 13, offset: 50},
            {platformIndex: 14, offset: 55},
            {platformIndex: 15, offset: 50},
            {platformIndex: 16, offset: 55}
        ]
    }
};

// Game State
const gameState = {
    canvas: null,
    ctx: null,
    camera: { x: 0, y: 0 },
    currentLevel: 1,
    isPlaying: false,
    isPaused: false,
    lastTime: 0,
    
    player: {
        x: 100,
        y: 500,
        width: 30,
        height: 40,
        velocityX: 0,
        velocityY: 0,
        onGround: false,
        jumpPressed: false,
        airTime: 0
    },
    
    platforms: [],
    targets: [],
    webs: [],
    particles: [],
    
    input: {
        left: false,
        right: false,
        up: false,
        space: false
    },
    
    mobileControls: {
        leftPressed: false,
        rightPressed: false,
        jumpPressed: false,
        shootPressed: false
    },
    
    webCooldownTimer: 0,
    targetsRemaining: 0,
    levelComplete: false,
    audioEnabled: true
};

// Audio Manager Class
class AudioManager {
    constructor() {
        this.audioContext = null;
        this.sounds = {};
        this.backgroundMusic = null;
        this.enabled = true;
    }

    async init() {
        try {
            this.audioContext = new (window.AudioContext || window.webkitAudioContext)();
            
            if (this.audioContext.state === 'suspended') {
                const resumeAudio = () => {
                    this.resume();
                    document.removeEventListener('click', resumeAudio);
                    document.removeEventListener('touchstart', resumeAudio);
                };
                document.addEventListener('click', resumeAudio);
                document.addEventListener('touchstart', resumeAudio);
            }
        } catch (error) {
            console.warn('Audio context creation failed:', error);
            this.enabled = false;
        }
    }

    resume() {
        if (this.audioContext && this.audioContext.state === 'suspended') {
            this.audioContext.resume();
        }
    }

    playTone(frequency, duration, type = 'sine', volume = 0.3) {
        if (!this.enabled || !this.audioContext) return;

        try {
            const oscillator = this.audioContext.createOscillator();
            const gainNode = this.audioContext.createGain();

            oscillator.connect(gainNode);
            gainNode.connect(this.audioContext.destination);

            oscillator.frequency.setValueAtTime(frequency, this.audioContext.currentTime);
            oscillator.type = type;

            gainNode.gain.setValueAtTime(0, this.audioContext.currentTime);
            gainNode.gain.linearRampToValueAtTime(volume, this.audioContext.currentTime + 0.01);
            gainNode.gain.linearRampToValueAtTime(0, this.audioContext.currentTime + duration);

            oscillator.start(this.audioContext.currentTime);
            oscillator.stop(this.audioContext.currentTime + duration);
        } catch (error) {
            console.warn('Audio playback failed:', error);
        }
    }

    jump() {
        this.playTone(400, 0.2, 'square', 0.2);
    }

    shoot() {
        this.playTone(800, 0.1, 'sawtooth', 0.15);
    }

    hit() {
        this.playTone(600, 0.3, 'triangle', 0.25);
    }

    victory() {
        setTimeout(() => this.playTone(523, 0.2), 0);
        setTimeout(() => this.playTone(659, 0.2), 200);
        setTimeout(() => this.playTone(784, 0.4), 400);
    }

    click() {
        this.playTone(1000, 0.05, 'square', 0.1);
    }

    startBackgroundMusic() {
        if (!this.enabled || !this.audioContext || this.backgroundMusic) return;

        try {
            const oscillator1 = this.audioContext.createOscillator();
            const oscillator2 = this.audioContext.createOscillator();
            const gainNode = this.audioContext.createGain();

            oscillator1.connect(gainNode);
            oscillator2.connect(gainNode);
            gainNode.connect(this.audioContext.destination);

            oscillator1.frequency.setValueAtTime(220, this.audioContext.currentTime);
            oscillator2.frequency.setValueAtTime(330, this.audioContext.currentTime);
            
            oscillator1.type = 'sine';
            oscillator2.type = 'sine';

            gainNode.gain.setValueAtTime(0.05, this.audioContext.currentTime);

            oscillator1.start();
            oscillator2.start();

            this.backgroundMusic = { oscillator1, oscillator2, gainNode };
        } catch (error) {
            console.warn('Background music failed:', error);
        }
    }

    stopBackgroundMusic() {
        if (this.backgroundMusic) {
            try {
                this.backgroundMusic.oscillator1.stop();
                this.backgroundMusic.oscillator2.stop();
            } catch (error) {
                console.warn('Error stopping background music:', error);
            }
            this.backgroundMusic = null;
        }
    }

    toggle() {
        this.enabled = !this.enabled;
        if (!this.enabled) {
            this.stopBackgroundMusic();
        }
        return this.enabled;
    }
}

// Global audio manager instance
const audioManager = new AudioManager();

// Helper Functions
function resizeCanvas() {
    if (!gameState.canvas) return;
    
    gameState.canvas.width = window.innerWidth;
    gameState.canvas.height = window.innerHeight;
}

function checkCollision(rect1, rect2) {
    return rect1.x < rect2.x + rect2.width &&
           rect1.x + rect1.width > rect2.x &&
           rect1.y < rect2.y + rect2.height &&
           rect1.y + rect1.height > rect2.y;
}

// Create platforms from predefined layout
function createPlatforms(level) {
    const layout = LEVEL_LAYOUTS[level];
    if (!layout) {
        console.error(`No layout found for level ${level}`);
        return [];
    }
    
    return layout.platforms.map(p => ({
        x: p.x,
        y: p.y,
        width: p.width,
        height: p.height,
        type: p.type
    }));
}

// Create targets from predefined layout
function createTargets(level) {
    const layout = LEVEL_LAYOUTS[level];
    if (!layout || !layout.targets) {
        console.error(`No target layout found for level ${level}`);
        return [];
    }
    
    const targets = [];
    const platforms = gameState.platforms;
    
    layout.targets.forEach(targetData => {
        const platform = platforms[targetData.platformIndex];
        if (platform) {
            targets.push({
                x: platform.x + targetData.offset,
                y: platform.y - 35,
                width: 30,
                height: 30,
                pulse: Math.random() * Math.PI * 2
            });
        }
    });
    
    console.log(`Created ${targets.length} targets for level ${level}`);
    return targets;
}

function createParticles() {
    const particleContainer = document.getElementById('particles');
    if (particleContainer) {
        particleContainer.innerHTML = '';
        
        for (let i = 0; i < 30; i++) {
            const particle = document.createElement('div');
            particle.className = 'particle';
            particle.style.left = Math.random() * 100 + '%';
            particle.style.top = Math.random() * 100 + '%';
            particle.style.animationDelay = Math.random() * 6 + 's';
            particle.style.animationDuration = (4 + Math.random() * 4) + 's';
            particleContainer.appendChild(particle);
        }
    }
}

// Input Handlers
function setupKeyboardInput() {
    const keys = {
        'ArrowLeft': 'left', 'KeyA': 'left',
        'ArrowRight': 'right', 'KeyD': 'right',
        'ArrowUp': 'up', 'KeyW': 'up',
        'Space': 'space'
    };

    document.addEventListener('keydown', (e) => {
        if (keys[e.code] && gameState.isPlaying) {
            e.preventDefault();
            gameState.input[keys[e.code]] = true;
        }
    });

    document.addEventListener('keyup', (e) => {
        if (keys[e.code]) {
            e.preventDefault();
            gameState.input[keys[e.code]] = false;
        }
    });
}

function setupTouchInput() {
    const buttons = {
        leftButton: 'leftPressed',
        rightButton: 'rightPressed',
        jumpButton: 'jumpPressed',
        shootButton: 'shootPressed'
    };

    Object.keys(buttons).forEach(buttonId => {
        const button = document.getElementById(buttonId);
        if (!button) return;
        
        const controlKey = buttons[buttonId];

        ['touchstart', 'mousedown'].forEach(eventType => {
            button.addEventListener(eventType, (e) => {
                e.preventDefault();
                e.stopPropagation();
                gameState.mobileControls[controlKey] = true;
                button.classList.add('active');
            });
        });

        ['touchend', 'mouseup', 'touchcancel'].forEach(eventType => {
            button.addEventListener(eventType, (e) => {
                e.preventDefault();
                e.stopPropagation();
                gameState.mobileControls[controlKey] = false;
                button.classList.remove('active');
            });
        });
    });
}

// Game Logic - Enhanced jump physics
function updatePlayer(deltaTime) {
    const player = gameState.player;
    
    const leftPressed = gameState.input.left || gameState.mobileControls.leftPressed;
    const rightPressed = gameState.input.right || gameState.mobileControls.rightPressed;
    const jumpPressed = gameState.input.up || gameState.mobileControls.jumpPressed;
    const shootPressed = gameState.input.space || gameState.mobileControls.shootPressed;

    // Enhanced horizontal movement with momentum
    if (leftPressed) {
        player.velocityX = -MOVE_SPEED;
    } else if (rightPressed) {
        player.velocityX = MOVE_SPEED;
    } else {
        // Reduced friction for better jumping
        player.velocityX *= 0.85;
    }

    // Enhanced jumping with better air control
    if (jumpPressed && player.onGround && !player.jumpPressed) {
        player.velocityY = JUMP_FORCE;
        player.onGround = false;
        player.jumpPressed = true;
        player.airTime = 0;
        audioManager.jump();
        gameState.mobileControls.jumpPressed = false;
    }
    
    if (!jumpPressed) {
        player.jumpPressed = false;
    }

    // Air time tracking for better jump physics
    if (!player.onGround) {
        player.airTime += deltaTime;
    } else {
        player.airTime = 0;
    }

    // Web shooting
    if (shootPressed && gameState.webCooldownTimer <= 0) {
        gameState.webs.push({
            x: player.x + player.width / 2,
            y: player.y + player.height / 2,
            velocityX: WEB_SPEED,
            velocityY: 0,
            width: 10,
            height: 4
        });
        gameState.webCooldownTimer = WEB_COOLDOWN;
        audioManager.shoot();

        if (gameState.webs.length > MAX_WEBS) {
            gameState.webs.shift();
        }
    }

    if (gameState.webCooldownTimer > 0) {
        gameState.webCooldownTimer -= deltaTime;
    }

    // Apply gravity (reduced for better control)
    player.velocityY += GRAVITY;

    // Update position
    player.x += player.velocityX;
    player.y += player.velocityY;

    // Enhanced platform collision detection
    player.onGround = false;
    gameState.platforms.forEach(platform => {
        if (checkCollision(player, platform)) {
            // Top collision (landing) - more forgiving
            if (player.velocityY > 0 && player.y < platform.y + 5) {
                player.y = platform.y - player.height;
                player.velocityY = 0;
                player.onGround = true;
            }
            // Side collisions for better platform navigation
            else if (Math.abs(player.velocityX) > 0) {
                if (player.x < platform.x && player.velocityX > 0) {
                    // Hitting from left
                    player.x = platform.x - player.width;
                    player.velocityX = 0;
                } else if (player.x > platform.x && player.velocityX < 0) {
                    // Hitting from right
                    player.x = platform.x + platform.width;
                    player.velocityX = 0;
                }
            }
        }
    });

    // World bounds
    player.x = Math.max(0, Math.min(WORLD_WIDTH - player.width, player.x));
    if (player.y > WORLD_HEIGHT) {
        // Reset to start of level
        player.y = 100;
        player.x = 100;
        player.velocityY = 0;
        player.velocityX = 0;
    }
}

function updateWebs(deltaTime) {
    for (let i = gameState.webs.length - 1; i >= 0; i--) {
        const web = gameState.webs[i];
        web.x += web.velocityX;
        web.y += web.velocityY;

        if (web.x > WORLD_WIDTH || web.x < -web.width || web.y > WORLD_HEIGHT || web.y < -web.height) {
            gameState.webs.splice(i, 1);
            continue;
        }

        for (let j = gameState.targets.length - 1; j >= 0; j--) {
            const target = gameState.targets[j];
            if (checkCollision(web, target)) {
                gameState.targets.splice(j, 1);
                gameState.webs.splice(i, 1);
                gameState.targetsRemaining--;
                audioManager.hit();
                
                console.log(`Target hit! Remaining: ${gameState.targetsRemaining}`);
                
                for (let k = 0; k < 5; k++) {
                    gameState.particles.push({
                        x: target.x + target.width / 2,
                        y: target.y + target.height / 2,
                        velocityX: (Math.random() - 0.5) * 8,
                        velocityY: (Math.random() - 0.5) * 8,
                        life: 1,
                        decay: 0.02
                    });
                }

                if (gameState.particles.length > MAX_PARTICLES) {
                    gameState.particles.shift();
                }
                
                break;
            }
        }
    }

    gameState.targets.forEach(target => {
        target.pulse += deltaTime * 0.005;
    });
}

function updateParticles(deltaTime) {
    for (let i = gameState.particles.length - 1; i >= 0; i--) {
        const particle = gameState.particles[i];
        particle.x += particle.velocityX;
        particle.y += particle.velocityY;
        particle.life -= particle.decay;
        
        if (particle.life <= 0) {
            gameState.particles.splice(i, 1);
        }
    }
}

function updateCamera() {
    const player = gameState.player;
    const canvas = gameState.canvas;
    
    if (!canvas) return;
    
    gameState.camera.x = player.x - canvas.width / 2;
    gameState.camera.y = player.y - canvas.height / 2 + 100;
    
    gameState.camera.x = Math.max(0, Math.min(WORLD_WIDTH - canvas.width, gameState.camera.x));
    gameState.camera.y = Math.max(0, Math.min(WORLD_HEIGHT - canvas.height, gameState.camera.y));
}

function checkWinCondition() {
    if (gameState.targetsRemaining <= 0 && !gameState.levelComplete) {
        gameState.levelComplete = true;
        audioManager.victory();
        setTimeout(() => {
            showVictoryScreen();
        }, 500);
    }
}

function update(deltaTime) {
    if (!gameState.isPlaying || gameState.isPaused) return;

    updatePlayer(deltaTime);
    updateWebs(deltaTime);
    updateParticles(deltaTime);
    updateCamera();
    checkWinCondition();
    
    const targetsElement = document.getElementById('targetsRemaining');
    if (targetsElement) {
        targetsElement.textContent = `Targets: ${gameState.targetsRemaining}`;
    }
    
    const levelNameElement = document.getElementById('levelName');
    if (levelNameElement && LEVEL_LAYOUTS[gameState.currentLevel]) {
        levelNameElement.textContent = LEVEL_LAYOUTS[gameState.currentLevel].name;
    }
}

function getPlatformColor(platform) {
    switch (platform.type) {
        case 'ground':
            return '#8B4513'; // Brown
        case 'building':
            return '#696969'; // Gray
        case 'special':
            return '#4169E1'; // Blue
        default:
            return '#444444';
    }
}

function render() {
    const ctx = gameState.ctx;
    const camera = gameState.camera;
    
    if (!ctx || !gameState.canvas) return;
    
    ctx.clearRect(0, 0, gameState.canvas.width, gameState.canvas.height);
    
    ctx.save();
    ctx.translate(-camera.x, -camera.y);
    
    // Render platforms with enhanced visibility
    gameState.platforms.forEach(platform => {
        ctx.fillStyle = getPlatformColor(platform);
        ctx.fillRect(platform.x, platform.y, platform.width, platform.height);
        
        // Platform border for better visibility
        ctx.strokeStyle = '#ffffff';
        ctx.lineWidth = 2;
        ctx.strokeRect(platform.x, platform.y, platform.width, platform.height);
        
        // Add platform edge highlighting for jump indicators
        if (platform.type !== 'ground') {
            ctx.strokeStyle = '#ffff00';
            ctx.lineWidth = 1;
            ctx.strokeRect(platform.x - 1, platform.y - 1, platform.width + 2, platform.height + 2);
        }
    });
    
    // Render targets with enhanced pulse effect
    ctx.strokeStyle = '#00ff00';
    ctx.lineWidth = 3;
    gameState.targets.forEach(target => {
        const pulse = Math.sin(target.pulse) * 0.3 + 0.7;
        
        ctx.fillStyle = `rgba(0, 255, 0, ${pulse * 0.8})`;
        ctx.fillRect(target.x, target.y, target.width, target.height);
        ctx.strokeRect(target.x, target.y, target.width, target.height);
        
        ctx.fillStyle = `rgba(255, 255, 255, ${pulse * 0.5})`;
        ctx.fillRect(target.x + 5, target.y + 5, target.width - 10, target.height - 10);
    });
    
    // Render webs
    ctx.fillStyle = '#ffffff';
    ctx.strokeStyle = '#cccccc';
    ctx.lineWidth = 1;
    gameState.webs.forEach(web => {
        ctx.fillRect(web.x, web.y, web.width, web.height);
        ctx.strokeRect(web.x, web.y, web.width, web.height);
    });
    
    // Render particles
    gameState.particles.forEach(particle => {
        ctx.fillStyle = `rgba(0, 255, 0, ${particle.life})`;
        ctx.fillRect(particle.x - 1, particle.y - 1, 3, 3);
    });
    
    // Render player (Spider-Man) with enhanced visibility
    const player = gameState.player;
    
    // Shadow for depth
    ctx.fillStyle = 'rgba(0, 0, 0, 0.3)';
    ctx.fillRect(player.x + 2, player.y + 2, player.width, player.height);
    
    // Red upper body
    ctx.fillStyle = '#ff0000';
    ctx.fillRect(player.x, player.y, player.width, player.height * 0.6);
    
    // Blue lower body
    ctx.fillStyle = '#0000ff';
    ctx.fillRect(player.x, player.y + player.height * 0.6, player.width, player.height * 0.4);
    
    // Player outline
    ctx.strokeStyle = '#ffffff';
    ctx.lineWidth = 2;
    ctx.strokeRect(player.x, player.y, player.width, player.height);
    
    // Eyes
    ctx.fillStyle = '#ffffff';
    ctx.fillRect(player.x + 6, player.y + 8, 6, 6);
    ctx.fillRect(player.x + 18, player.y + 8, 6, 6);
    
    ctx.restore();
}

function gameLoop(currentTime) {
    const deltaTime = currentTime - gameState.lastTime;
    gameState.lastTime = currentTime;

    update(deltaTime);
    render();

    requestAnimationFrame(gameLoop);
}

// Menu Functions
function showMainMenu() {
    console.log('Showing main menu');
    const elements = {
        mainMenu: document.getElementById('mainMenu'),
        gameHUD: document.getElementById('gameHUD'),
        mobileControls: document.getElementById('mobileControls'),
        victoryOverlay: document.getElementById('victoryOverlay'),
        levelMenu: document.getElementById('levelMenu')
    };
    
    Object.values(elements).forEach(el => {
        if (el) {
            if (el.id === 'mainMenu') {
                el.classList.remove('hidden');
            } else {
                el.classList.add('hidden');
            }
        }
    });
    
    gameState.isPlaying = false;
    audioManager.stopBackgroundMusic();
}

function showLevelMenu() {
    console.log('Showing level menu');
    const mainMenu = document.getElementById('mainMenu');
    const levelMenu = document.getElementById('levelMenu');
    
    if (mainMenu) mainMenu.classList.add('hidden');
    if (levelMenu) levelMenu.classList.remove('hidden');
    
    audioManager.click();
}

function startLevel(levelNumber) {
    console.log(`Starting level ${levelNumber}`);
    
    if (!LEVEL_LAYOUTS[levelNumber]) {
        console.error(`Level ${levelNumber} layout not found`);
        return;
    }
    
    gameState.currentLevel = levelNumber;
    gameState.isPlaying = true;
    gameState.levelComplete = false;
    
    // Reset player to better starting position
    gameState.player.x = 50;
    gameState.player.y = 800;
    gameState.player.velocityX = 0;
    gameState.player.velocityY = 0;
    gameState.player.onGround = false;
    gameState.player.jumpPressed = false;
    gameState.player.airTime = 0;
    
    // Reset arrays
    gameState.webs = [];
    gameState.particles = [];
    gameState.webCooldownTimer = 0;
    
    // Create level content from predefined layouts
    gameState.platforms = createPlatforms(levelNumber);
    gameState.targets = createTargets(levelNumber);
    gameState.targetsRemaining = gameState.targets.length;
    
    console.log(`Level ${levelNumber} "${LEVEL_LAYOUTS[levelNumber].name}" created with ${gameState.platforms.length} platforms and ${gameState.targets.length} targets`);
    
    // Hide menus, show game UI
    const elements = {
        mainMenu: document.getElementById('mainMenu'),
        levelMenu: document.getElementById('levelMenu'),
        victoryOverlay: document.getElementById('victoryOverlay'),
        gameHUD: document.getElementById('gameHUD'),
        mobileControls: document.getElementById('mobileControls')
    };
    
    if (elements.mainMenu) elements.mainMenu.classList.add('hidden');
    if (elements.levelMenu) elements.levelMenu.classList.add('hidden');
    if (elements.victoryOverlay) elements.victoryOverlay.classList.add('hidden');
    if (elements.gameHUD) elements.gameHUD.classList.remove('hidden');
    if (elements.mobileControls) elements.mobileControls.classList.remove('hidden');
    
    if (gameState.audioEnabled) {
        audioManager.startBackgroundMusic();
    }
    
    audioManager.click();
}

function showVictoryScreen() {
    console.log('Showing victory screen');
    const victoryOverlay = document.getElementById('victoryOverlay');
    if (victoryOverlay) {
        victoryOverlay.classList.remove('hidden');
    }
    
    const nextButton = document.getElementById('nextLevelButton');
    const playAgainButton = document.getElementById('playAgainButton');
    
    if (nextButton && playAgainButton) {
        if (gameState.currentLevel < 5) {
            nextButton.style.display = 'inline-block';
            playAgainButton.textContent = 'Play Again';
        } else {
            nextButton.style.display = 'none';
            playAgainButton.textContent = 'Play Again';
        }
    }
}

// Fixed menu event setup
function setupMenuEvents() {
    console.log('Setting up menu events...');
    
    // Wait for DOM to be fully loaded
    document.addEventListener('DOMContentLoaded', () => {
        console.log('DOM ready, setting up button events');
        
        // Main menu buttons
        const playButton = document.getElementById('playButton');
        const levelsButton = document.getElementById('levelsButton');
        const audioButton = document.getElementById('audioButton');
        
        if (playButton) {
            console.log('Setting up play button');
            playButton.addEventListener('click', (e) => {
                console.log('Play button clicked!');
                e.preventDefault();
                startLevel(1);
            });
        } else {
            console.warn('Play button not found');
        }
        
        if (levelsButton) {
            console.log('Setting up levels button');
            levelsButton.addEventListener('click', (e) => {
                console.log('Levels button clicked!');
                e.preventDefault();
                showLevelMenu();
            });
        } else {
            console.warn('Levels button not found');
        }
        
        if (audioButton) {
            console.log('Setting up audio button');
            audioButton.addEventListener('click', (e) => {
                console.log('Audio button clicked!');
                e.preventDefault();
                const enabled = audioManager.toggle();
                gameState.audioEnabled = enabled;
                audioButton.textContent = enabled ? 'ðŸ”Š MUSIC' : 'ðŸ”‡ MUSIC';
                const audioToggle = document.getElementById('audioToggle');
                if (audioToggle) {
                    audioToggle.textContent = enabled ? 'ðŸ”Š' : 'ðŸ”‡';
                }
                audioManager.click();
            });
        } else {
            console.warn('Audio button not found');
        }
        
        // Level menu events
        const backToMenuButton = document.getElementById('backToMenuButton');
        if (backToMenuButton) {
            backToMenuButton.addEventListener('click', (e) => {
                console.log('Back to menu clicked');
                e.preventDefault();
                showMainMenu();
                audioManager.click();
            });
        }
        
        const levelButtons = document.querySelectorAll('.level-btn');
        console.log(`Found ${levelButtons.length} level buttons`);
        levelButtons.forEach(btn => {
            btn.addEventListener('click', (e) => {
                e.preventDefault();
                const level = parseInt(e.target.dataset.level);
                console.log(`Level ${level} selected`);
                startLevel(level);
            });
        });
        
        // HUD buttons
        const menuButton = document.getElementById('menuButton');
        const audioToggle = document.getElementById('audioToggle');
        
        if (menuButton) {
            menuButton.addEventListener('click', (e) => {
                e.preventDefault();
                showMainMenu();
                audioManager.click();
            });
        }
        
        if (audioToggle) {
            audioToggle.addEventListener('click', (e) => {
                e.preventDefault();
                const enabled = audioManager.toggle();
                gameState.audioEnabled = enabled;
                if (audioButton) {
                    audioButton.textContent = enabled ? 'ðŸ”Š MUSIC' : 'ðŸ”‡ MUSIC';
                }
                audioToggle.textContent = enabled ? 'ðŸ”Š' : 'ðŸ”‡';
                audioManager.click();
            });
        }
        
        // Victory menu events
        const nextLevelButton = document.getElementById('nextLevelButton');
        const playAgainButton = document.getElementById('playAgainButton');
        const backToMenuFromVictory = document.getElementById('backToMenuFromVictory');
        
        if (nextLevelButton) {
            nextLevelButton.addEventListener('click', (e) => {
                e.preventDefault();
                if (gameState.currentLevel < 5) {
                    startLevel(gameState.currentLevel + 1);
                }
            });
        }
        
        if (playAgainButton) {
            playAgainButton.addEventListener('click', (e) => {
                e.preventDefault();
                startLevel(gameState.currentLevel);
            });
        }
        
        if (backToMenuFromVictory) {
            backToMenuFromVictory.addEventListener('click', (e) => {
                e.preventDefault();
                showMainMenu();
                audioManager.click();
            });
        }
        
        console.log('All menu events setup complete');
    });
}

// Initialization
function init() {
    console.log('Initializing game...');
    
    gameState.canvas = document.getElementById('gameCanvas');
    if (gameState.canvas) {
        gameState.ctx = gameState.canvas.getContext('2d');
        console.log('Canvas initialized');
    } else {
        console.error('Canvas not found');
        return;
    }
    
    resizeCanvas();
    window.addEventListener('resize', resizeCanvas);
    window.addEventListener('orientationchange', () => {
        setTimeout(resizeCanvas, 100);
    });
    
    audioManager.init();
    setupKeyboardInput();
    setupTouchInput();
    createParticles();
    
    requestAnimationFrame(gameLoop);
    showMainMenu();
    
    console.log('Game initialized successfully');
}

// Setup menu events immediately
setupMenuEvents();

// Also initialize when DOM loads
document.addEventListener('DOMContentLoaded', () => {
    console.log('DOM loaded, initializing...');
    init();
});
</script>
</body>
</html>
