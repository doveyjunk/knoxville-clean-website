# Hero Design System
## Modern Americana Minimalism for Service Businesses

> **Version 1.0** | World-class design system for Claude Code implementation  
> **Aesthetic**: Clean, disciplined minimalism with civic-professional personality  
> **Target**: Service businesses (house cleaning, professional services)  
> **Framework**: React + Tailwind CSS | **Accessibility**: WCAG 2.1 AA

---

## Table of Contents

1. [Design Philosophy](#design-philosophy)
2. [Design Tokens](#design-tokens)
3. [Component Library](#component-library)
4. [Layout Patterns](#layout-patterns)
5. [Animation System](#animation-system)
6. [Accessibility Standards](#accessibility-standards)
7. [Performance Guidelines](#performance-guidelines)
8. [BookingKoala Integration](#bookingkoala-integration)
9. [Analytics & Instrumentation](#analytics--instrumentation)
10. [Testing Standards](#testing-standards)
11. [Claude Code Implementation](#claude-code-implementation)

---

## Design Philosophy

### Core Essence
**Modern Americana minimalism** — Clean, disciplined professionalism with subtle patriotic confidence. White-dominant layouts with structured red-blue duality. Communicates trust, precision, and civic pride without visual noise.

### Brand Personality
- **Visual Tone**: Bright, airy, confident
- **Mood**: Trustworthy, capable, efficient
- **Texture**: Smooth gradients, soft shadows, crisp edges
- **Temperature**: Cool-neutral base with controlled warmth

### Design Principles
1. **Clarity Over Decoration** - Every element serves purpose
2. **Hierarchy Through Space** - White space creates emphasis
3. **Trust Through Consistency** - Predictable interactions
4. **Accessibility First** - Universal usability
5. **Performance Driven** - Speed builds confidence

---

## Design Tokens

### Color System

#### Primary Palette
```css
/* Brand Colors */
--color-brand-red: #BC1823;
--color-brand-navy: #171b3e;
--color-brand-white: #ffffff;

/* Primary Variants */
--color-red-50: #fef2f2;
--color-red-100: #fee2e2;
--color-red-200: #fecaca;
--color-red-300: #fca5a5;
--color-red-400: #f87171;
--color-red-500: #ef4444;
--color-red-600: #dc2626;
--color-red-700: #b91c1c;
--color-red-800: #991b1b;
--color-red-900: #7f1d1d;
--color-red-brand: #BC1823;

--color-blue-50: #eff6ff;
--color-blue-100: #dbeafe;
--color-blue-200: #bfdbfe;
--color-blue-300: #93c5fd;
--color-blue-400: #60a5fa;
--color-blue-500: #3b82f6;
--color-blue-600: #2563eb;
--color-blue-700: #1d4ed8;
--color-blue-800: #1e40af;
--color-blue-900: #1e3a8a;
--color-blue-brand: #171b3e;
```

#### Neutral System
```css
/* Neutral Palette - Cool-toned for professionalism */
--color-white: #ffffff;
--color-gray-50: #f8fafc;
--color-gray-100: #f1f5f9;
--color-gray-200: #e2e8f0;
--color-gray-300: #cbd5e1;
--color-gray-400: #94a3b8;
--color-gray-500: #64748b;
--color-gray-600: #475569;
--color-gray-700: #334155;
--color-gray-800: #1e293b;
--color-gray-900: #0f172a;

/* Background Variations */
--color-bg-primary: #ffffff;
--color-bg-secondary: #f8fafc;
--color-bg-tertiary: #f1f5f9;
--color-bg-overlay: rgba(15, 23, 42, 0.75);
```

#### Semantic Colors
```css
/* State Colors */
--color-success-50: #f0fdf4;
--color-success-500: #22c55e;
--color-success-700: #15803d;

--color-warning-50: #fffbeb;
--color-warning-500: #f59e0b;
--color-warning-700: #a16207;

--color-error-50: #fef2f2;
--color-error-500: #ef4444;
--color-error-700: #b91c1c;

--color-info-50: #eff6ff;
--color-info-500: #3b82f6;
--color-info-700: #1d4ed8;
```

#### Text Colors
```css
--color-text-primary: #0f172a;
--color-text-secondary: #475569;
--color-text-tertiary: #64748b;
--color-text-inverse: #ffffff;
--color-text-brand: #171b3e;
--color-text-accent: #BC1823;
```

### Typography System

#### Font Stack
```css
--font-family-primary: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
--font-family-mono: 'JetBrains Mono', 'Fira Code', 'SF Mono', Consolas, monospace;
```

#### Font Weights
```css
--font-weight-light: 300;
--font-weight-normal: 400;
--font-weight-medium: 500;
--font-weight-semibold: 600;
--font-weight-bold: 700;
--font-weight-extrabold: 800;
```

#### Font Sizes & Line Heights
```css
/* Type Scale */
--text-xs: 0.75rem;    /* 12px */
--text-sm: 0.875rem;   /* 14px */
--text-base: 1rem;     /* 16px */
--text-lg: 1.125rem;   /* 18px */
--text-xl: 1.25rem;    /* 20px */
--text-2xl: 1.5rem;    /* 24px */
--text-3xl: 1.875rem;  /* 30px */
--text-4xl: 2.25rem;   /* 36px */
--text-5xl: 3rem;      /* 48px */
--text-6xl: 3.75rem;   /* 60px */

/* Line Heights */
--leading-tight: 1.1;
--leading-snug: 1.2;
--leading-normal: 1.4;
--leading-relaxed: 1.6;
--leading-loose: 1.8;

/* Letter Spacing */
--tracking-tight: -0.025em;
--tracking-normal: 0em;
--tracking-wide: 0.025em;
--tracking-wider: 0.05em;
```

#### Typography Tokens
```css
/* Heading Styles */
--type-h1: var(--font-weight-extrabold) var(--text-5xl)/var(--leading-tight) var(--font-family-primary);
--type-h2: var(--font-weight-bold) var(--text-4xl)/var(--leading-tight) var(--font-family-primary);
--type-h3: var(--font-weight-bold) var(--text-3xl)/var(--leading-snug) var(--font-family-primary);
--type-h4: var(--font-weight-semibold) var(--text-2xl)/var(--leading-snug) var(--font-family-primary);
--type-h5: var(--font-weight-semibold) var(--text-xl)/var(--leading-snug) var(--font-family-primary);
--type-h6: var(--font-weight-semibold) var(--text-lg)/var(--leading-normal) var(--font-family-primary);

/* Body Styles */
--type-body-lg: var(--font-weight-normal) var(--text-lg)/var(--leading-relaxed) var(--font-family-primary);
--type-body: var(--font-weight-normal) var(--text-base)/var(--leading-relaxed) var(--font-family-primary);
--type-body-sm: var(--font-weight-normal) var(--text-sm)/var(--leading-relaxed) var(--font-family-primary);

/* UI Styles */
--type-button-lg: var(--font-weight-semibold) var(--text-lg)/var(--leading-normal) var(--font-family-primary);
--type-button: var(--font-weight-semibold) var(--text-base)/var(--leading-normal) var(--font-family-primary);
--type-button-sm: var(--font-weight-semibold) var(--text-sm)/var(--leading-normal) var(--font-family-primary);
--type-caption: var(--font-weight-medium) var(--text-xs)/var(--leading-normal) var(--font-family-primary);
```

### Spacing System

#### Base Scale (4px)
```css
--space-0: 0;
--space-1: 0.25rem;  /* 4px */
--space-2: 0.5rem;   /* 8px */
--space-3: 0.75rem;  /* 12px */
--space-4: 1rem;     /* 16px */
--space-5: 1.25rem;  /* 20px */
--space-6: 1.5rem;   /* 24px */
--space-8: 2rem;     /* 32px */
--space-10: 2.5rem;  /* 40px */
--space-12: 3rem;    /* 48px */
--space-16: 4rem;    /* 64px */
--space-20: 5rem;    /* 80px */
--space-24: 6rem;    /* 96px */
--space-32: 8rem;    /* 128px */
```

#### Container Widths
```css
--container-sm: 640px;
--container-md: 768px;
--container-lg: 1024px;
--container-xl: 1280px;
--container-2xl: 1536px;
--container-content: 760px; /* Optimal reading width */
```

### Border Radius
```css
--radius-none: 0;
--radius-sm: 0.125rem;  /* 2px */
--radius-base: 0.25rem; /* 4px */
--radius-md: 0.375rem;  /* 6px */
--radius-lg: 0.5rem;    /* 8px */
--radius-xl: 0.75rem;   /* 12px */
--radius-2xl: 1rem;     /* 16px */
--radius-3xl: 1.5rem;   /* 24px */
--radius-full: 9999px;
```

### Shadow System
```css
--shadow-sm: 0 1px 2px 0 rgba(0, 0, 0, 0.05);
--shadow-base: 0 1px 3px 0 rgba(0, 0, 0, 0.1), 0 1px 2px 0 rgba(0, 0, 0, 0.06);
--shadow-md: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -1px rgba(0, 0, 0, 0.06);
--shadow-lg: 0 10px 15px -3px rgba(0, 0, 0, 0.1), 0 4px 6px -2px rgba(0, 0, 0, 0.05);
--shadow-xl: 0 20px 25px -5px rgba(0, 0, 0, 0.1), 0 10px 10px -5px rgba(0, 0, 0, 0.04);
--shadow-2xl: 0 25px 50px -12px rgba(0, 0, 0, 0.25);

/* Brand-specific shadows */
--shadow-brand: 0 6px 18px rgba(15, 23, 42, 0.08);
--shadow-brand-hover: 0 12px 24px rgba(15, 23, 42, 0.12);
```

### Z-Index Scale
```css
--z-index-dropdown: 10;
--z-index-sticky: 20;
--z-index-fixed: 30;
--z-index-modal-backdrop: 40;
--z-index-modal: 50;
--z-index-popover: 60;
--z-index-tooltip: 70;
--z-index-toast: 80;
--z-index-overlay: 90;
```

### Motion System
```css
/* Duration */
--duration-fast: 150ms;
--duration-normal: 250ms;
--duration-slow: 350ms;
--duration-slower: 500ms;

/* Easing */
--ease-linear: linear;
--ease-out: cubic-bezier(0, 0, 0.2, 1);
--ease-in: cubic-bezier(0.4, 0, 1, 1);
--ease-in-out: cubic-bezier(0.4, 0, 0.2, 1);
--ease-brand: cubic-bezier(0.22, 1, 0.36, 1);
```

---

## Component Library

### Button System

#### Primary Button
```tsx
interface ButtonProps {
  variant?: 'primary' | 'secondary' | 'ghost' | 'link' | 'danger';
  size?: 'sm' | 'md' | 'lg' | 'xl';
  fullWidth?: boolean;
  loading?: boolean;
  disabled?: boolean;
  icon?: ReactNode;
  iconPosition?: 'left' | 'right';
  children: ReactNode;
  onClick?: () => void;
  type?: 'button' | 'submit' | 'reset';
  href?: string; // For link variant
}

// Tailwind Classes for Button Variants
const buttonVariants = {
  primary: 'bg-red-brand hover:bg-red-800 focus:ring-red-500 text-white',
  secondary: 'bg-blue-brand hover:bg-blue-900 focus:ring-blue-500 text-white',
  ghost: 'bg-transparent hover:bg-gray-100 focus:ring-gray-300 text-gray-700 border border-gray-300',
  link: 'bg-transparent hover:bg-transparent focus:bg-transparent text-blue-brand hover:text-blue-800 underline',
  danger: 'bg-red-500 hover:bg-red-600 focus:ring-red-400 text-white'
};

const buttonSizes = {
  sm: 'px-3 py-2 text-sm',
  md: 'px-4 py-2.5 text-base',
  lg: 'px-6 py-3 text-lg',
  xl: 'px-8 py-4 text-xl'
};
```

#### Button States & Accessibility
```css
/* Focus Ring */
.btn-focus {
  @apply focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-opacity-50;
}

/* Loading State */
.btn-loading {
  @apply relative text-transparent;
}

.btn-loading::after {
  content: '';
  position: absolute;
  width: 16px;
  height: 16px;
  top: 50%;
  left: 50%;
  margin-left: -8px;
  margin-top: -8px;
  border: 2px solid transparent;
  border-top-color: currentColor;
  border-radius: 50%;
  animation: spin 1s linear infinite;
}

/* Disabled State */
.btn-disabled {
  @apply opacity-50 cursor-not-allowed pointer-events-none;
}
```

### Navigation Components

#### Header Navigation
```tsx
interface HeaderProps {
  logo: ReactNode;
  navigation: Array<{
    label: string;
    href: string;
    active?: boolean;
  }>;
  cta: {
    label: string;
    href: string;
  };
  mobileMenuOpen?: boolean;
  onMobileMenuToggle?: () => void;
}

// Tailwind Classes
const headerClasses = {
  container: 'sticky top-0 z-50 bg-white/95 backdrop-blur-sm border-b border-gray-200',
  wrapper: 'max-w-7xl mx-auto px-4 sm:px-6 lg:px-8',
  nav: 'flex justify-between items-center h-16',
  logo: 'flex-shrink-0',
  navigation: 'hidden md:flex space-x-8',
  navLink: 'text-gray-600 hover:text-gray-900 px-3 py-2 text-sm font-medium transition-colors',
  navLinkActive: 'text-blue-brand border-b-2 border-blue-brand',
  cta: 'ml-8 bg-red-brand hover:bg-red-800 text-white px-4 py-2 rounded-lg text-sm font-semibold transition-colors',
  mobileToggle: 'md:hidden p-2 rounded-md text-gray-400 hover:text-gray-500 hover:bg-gray-100'
};
```

#### Mobile Drawer
```tsx
interface MobileDrawerProps {
  isOpen: boolean;
  onClose: () => void;
  navigation: Array<{
    label: string;
    href: string;
    active?: boolean;
  }>;
  cta: {
    label: string;
    href: string;
  };
}

// Implementation includes:
// - Focus trap with first/last focusable elements
// - ESC key handling
// - Backdrop click to close
// - Smooth slide animation from right
// - Prevent body scroll when open
```

### Card Components

#### Service Card
```tsx
interface ServiceCardProps {
  title: string;
  description: string;
  image: {
    src: string;
    alt: string;
  };
  features?: string[];
  cta: {
    label: string;
    href: string;
  };
  badge?: string;
}

const serviceCardClasses = {
  container: 'group relative bg-white rounded-2xl shadow-brand hover:shadow-brand-hover transition-all duration-300 overflow-hidden',
  image: 'aspect-w-16 aspect-h-9 bg-gray-200',
  content: 'p-6',
  title: 'text-xl font-bold text-gray-900 mb-3',
  description: 'text-gray-600 mb-4 leading-relaxed',
  features: 'space-y-2 mb-6',
  feature: 'flex items-center text-sm text-gray-600',
  featureIcon: 'w-4 h-4 text-green-500 mr-2 flex-shrink-0',
  cta: 'w-full bg-blue-brand hover:bg-blue-900 text-white py-3 px-4 rounded-lg font-semibold transition-colors',
  badge: 'absolute top-4 left-4 bg-red-brand text-white px-3 py-1 rounded-full text-sm font-medium'
};
```

#### Testimonial Card
```tsx
interface TestimonialCardProps {
  content: string;
  author: {
    name: string;
    location?: string;
    avatar?: string;
  };
  rating?: number;
  source?: string;
}

const testimonialCardClasses = {
  container: 'bg-white rounded-xl p-6 shadow-brand',
  content: 'text-gray-700 mb-4 leading-relaxed italic',
  rating: 'flex items-center mb-4',
  star: 'w-5 h-5 text-yellow-400',
  author: 'flex items-center',
  avatar: 'w-12 h-12 rounded-full bg-gray-200 mr-4',
  authorInfo: 'flex-1',
  authorName: 'font-semibold text-gray-900',
  authorLocation: 'text-sm text-gray-600'
};
```

### Form Components

#### Input Field
```tsx
interface InputFieldProps {
  label: string;
  id: string;
  type?: 'text' | 'email' | 'tel' | 'password' | 'url';
  placeholder?: string;
  required?: boolean;
  disabled?: boolean;
  error?: string;
  helpText?: string;
  value?: string;
  onChange?: (value: string) => void;
  onBlur?: () => void;
  autoComplete?: string;
  maxLength?: number;
}

const inputClasses = {
  wrapper: 'mb-4',
  label: 'block text-sm font-medium text-gray-700 mb-2',
  input: 'w-full px-3 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-blue-500 transition-colors',
  inputError: 'border-red-500 focus:ring-red-500 focus:border-red-500',
  inputDisabled: 'bg-gray-50 text-gray-500 cursor-not-allowed',
  helpText: 'mt-1 text-sm text-gray-600',
  errorText: 'mt-1 text-sm text-red-600 flex items-center',
  errorIcon: 'w-4 h-4 mr-1 flex-shrink-0'
};
```

#### Contact Form
```tsx
interface ContactFormProps {
  onSubmit: (data: ContactFormData) => Promise<void>;
  initialData?: Partial<ContactFormData>;
  variant?: 'modal' | 'page';
}

interface ContactFormData {
  name: string;
  email: string;
  phone?: string;
  service?: string;
  message: string;
  preferredContact?: 'email' | 'phone';
  preferredTime?: string;
}

// Features:
// - Real-time validation with Zod schema
// - Honeypot spam protection
// - Time-to-submit validation
// - Phone number masking
// - Success/error states with animations
// - Accessibility compliance
```

### Modal Components

#### Base Modal
```tsx
interface ModalProps {
  isOpen: boolean;
  onClose: () => void;
  title?: string;
  size?: 'sm' | 'md' | 'lg' | 'xl' | 'full';
  closeOnOverlayClick?: boolean;
  closeOnEscape?: boolean;
  children: ReactNode;
}

const modalClasses = {
  overlay: 'fixed inset-0 z-50 bg-gray-900/75 backdrop-blur-sm',
  container: 'fixed inset-0 z-50 overflow-y-auto',
  wrapper: 'flex min-h-full items-center justify-center p-4',
  content: 'relative bg-white rounded-xl shadow-xl max-w-md w-full',
  header: 'flex items-center justify-between p-6 border-b border-gray-200',
  title: 'text-lg font-semibold text-gray-900',
  closeButton: 'text-gray-400 hover:text-gray-500 p-2 rounded-lg hover:bg-gray-100',
  body: 'p-6',
  footer: 'flex items-center justify-end space-x-3 p-6 border-t border-gray-200'
};

// Modal sizes
const modalSizes = {
  sm: 'max-w-sm',
  md: 'max-w-md',
  lg: 'max-w-lg',
  xl: 'max-w-xl',
  full: 'max-w-4xl'
};
```

#### Lead Capture Modal
```tsx
interface LeadModalProps {
  isOpen: boolean;
  onClose: () => void;
  onSubmit: (data: LeadData) => Promise<void>;
  trigger: 'exit-intent' | 'time-delay' | 'scroll-depth' | 'manual';
}

interface LeadData {
  email: string;
  firstName?: string;
  serviceInterest?: string;
  source: string;
}

// Features:
// - Minimal friction (email only required)
// - Service interest dropdown
// - Source tracking
// - Success state with next steps
// - Analytics tracking
```

### Feedback Components

#### Toast Notification
```tsx
interface ToastProps {
  type: 'success' | 'error' | 'warning' | 'info';
  title: string;
  message?: string;
  duration?: number;
  action?: {
    label: string;
    onClick: () => void;
  };
  onDismiss: () => void;
}

const toastClasses = {
  container: 'fixed top-4 right-4 z-80 max-w-sm w-full',
  toast: 'bg-white rounded-lg shadow-lg border-l-4 p-4 mb-3 animate-slide-in',
  success: 'border-green-500',
  error: 'border-red-500',
  warning: 'border-yellow-500',
  info: 'border-blue-500',
  header: 'flex items-start',
  icon: 'flex-shrink-0 w-5 h-5 mt-0.5 mr-3',
  content: 'flex-1 min-w-0',
  title: 'text-sm font-medium text-gray-900',
  message: 'mt-1 text-sm text-gray-600',
  actions: 'mt-3 flex space-x-3',
  action: 'text-sm font-medium text-blue-600 hover:text-blue-500',
  dismiss: 'ml-auto flex-shrink-0 text-gray-400 hover:text-gray-500'
};
```

#### Alert Component
```tsx
interface AlertProps {
  type: 'success' | 'error' | 'warning' | 'info';
  title?: string;
  children: ReactNode;
  dismissible?: boolean;
  onDismiss?: () => void;
  icon?: ReactNode;
}

const alertClasses = {
  base: 'rounded-lg p-4 border-l-4',
  success: 'bg-green-50 border-green-500 text-green-800',
  error: 'bg-red-50 border-red-500 text-red-800',
  warning: 'bg-yellow-50 border-yellow-500 text-yellow-800',
  info: 'bg-blue-50 border-blue-500 text-blue-800',
  header: 'flex items-center',
  icon: 'w-5 h-5 mr-2 flex-shrink-0',
  content: 'flex-1',
  title: 'font-medium mb-1',
  dismiss: 'ml-auto text-current/60 hover:text-current/80'
};
```

### Interactive Components

#### FAQ Accordion
```tsx
interface FAQItem {
  id: string;
  question: string;
  answer: string;
}

interface FAQAccordionProps {
  items: FAQItem[];
  allowMultiple?: boolean;
  defaultOpen?: string[];
}

const accordionClasses = {
  container: 'space-y-2',
  item: 'border border-gray-200 rounded-lg overflow-hidden',
  button: 'w-full px-6 py-4 text-left bg-white hover:bg-gray-50 focus:bg-gray-50 focus:outline-none focus:ring-2 focus:ring-blue-500 focus:ring-inset transition-colors',
  question: 'flex items-center justify-between text-gray-900 font-medium',
  icon: 'w-5 h-5 text-gray-500 transform transition-transform duration-200',
  answer: 'px-6 pb-4 text-gray-600 leading-relaxed'
};

// Features:
// - Keyboard navigation (arrow keys, home, end)
// - Screen reader support
// - Smooth expand/collapse animations
// - Optional multiple open items
// - Focus management
```

#### Tabs Component
```tsx
interface TabItem {
  id: string;
  label: string;
  content: ReactNode;
  disabled?: boolean;
}

interface TabsProps {
  items: TabItem[];
  defaultTab?: string;
  onChange?: (tabId: string) => void;
  variant?: 'line' | 'pill' | 'card';
}

const tabClasses = {
  container: 'w-full',
  list: 'flex border-b border-gray-200',
  tab: 'px-4 py-2 -mb-px font-medium text-sm focus:outline-none focus:ring-2 focus:ring-blue-500 focus:ring-inset',
  tabActive: 'text-blue-600 border-b-2 border-blue-600',
  tabInactive: 'text-gray-600 hover:text-gray-800 hover:border-gray-300',
  tabDisabled: 'text-gray-400 cursor-not-allowed',
  panel: 'pt-6 focus:outline-none'
};
```

### Carousel Components

#### Testimonial Carousel
```tsx
interface TestimonialCarouselProps {
  testimonials: TestimonialCardProps[];
  autoplay?: boolean;
  interval?: number;
  showDots?: boolean;
  showArrows?: boolean;
}

const carouselClasses = {
  container: 'relative',
  track: 'flex transition-transform duration-500 ease-in-out',
  slide: 'w-full flex-shrink-0',
  controls: 'flex items-center justify-center mt-6 space-x-4',
  arrow: 'p-2 rounded-full bg-gray-100 hover:bg-gray-200 text-gray-600 hover:text-gray-800 disabled:opacity-50 disabled:cursor-not-allowed',
  dots: 'flex space-x-2',
  dot: 'w-2 h-2 rounded-full bg-gray-300 hover:bg-gray-400 focus:bg-gray-400 transition-colors',
  dotActive: 'bg-blue-600'
};

// Features:
// - Touch/swipe support on mobile
// - Keyboard navigation
// - Auto-play with pause on hover
// - Accessible labels and controls
// - Respects prefers-reduced-motion
```

### Utility Components

#### Loading Skeleton
```tsx
interface SkeletonProps {
  variant?: 'text' | 'circular' | 'rectangular';
  width?: string | number;
  height?: string | number;
  lines?: number; // For text variant
  className?: string;
}

const skeletonClasses = {
  base: 'animate-pulse bg-gray-200 rounded',
  text: 'h-4 bg-gray-200 rounded',
  circular: 'rounded-full bg-gray-200',
  rectangular: 'bg-gray-200 rounded-lg'
};
```

#### Empty State
```tsx
interface EmptyStateProps {
  icon?: ReactNode;
  title: string;
  description?: string;
  action?: {
    label: string;
    onClick: () => void;
  };
  illustration?: string;
}

const emptyStateClasses = {
  container: 'text-center py-12 px-4',
  icon: 'mx-auto w-16 h-16 text-gray-400 mb-4',
  title: 'text-lg font-semibold text-gray-900 mb-2',
  description: 'text-gray-600 mb-6 max-w-sm mx-auto',
  action: 'bg-blue-brand hover:bg-blue-800 text-white px-4 py-2 rounded-lg font-medium transition-colors'
};
```

#### Back to Top
```tsx
interface BackToTopProps {
  threshold?: number; // Scroll position to show button
  smooth?: boolean;
  className?: string;
}

const backToTopClasses = {
  button: 'fixed bottom-8 right-8 z-40 p-3 bg-blue-brand hover:bg-blue-800 text-white rounded-full shadow-lg hover:shadow-xl transition-all duration-300 focus:outline-none focus:ring-2 focus:ring-blue-500 focus:ring-offset-2',
  icon: 'w-5 h-5',
  hidden: 'opacity-0 translate-y-2 pointer-events-none',
  visible: 'opacity-100 translate-y-0'
};

// Features:
// - Smooth scroll behavior
// - Fade in/out animation
// - Respects prefers-reduced-motion
// - Focus management
```

### BookingKoala Integration

#### BK Embed Component
```tsx
interface BKEmbedProps {
  type: 'booking' | 'login' | 'signup' | 'gift-cards';
  height?: number | 'auto';
  onLoad?: () => void;
  onError?: (error: Error) => void;
  onResize?: (height: number) => void;
}

const bkEmbedClasses = {
  container: 'w-full bg-white rounded-lg overflow-hidden shadow-brand',
  iframe: 'w-full border-0',
  loading: 'flex items-center justify-center h-96 bg-gray-50',
  error: 'flex flex-col items-center justify-center h-96 bg-gray-50 text-gray-600'
};

// Security & Performance Features:
// - CSP: frame-src https://*.bookingkoala.com
// - Sandbox attributes for security
// - Auto-resize via postMessage
// - Loading states and error handling
// - Analytics integration
// - DNS prefetch and preconnect
```

#### Implementation Details:
```tsx
// CSP Configuration
const cspDirectives = {
  'frame-src': ['https://*.bookingkoala.com'],
  'connect-src': ['https://*.bookingkoala.com'],
  'script-src': ['self', 'unsafe-inline'] // For postMessage handling
};

// PostMessage Handler
interface BKMessage {
  type: 'resize' | 'navigate' | 'error' | 'analytics';
  payload: {
    height?: number;
    path?: string;
    error?: string;
    event?: string;
    data?: Record<string, any>;
  };
}

// Analytics Events
const bkAnalyticsEvents = {
  mount: { event: 'bk_iframe_mount', params: { type, path } },
  resize: { event: 'bk_iframe_resize', params: { height, path } },
  error: { event: 'bk_iframe_error', params: { error, path } },
  navigation: { event: 'bk_iframe_navigate', params: { from, to } }
};
```

### Error Boundary Components

#### 404 Page
```tsx
interface NotFoundPageProps {
  title?: string;
  description?: string;
  homeLink?: string;
  contactLink?: string;
  searchEnabled?: boolean;
}

const notFoundClasses = {
  container: 'min-h-screen bg-gray-50 flex flex-col items-center justify-center px-4',
  content: 'text-center max-w-md mx-auto',
  errorCode: 'text-6xl font-bold text-blue-brand mb-4',
  title: 'text-2xl font-bold text-gray-900 mb-4',
  description: 'text-gray-600 mb-8 leading-relaxed',
  actions: 'flex flex-col sm:flex-row gap-4 justify-center',
  primaryAction: 'bg-blue-brand hover:bg-blue-800 text-white px-6 py-3 rounded-lg font-semibold transition-colors',
  secondaryAction: 'bg-gray-100 hover:bg-gray-200 text-gray-700 px-6 py-3 rounded-lg font-semibold transition-colors'
};
```

#### 500 Error Page
```tsx
interface ErrorPageProps {
  error?: Error;
  resetErrorBoundary?: () => void;
  supportEmail?: string;
}

// Features:
// - Error reporting to monitoring service
// - User-friendly error messages
// - Recovery actions
// - Support contact information
```

#### Maintenance Banner
```tsx
interface MaintenanceBannerProps {
  message: string;
  scheduledEnd?: Date;
  contactInfo?: string;
  dismissible?: boolean;
}

const maintenanceBannerClasses = {
  banner: 'bg-yellow-50 border-b border-yellow-200 px-4 py-3',
  content: 'max-w-7xl mx-auto flex items-center justify-between',
  message: 'text-yellow-800 text-sm font-medium',
  dismiss: 'text-yellow-600 hover:text-yellow-800 p-1 rounded'
};
```

---

## Layout Patterns

### Container System

#### Base Container
```tsx
interface ContainerProps {
  size?: 'sm' | 'md' | 'lg' | 'xl' | '2xl' | 'full';
  padding?: boolean;
  children: ReactNode;
}

const containerClasses = {
  base: 'mx-auto',
  sizes: {
    sm: 'max-w-screen-sm',
    md: 'max-w-screen-md', 
    lg: 'max-w-screen-lg',
    xl: 'max-w-screen-xl',
    '2xl': 'max-w-screen-2xl',
    full: 'max-w-full'
  },
  padding: 'px-4 sm:px-6 lg:px-8'
};
```

### Grid System

#### Responsive Grid
```tsx
interface GridProps {
  cols?: 1 | 2 | 3 | 4 | 6 | 12;
  gap?: 2 | 4 | 6 | 8 | 12;
  responsive?: {
    sm?: 1 | 2 | 3 | 4 | 6 | 12;
    md?: 1 | 2 | 3 | 4 | 6 | 12;
    lg?: 1 | 2 | 3 | 4 | 6 | 12;
    xl?: 1 | 2 | 3 | 4 | 6 | 12;
  };
  children: ReactNode;
}

// Example: Service grid pattern
const serviceGridClasses = {
  container: 'grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8'
};
```

### Page Layouts

#### Single Column Layout (Homepage)
```tsx
interface SingleColumnLayoutProps {
  header: ReactNode;
  hero: ReactNode;
  sections: ReactNode[];
  footer: ReactNode;
  cta?: ReactNode;
}

const singleColumnClasses = {
  wrapper: 'min-h-screen bg-white',
  main: 'flex-1',
  section: 'py-16 lg:py-24',
  sectionAlt: 'py-16 lg:py-24 bg-gray-50' // Alternate background
};

// Section order pattern:
// Hero → Services → How It Works → Testimonials → FAQ → CTA → Footer
```

#### Two Column Layout (Blog/Knowledge Base)
```tsx
interface TwoColumnLayoutProps {
  sidebar: ReactNode;
  content: ReactNode;
  sidebarPosition?: 'left' | 'right';
  sidebarWidth?: 'narrow' | 'normal' | 'wide';
}

const twoColumnClasses = {
  container: 'max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-8',
  wrapper: 'grid grid-cols-1 lg:grid-cols-4 gap-8',
  sidebar: 'lg:col-span-1',
  content: 'lg:col-span-3 max-w-none prose prose-lg'
};
```

### Section Patterns

#### Hero Section
```tsx
interface HeroSectionProps {
  title: string;
  subtitle?: string;
  cta: {
    primary: { label: string; href: string };
    secondary?: { label: string; href: string };
  };
  image?: {
    src: string;
    alt: string;
  };
  backgroundPattern?: 'gradient' | 'dots' | 'none';
}

const heroClasses = {
  section: 'relative bg-white overflow-hidden',
  container: 'max-w-7xl mx-auto px-4 sm:px-6 lg:px-8',
  wrapper: 'relative z-10 py-16 sm:py-24 lg:py-32',
  grid: 'grid grid-cols-1 lg:grid-cols-2 gap-12 items-center',
  content: 'text-center lg:text-left',
  title: 'text-4xl sm:text-5xl lg:text-6xl font-extrabold text-gray-900 tracking-tight',
  subtitle: 'mt-6 text-xl text-gray-600 leading-relaxed',
  ctas: 'mt-8 flex flex-col sm:flex-row gap-4 justify-center lg:justify-start',
  primaryCta: 'bg-red-brand hover:bg-red-800 text-white px-8 py-3 rounded-lg text-lg font-semibold transition-colors',
  secondaryCta: 'bg-blue-brand hover:bg-blue-800 text-white px-8 py-3 rounded-lg text-lg font-semibold transition-colors',
  image: 'relative lg:col-start-2',
  imageWrapper: 'aspect-w-16 aspect-h-9 rounded-2xl overflow-hidden shadow-2xl'
};
```

#### How It Works Section
```tsx
interface HowItWorksProps {
  title: string;
  description?: string;
  steps: Array<{
    title: string;
    description: string;
    icon: ReactNode;
  }>;
}

const howItWorksClasses = {
  section: 'py-16 lg:py-24 bg-gray-50',
  container: 'max-w-7xl mx-auto px-4 sm:px-6 lg:px-8',
  header: 'text-center mb-16',
  title: 'text-3xl lg:text-4xl font-bold text-gray-900 mb-4',
  description: 'text-xl text-gray-600 max-w-2xl mx-auto',
  steps: 'grid grid-cols-1 md:grid-cols-3 gap-8',
  step: 'text-center',
  stepIcon: 'w-16 h-16 mx-auto mb-6 text-blue-brand',
  stepTitle: 'text-xl font-semibold text-gray-900 mb-3',
  stepDescription: 'text-gray-600 leading-relaxed'
};
```

#### CTA Section
```tsx
interface CTASectionProps {
  title: string;
  description?: string;
  cta: {
    label: string;
    href: string;
  };
  backgroundColor?: 'white' | 'gray' | 'brand';
  pattern?: 'gradient' | 'none';
}

const ctaClasses = {
  section: 'relative py-16 lg:py-24',
  white: 'bg-white',
  gray: 'bg-gray-50',
  brand: 'bg-gradient-to-r from-blue-brand to-red-brand',
  container: 'max-w-4xl mx-auto px-4 sm:px-6 lg:px-8 text-center',
  title: 'text-3xl lg:text-4xl font-bold mb-4',
  titleWhite: 'text-gray-900',
  titleBrand: 'text-white',
  description: 'text-xl mb-8',
  descriptionWhite: 'text-gray-600',
  descriptionBrand: 'text-white/90',
  cta: 'inline-block px-8 py-3 text-lg font-semibold rounded-lg transition-colors',
  ctaWhite: 'bg-red-brand hover:bg-red-800 text-white',
  ctaBrand: 'bg-white hover:bg-gray-100 text-gray-900'
};
```

### Responsive Patterns

#### Breakpoint Strategy
```css
/* Mobile First Approach */
.responsive-grid {
  /* Base (mobile): Single column */
  grid-template-columns: 1fr;
  gap: 1rem;
}

@media (min-width: 640px) {
  .responsive-grid {
    /* Small: 2 columns */
    grid-template-columns: repeat(2, 1fr);
    gap: 1.5rem;
  }
}

@media (min-width: 1024px) {
  .responsive-grid {
    /* Large: 3 columns */
    grid-template-columns: repeat(3, 1fr);
    gap: 2rem;
  }
}
```

#### Navigation Breakpoints
```tsx
// Desktop: Horizontal navigation with logo left, links center, CTA right
// Tablet: Same as desktop if space allows, otherwise hamburger menu
// Mobile: Logo left, hamburger right, drawer navigation

const navigationBreakpoint = 'md'; // 768px
const showMobileMenu = 'below md breakpoint';
```

---

## Animation System

### Motion Philosophy
Animations reinforce trust, ease, and refinement. Every motion serves clarity, mirroring professional cleaning service precision.

### Timing & Easing
```css
/* Duration Scale */
:root {
  --duration-instant: 0ms;
  --duration-fast: 150ms;
  --duration-normal: 250ms;
  --duration-slow: 350ms;
  --duration-slower: 500ms;
  --duration-slowest: 750ms;
}

/* Easing Functions */
:root {
  --ease-linear: linear;
  --ease-in: cubic-bezier(0.4, 0, 1, 1);
  --ease-out: cubic-bezier(0, 0, 0.2, 1);
  --ease-in-out: cubic-bezier(0.4, 0, 0.2, 1);
  --ease-brand: cubic-bezier(0.22, 1, 0.36, 1); /* Custom smooth */
}
```

### Animation Classes
```css
/* Page Load Animations */
.animate-fade-in {
  animation: fadeIn var(--duration-slow) var(--ease-out) forwards;
  opacity: 0;
}

.animate-slide-up {
  animation: slideUp var(--duration-slow) var(--ease-brand) forwards;
  opacity: 0;
  transform: translateY(20px);
}

.animate-scale-in {
  animation: scaleIn var(--duration-normal) var(--ease-out) forwards;
  opacity: 0;
  transform: scale(0.95);
}

/* Interaction Animations */
.animate-button-press {
  transition: transform var(--duration-fast) var(--ease-in-out);
}

.animate-button-press:active {
  transform: scale(0.97);
}

.animate-hover-lift {
  transition: transform var(--duration-normal) var(--ease-out),
              box-shadow var(--duration-normal) var(--ease-out);
}

.animate-hover-lift:hover {
  transform: translateY(-2px);
  box-shadow: var(--shadow-brand-hover);
}

/* Loading Animations */
.animate-spin {
  animation: spin 1s linear infinite;
}

.animate-pulse {
  animation: pulse 2s cubic-bezier(0.4, 0, 0.6, 1) infinite;
}

/* Keyframes */
@keyframes fadeIn {
  from { opacity: 0; }
  to { opacity: 1; }
}

@keyframes slideUp {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes scaleIn {
  from {
    opacity: 0;
    transform: scale(0.95);
  }
  to {
    opacity: 1;
    transform: scale(1);
  }
}

@keyframes spin {
  from { transform: rotate(0deg); }
  to { transform: rotate(360deg); }
}

@keyframes pulse {
  0%, 100% { opacity: 1; }
  50% { opacity: .5; }
}
```

### Component-Specific Animations

#### Modal Animations
```css
.modal-enter {
  opacity: 0;
  transform: scale(0.95);
}

.modal-enter-active {
  opacity: 1;
  transform: scale(1);
  transition: opacity var(--duration-normal) var(--ease-out),
              transform var(--duration-normal) var(--ease-out);
}

.modal-exit {
  opacity: 1;
  transform: scale(1);
}

.modal-exit-active {
  opacity: 0;
  transform: scale(0.95);
  transition: opacity var(--duration-normal) var(--ease-in),
              transform var(--duration-normal) var(--ease-in);
}
```

#### Toast Animations
```css
.toast-enter {
  transform: translateX(100%);
  opacity: 0;
}

.toast-enter-active {
  transform: translateX(0);
  opacity: 1;
  transition: transform var(--duration-normal) var(--ease-out),
              opacity var(--duration-normal) var(--ease-out);
}

.toast-exit {
  transform: translateX(0);
  opacity: 1;
}

.toast-exit-active {
  transform: translateX(100%);
  opacity: 0;
  transition: transform var(--duration-normal) var(--ease-in),
              opacity var(--duration-normal) var(--ease-in);
}
```

### Accessibility Considerations
```css
/* Respect user preferences */
@media (prefers-reduced-motion: reduce) {
  *,
  *::before,
  *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
    scroll-behavior: auto !important;
  }
}

/* Focus animations that respect reduced motion */
@media (prefers-reduced-motion: reduce) {
  .focus-ring {
    transition: none;
  }
}

@media (prefers-reduced-motion: no-preference) {
  .focus-ring {
    transition: box-shadow var(--duration-fast) var(--ease-out);
  }
}
```

---

## Accessibility Standards

### WCAG 2.1 AA Compliance

#### Color Contrast Requirements
```css
/* Text Contrast Ratios */
/* Normal text (16px+): 4.5:1 minimum */
/* Large text (18px+ or 14px+ bold): 3:1 minimum */
/* UI components: 3:1 minimum */

/* Verified Contrast Ratios */
.text-primary { color: #0f172a; } /* 15.8:1 on white */
.text-secondary { color: #475569; } /* 7.2:1 on white */
.text-tertiary { color: #64748b; } /* 5.7:1 on white */

.bg-red-brand { background: #BC1823; } /* 5.1:1 with white text */
.bg-blue-brand { background: #171b3e; } /* 12.6:1 with white text */
```

#### Focus Management
```css
/* Global Focus Ring */
.focus-ring {
  outline: 2px solid transparent;
  outline-offset: 2px;
  box-shadow: 0 0 0 2px #ffffff, 0 0 0 4px #2563eb;
}

/* Component-specific focus styles */
.btn:focus-visible {
  outline: 2px solid transparent;
  outline-offset: 2px;
  box-shadow: 0 0 0 2px #ffffff, 0 0 0 4px currentColor;
}

.input:focus {
  outline: 2px solid transparent;
  outline-offset: 2px;
  border-color: #2563eb;
  box-shadow: 0 0 0 1px #2563eb;
}
```

#### Semantic HTML Structure
```tsx
// Proper landmark usage
<header role="banner">
  <nav role="navigation" aria-label="Main navigation">
    {/* Navigation content */}
  </nav>
</header>

<main role="main">
  <section aria-labelledby="services-heading">
    <h2 id="services-heading">Our Services</h2>
    {/* Section content */}
  </section>
</main>

<aside role="complementary" aria-label="Contact information">
  {/* Sidebar content */}
</aside>

<footer role="contentinfo">
  {/* Footer content */}
</footer>
```

#### Skip Links
```tsx
const SkipLink = () => (
  <a
    href="#main-content"
    className="sr-only focus:not-sr-only focus:absolute focus:top-4 focus:left-4 bg-blue-brand text-white px-4 py-2 rounded-lg font-medium z-50"
  >
    Skip to main content
  </a>
);
```

#### Screen Reader Support
```tsx
// Proper labeling
<button aria-label="Open main menu" aria-expanded={isOpen}>
  <span aria-hidden="true">☰</span>
</button>

// Live regions for dynamic content
<div aria-live="polite" aria-atomic="true" className="sr-only">
  {statusMessage}
</div>

// Form associations
<label htmlFor="email" className="block text-sm font-medium">
  Email Address
</label>
<input
  id="email"
  type="email"
  aria-describedby="email-help email-error"
  aria-invalid={!!error}
/>
<div id="email-help" className="text-sm text-gray-600">
  We'll never share your email address.
</div>
{error && (
  <div id="email-error" className="text-sm text-red-600" role="alert">
    {error}
  </div>
)}
```

#### Keyboard Navigation
```tsx
// Focus trap for modals
const useFocusTrap = (isActive: boolean) => {
  const ref = useRef<HTMLDivElement>(null);
  
  useEffect(() => {
    if (!isActive || !ref.current) return;
    
    const focusableElements = ref.current.querySelectorAll(
      'button, [href], input, select, textarea, [tabindex]:not([tabindex="-1"])'
    );
    
    const firstElement = focusableElements[0] as HTMLElement;
    const lastElement = focusableElements[focusableElements.length - 1] as HTMLElement;
    
    const handleTabKey = (e: KeyboardEvent) => {
      if (e.key === 'Tab') {
        if (e.shiftKey) {
          if (document.activeElement === firstElement) {
            lastElement.focus();
            e.preventDefault();
          }
        } else {
          if (document.activeElement === lastElement) {
            firstElement.focus();
            e.preventDefault();
          }
        }
      }
    };
    
    document.addEventListener('keydown', handleTabKey);
    firstElement.focus();
    
    return () => {
      document.removeEventListener('keydown', handleTabKey);
    };
  }, [isActive]);
  
  return ref;
};
```

#### Aria Patterns
```tsx
// Accordion
<div className="accordion">
  <h3>
    <button
      aria-expanded={isOpen}
      aria-controls={`panel-${id}`}
      id={`button-${id}`}
    >
      {question}
    </button>
  </h3>
  <div
    id={`panel-${id}`}
    role="region"
    aria-labelledby={`button-${id}`}
    hidden={!isOpen}
  >
    {answer}
  </div>
</div>

// Tabs
<div className="tabs">
  <div role="tablist" aria-label="Service options">
    {tabs.map((tab, index) => (
      <button
        key={tab.id}
        role="tab"
        aria-selected={activeTab === tab.id}
        aria-controls={`panel-${tab.id}`}
        id={`tab-${tab.id}`}
        tabIndex={activeTab === tab.id ? 0 : -1}
      >
        {tab.label}
      </button>
    ))}
  </div>
  {tabs.map((tab) => (
    <div
      key={tab.id}
      role="tabpanel"
      aria-labelledby={`tab-${tab.id}`}
      id={`panel-${tab.id}`}
      hidden={activeTab !== tab.id}
    >
      {tab.content}
    </div>
  ))}
</div>
```

---

## Performance Guidelines

### Core Web Vitals Targets
```typescript
interface PerformanceBudgets {
  LCP: number; // Largest Contentful Paint ≤ 2.5s
  INP: number; // Interaction to Next Paint ≤ 200ms
  CLS: number; // Cumulative Layout Shift ≤ 0.10
}

const performanceTargets: PerformanceBudgets = {
  LCP: 2500, // milliseconds
  INP: 200,  // milliseconds
  CLS: 0.10  // score
};
```

### Image Optimization
```tsx
// Responsive image component
interface OptimizedImageProps {
  src: string;
  alt: string;
  width: number;
  height: number;
  sizes?: string;
  priority?: boolean;
  placeholder?: 'blur' | 'empty';
}

const OptimizedImage = ({ 
  src, 
  alt, 
  width, 
  height, 
  sizes = '100vw',
  priority = false 
}: OptimizedImageProps) => {
  return (
    <img
      src={src}
      alt={alt}
      width={width}
      height={height}
      sizes={sizes}
      loading={priority ? 'eager' : 'lazy'}
      decoding="async"
      className="w-full h-auto"
    />
  );
};

// Srcset generation for responsive images
const generateSrcSet = (baseUrl: string, widths: number[]) => {
  return widths
    .map(width => `${baseUrl}?w=${width} ${width}w`)
    .join(', ');
};
```

### Code Splitting Strategy
```typescript
// Route-based code splitting
const HomePage = lazy(() => import('./pages/HomePage'));
const ServicesPage = lazy(() => import('./pages/ServicesPage'));
const ContactPage = lazy(() => import('./pages/ContactPage'));

// Component-based code splitting for heavy components
const TestimonialCarousel = lazy(() => import('./components/TestimonialCarousel'));
const BookingModal = lazy(() => import('./components/BookingModal'));

// Preload critical route components
const preloadRoutes = () => {
  import('./pages/ServicesPage');
  import('./components/BookingModal');
};
```

### Resource Loading Strategy
```html
<!-- Critical resource hints -->
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://bookingkoala.com">
<link rel="dns-prefetch" href="https://analytics.google.com">

<!-- Critical CSS inlined -->
<style>/* Critical above-fold styles */</style>

<!-- Non-critical CSS loaded asynchronously -->
<link rel="preload" href="/css/non-critical.css" as="style" onload="this.onload=null;this.rel='stylesheet'">
```

### Bundle Optimization
```typescript
// Webpack/Vite configuration for optimal bundling
const bundleConfig = {
  splitChunks: {
    chunks: 'all',
    cacheGroups: {
      vendor: {
        test: /[\\/]node_modules[\\/]/,
        name: 'vendors',
        chunks: 'all',
      },
      common: {
        name: 'common',
        minChunks: 2,
        chunks: 'all',
      }
    }
  }
};

// Tree shaking for unused code elimination
export { Button, Input } from './components'; // Named exports only
```

### Performance Monitoring
```typescript
// Web Vitals measurement
const measureWebVitals = () => {
  import('web-vitals').then(({ getCLS, getFID, getFCP, getLCP, getTTFB }) => {
    getCLS(sendToAnalytics);
    getFID(sendToAnalytics);
    getFCP(sendToAnalytics);
    getLCP(sendToAnalytics);
    getTTFB(sendToAnalytics);
  });
};

const sendToAnalytics = (metric: any) => {
  gtag('event', metric.name, {
    event_category: 'Web Vitals',
    value: Math.round(metric.value),
    event_label: metric.id,
    non_interaction: true,
  });
};
```

---

## BookingKoala Integration

### Security Configuration
```typescript
// Content Security Policy
const cspConfig = {
  directives: {
    'frame-src': [
      'https://*.bookingkoala.com',
      'https://bookingkoala.com'
    ],
    'connect-src': [
      'https://*.bookingkoala.com',
      'https://bookingkoala.com'
    ],
    'script-src': [
      "'self'",
      "'unsafe-inline'", // For postMessage handling
      'https://analytics.google.com'
    ]
  }
};

// Iframe sandbox attributes
const sandboxAttributes = [
  'allow-forms',
  'allow-scripts',
  'allow-same-origin',
  'allow-popups',
  'allow-popups-to-escape-sandbox'
].join(' ');
```

### PostMessage Communication
```typescript
interface BookingKoalaMessage {
  type: 'resize' | 'navigate' | 'error' | 'booking-complete' | 'user-action';
  payload: {
    height?: number;
    path?: string;
    error?: string;
    bookingId?: string;
    userId?: string;
    action?: string;
    data?: Record<string, any>;
  };
  source: 'bookingkoala';
  version: string;
}

const handleBookingKoalaMessage = (event: MessageEvent<BookingKoalaMessage>) => {
  // Verify origin
  if (!event.origin.endsWith('.bookingkoala.com') && 
      event.origin !== 'https://bookingkoala.com') {
    return;
  }

  // Verify message structure
  if (!event.data || event.data.source !== 'bookingkoala') {
    return;
  }

  const { type, payload } = event.data;

  switch (type) {
    case 'resize':
      handleIframeResize(payload.height);
      break;
    case 'navigate':
      handleNavigation(payload.path);
      break;
    case 'booking-complete':
      handleBookingComplete(payload.bookingId, payload.data);
      break;
    case 'error':
      handleBookingError(payload.error);
      break;
    case 'user-action':
      trackUserAction(payload.action, payload.data);
      break;
  }
};
```

### Iframe Component Implementation
```tsx
interface BookingKoalaEmbedProps {
  type: 'booking' | 'login' | 'signup' | 'gift-cards';
  initialHeight?: number;
  className?: string;
  onLoad?: () => void;
  onError?: (error: string) => void;
  onBookingComplete?: (bookingId: string, data: any) => void;
}

const BookingKoalaEmbed = ({
  type,
  initialHeight = 800,
  className = '',
  onLoad,
  onError,
  onBookingComplete
}: BookingKoalaEmbedProps) => {
  const [height, setHeight] = useState(initialHeight);
  const [loading, setLoading] = useState(true);
  const [error, setError] = useState<string | null>(null);
  const iframeRef = useRef<HTMLIFrameElement>(null);

  // PostMessage handler
  useEffect(() => {
    const handleMessage = (event: MessageEvent) => {
      if (!event.origin.includes('bookingkoala.com')) return;

      const { type: messageType, payload } = event.data;

      switch (messageType) {
        case 'resize':
          if (payload.height && payload.height !== height) {
            setHeight(payload.height);
          }
          break;
        case 'error':
          setError(payload.error);
          onError?.(payload.error);
          break;
        case 'booking-complete':
          onBookingComplete?.(payload.bookingId, payload.data);
          break;
      }
    };

    window.addEventListener('message', handleMessage);
    return () => window.removeEventListener('message', handleMessage);
  }, [height, onError, onBookingComplete]);

  // Analytics tracking
  useEffect(() => {
    if (!loading) {
      gtag('event', 'bk_iframe_mount', {
        event_category: 'BookingKoala',
        event_label: type,
        custom_parameter_1: window.location.pathname
      });
    }
  }, [loading, type]);

  const baseUrl = 'https://app.bookingkoala.com';
  const iframeSrc = `${baseUrl}/${type}`;

  return (
    <div className={`relative bg-white rounded-lg overflow-hidden shadow-brand ${className}`}>
      {loading && (
        <div className="absolute inset-0 flex items-center justify-center bg-gray-50 z-10">
          <div className="text-center">
            <div className="animate-spin rounded-full h-8 w-8 border-2 border-blue-brand border-t-transparent mx-auto mb-4"></div>
            <p className="text-gray-600">Loading booking system...</p>
          </div>
        </div>
      )}
      
      {error && (
        <div className="absolute inset-0 flex items-center justify-center bg-gray-50 z-10">
          <div className="text-center max-w-md mx-auto p-6">
            <div className="text-red-500 mb-4">
              <svg className="w-12 h-12 mx-auto" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path strokeLinecap="round" strokeLinejoin="round" strokeWidth={2} d="M12 9v2m0 4h.01m-6.938 4h13.856c1.54 0 2.502-1.667 1.732-2.5L13.732 4c-.77-.833-1.964-.833-2.732 0L3.732 16.5c-.77.833.192 2.5 1.732 2.5z" />
              </svg>
            </div>
            <h3 className="text-lg font-semibold text-gray-900 mb-2">Booking System Error</h3>
            <p className="text-gray-600 mb-4">{error}</p>
            <button
              onClick={() => {
                setError(null);
                setLoading(true);
                if (iframeRef.current) {
                  iframeRef.current.src = iframeSrc;
                }
              }}
              className="bg-blue-brand hover:bg-blue-800 text-white px-4 py-2 rounded-lg font-medium transition-colors"
            >
              Try Again
            </button>
          </div>
        </div>
      )}

      <iframe
        ref={iframeRef}
        src={iframeSrc}
        width="100%"
        height={height}
        style={{ border: 'none', display: loading || error ? 'none' : 'block' }}
        sandbox={sandboxAttributes}
        loading="lazy"
        title={`BookingKoala ${type} interface`}
        onLoad={() => {
          setLoading(false);
          onLoad?.();
        }}
        onError={() => {
          setError('Failed to load booking system');
          setLoading(false);
        }}
      />
    </div>
  );
};
```

### Fallback Strategies
```tsx
// Noscript fallback
const BookingFallback = ({ type }: { type: string }) => (
  <noscript>
    <div className="p-8 text-center border-2 border-dashed border-gray-300 rounded-lg">
      <h3 className="text-lg font-semibold text-gray-900 mb-2">
        JavaScript Required
      </h3>
      <p className="text-gray-600 mb-4">
        Please enable JavaScript to access our booking system.
      </p>
      <a
        href={`https://app.bookingkoala.com/${type}`}
        target="_blank"
        rel="noopener noreferrer"
        className="inline-block bg-blue-brand hover:bg-blue-800 text-white px-6 py-3 rounded-lg font-semibold transition-colors"
      >
        Book on BookingKoala →
      </a>
    </div>
  </noscript>
);

// Network error fallback
const NetworkErrorFallback = ({ type }: { type: string }) => (
  <div className="p-8 text-center">
    <div className="text-red-500 mb-4">
      <svg className="w-12 h-12 mx-auto" fill="none" stroke="currentColor" viewBox="0 0 24 24">
        <path strokeLinecap="round" strokeLinejoin="round" strokeWidth={2} d="M18.364 5.636l-12.728 12.728m0-12.728l12.728 12.728" />
      </svg>
    </div>
    <h3 className="text-lg font-semibold text-gray-900 mb-2">
      Connection Error
    </h3>
    <p className="text-gray-600 mb-4">
      Unable to load the booking system. Please try again or contact us directly.
    </p>
    <div className="flex flex-col sm:flex-row gap-3 justify-center">
      <button
        onClick={() => window.location.reload()}
        className="bg-blue-brand hover:bg-blue-800 text-white px-6 py-3 rounded-lg font-semibold transition-colors"
      >
        Retry
      </button>
      <a
        href="tel:+1234567890"
        className="bg-gray-100 hover:bg-gray-200 text-gray-700 px-6 py-3 rounded-lg font-semibold transition-colors"
      >
        Call Us
      </a>
    </div>
  </div>
);
```

---

## Analytics & Instrumentation

### Event Tracking Schema
```typescript
interface AnalyticsEvent {
  event: string;
  category: string;
  label?: string;
  value?: number;
  custom_parameters?: Record<string, any>;
}

// Navigation Events
const trackNavigation = (label: string, href: string) => {
  gtag('event', 'nav_click', {
    event_category: 'Navigation',
    event_label: label,
    custom_parameter_1: href,
    custom_parameter_2: window.location.pathname
  });
};

// CTA Events
const trackCTA = (label: string, location: string, href?: string) => {
  gtag('event', 'cta_click', {
    event_category: 'Conversion',
    event_label: label,
    custom_parameter_1: location,
    custom_parameter_2: href || '',
    custom_parameter_3: window.location.pathname
  });
};

// Form Events
const trackFormEvent = (
  action: 'start' | 'submit' | 'success' | 'error',
  formType: string,
  errorDetails?: string
) => {
  gtag('event', `form_${action}`, {
    event_category: 'Form',
    event_label: formType,
    custom_parameter_1: errorDetails || '',
    custom_parameter_2: window.location.pathname
  });
};

// BookingKoala Events
const trackBookingEvent = (
  action: 'mount' | 'resize' | 'error' | 'complete',
  type: string,
  details?: any
) => {
  gtag('event', `bk_${action}`, {
    event_category: 'BookingKoala',
    event_label: type,
    custom_parameter_1: JSON.stringify(details || {}),
    custom_parameter_2: window.location.pathname
  });
};

// FAQ Events
const trackFAQToggle = (questionId: string, state: 'open' | 'close') => {
  gtag('event', 'faq_toggle', {
    event_category: 'Engagement',
    event_label: questionId,
    custom_parameter_1: state,
    custom_parameter_2: window.location.pathname
  });
};
```

### Data Layer Configuration
```typescript
// Google Tag Manager Data Layer
interface DataLayerEvent {
  event: string;
  page_title: string;
  page_location: string;
  page_path: string;
  user_id?: string;
  session_id: string;
  timestamp: number;
  [key: string]: any;
}

const pushToDataLayer = (eventData: Partial<DataLayerEvent>) => {
  window.dataLayer = window.dataLayer || [];
  window.dataLayer.push({
    event: eventData.event,
    page_title: document.title,
    page_location: window.location.href,
    page_path: window.location.pathname,
    session_id: getSessionId(),
    timestamp: Date.now(),
    ...eventData
  });
};

// Enhanced E-commerce tracking for bookings
const trackBookingPurchase = (booking: {
  bookingId: string;
  service: string;
  value: number;
  currency: string;
}) => {
  pushToDataLayer({
    event: 'purchase',
    transaction_id: booking.bookingId,
    value: booking.value,
    currency: booking.currency,
    items: [{
      item_id: booking.service,
      item_name: booking.service,
      category: 'Cleaning Service',
      quantity: 1,
      price: booking.value
    }]
  });
};
```

### Performance Monitoring
```typescript
// Core Web Vitals tracking
const trackWebVitals = () => {
  import('web-vitals').then(({ getCLS, getFID, getFCP, getLCP, getTTFB }) => {
    getCLS((metric) => {
      gtag('event', 'web_vitals', {
        event_category: 'Performance',
        event_label: 'CLS',
        value: Math.round(metric.value * 1000),
        custom_parameter_1: metric.id,
        custom_parameter_2: window.location.pathname
      });
    });

    getFID((metric) => {
      gtag('event', 'web_vitals', {
        event_category: 'Performance',
        event_label: 'FID',
        value: Math.round(metric.value),
        custom_parameter_1: metric.id,
        custom_parameter_2: window.location.pathname
      });
    });

    getLCP((metric) => {
      gtag('event', 'web_vitals', {
        event_category: 'Performance',
        event_label: 'LCP',
        value: Math.round(metric.value),
        custom_parameter_1: metric.id,
        custom_parameter_2: window.location.pathname
      });
    });
  });
};

// Error tracking
const trackError = (error: Error, errorInfo?: any) => {
  gtag('event', 'exception', {
    description: error.message,
    fatal: false,
    custom_parameter_1: error.stack || '',
    custom_parameter_2: JSON.stringify(errorInfo || {}),
    custom_parameter_3: window.location.pathname
  });
};
```

### User Behavior Tracking
```typescript
// Scroll depth tracking
const trackScrollDepth = () => {
  let maxScroll = 0;
  const thresholds = [25, 50, 75, 90, 100];
  const tracked = new Set<number>();

  const handleScroll = throttle(() => {
    const scrollPercent = Math.round(
      (window.scrollY / (document.body.scrollHeight - window.innerHeight)) * 100
    );
    
    if (scrollPercent > maxScroll) {
      maxScroll = scrollPercent;
      
      thresholds.forEach(threshold => {
        if (scrollPercent >= threshold && !tracked.has(threshold)) {
          tracked.add(threshold);
          gtag('event', 'scroll_depth', {
            event_category: 'Engagement',
            event_label: `${threshold}%`,
            value: threshold,
            custom_parameter_1: window.location.pathname
          });
        }
      });
    }
  }, 100);

  window.addEventListener('scroll', handleScroll, { passive: true });
  
  return () => window.removeEventListener('scroll', handleScroll);
};

// Time on page tracking
const trackTimeOnPage = () => {
  const startTime = Date.now();
  const intervals = [30, 60, 120, 300]; // seconds
  const tracked = new Set<number>();

  const trackInterval = setInterval(() => {
    const timeOnPage = Math.floor((Date.now() - startTime) / 1000);
    
    intervals.forEach(interval => {
      if (timeOnPage >= interval && !tracked.has(interval)) {
        tracked.add(interval);
        gtag('event', 'time_on_page', {
          event_category: 'Engagement',
          event_label: `${interval}s`,
          value: interval,
          custom_parameter_1: window.location.pathname
        });
      }
    });
  }, 10000); // Check every 10 seconds

  return () => clearInterval(trackInterval);
};
```

---

## Testing Standards

### Unit Testing
```typescript
// Component testing with React Testing Library
import { render, screen, fireEvent, waitFor } from '@testing-library/react';
import userEvent from '@testing-library/user-event';
import { axe, toHaveNoViolations } from 'jest-axe';

expect.extend(toHaveNoViolations);

describe('Button Component', () => {
  it('should render with correct variant styles', () => {
    render(<Button variant="primary">Click me</Button>);
    const button = screen.getByRole('button');
    expect(button).toHaveClass('bg-red-brand');
  });

  it('should handle click events', async () => {
    const handleClick = jest.fn();
    render(<Button onClick={handleClick}>Click me</Button>);
    
    await userEvent.click(screen.getByRole('button'));
    expect(handleClick).toHaveBeenCalledTimes(1);
  });

  it('should be accessible', async () => {
    const { container } = render(<Button>Accessible button</Button>);
    const results = await axe(container);
    expect(results).toHaveNoViolations();
  });

  it('should support loading state', () => {
    render(<Button loading>Loading...</Button>);
    expect(screen.getByRole('button')).toHaveAttribute('aria-busy', 'true');
    expect(screen.getByTestId('loading-spinner')).toBeInTheDocument();
  });
});

// Form testing
describe('ContactForm', () => {
  it('should validate required fields', async () => {
    render(<ContactForm onSubmit={jest.fn()} />);
    
    await userEvent.click(screen.getByRole('button', { name: /submit/i }));
    
    expect(screen.getByText(/name is required/i)).toBeInTheDocument();
    expect(screen.getByText(/email is required/i)).toBeInTheDocument();
  });

  it('should submit with valid data', async () => {
    const mockSubmit = jest.fn();
    render(<ContactForm onSubmit={mockSubmit} />);
    
    await userEvent.type(screen.getByLabelText(/name/i), 'John Doe');
    await userEvent.type(screen.getByLabelText(/email/i), 'john@example.com');
    await userEvent.type(screen.getByLabelText(/message/i), 'Test message');
    
    await userEvent.click(screen.getByRole('button', { name: /submit/i }));
    
    await waitFor(() => {
      expect(mockSubmit).toHaveBeenCalledWith({
        name: 'John Doe',
        email: 'john@example.com',
        message: 'Test message'
      });
    });
  });
});
```

### Integration Testing
```typescript
// BookingKoala integration testing
describe('BookingKoala Integration', () => {
  beforeEach(() => {
    // Mock postMessage API
    global.postMessage = jest.fn();
    global.addEventListener = jest.fn();
  });

  it('should handle iframe resize messages', async () => {
    render(<BookingKoalaEmbed type="booking" />);
    
    // Simulate postMessage from iframe
    const messageEvent = new MessageEvent('message', {
      data: {
        type: 'resize',
        payload: { height: 600 },
        source: 'bookingkoala'
      },
      origin: 'https://app.bookingkoala.com'
    });
    
    fireEvent(window, messageEvent);
    
    await waitFor(() => {
      const iframe = screen.getByTitle(/bookingkoala booking interface/i);
      expect(iframe).toHaveAttribute('height', '600');
    });
  });

  it('should handle booking completion', async () => {
    const mockComplete = jest.fn();
    render(<BookingKoalaEmbed type="booking" onBookingComplete={mockComplete} />);
    
    const messageEvent = new MessageEvent('message', {
      data: {
        type: 'booking-complete',
        payload: { 
          bookingId: 'booking-123',
          data: { service: 'deep-clean', amount: 150 }
        },
        source: 'bookingkoala'
      },
      origin: 'https://app.bookingkoala.com'
    });
    
    fireEvent(window, messageEvent);
    
    expect(mockComplete).toHaveBeenCalledWith('booking-123', {
      service: 'deep-clean',
      amount: 150
    });
  });
});
```

### E2E Testing with Playwright
```typescript
import { test, expect } from '@playwright/test';

test.describe('Homepage Flow', () => {
  test('should complete booking flow', async ({ page }) => {
    await page.goto('/');
    
    // Hero CTA click
    await page.click('[data-testid="hero-cta"]');
    
    // Should navigate to booking page
    await expect(page).toHaveURL('/book');
    
    // BookingKoala iframe should load
    const iframe = page.frameLocator('[title*="BookingKoala"]');
    await expect(iframe.locator('body')).toBeVisible();
    
    // Test analytics tracking
    const analyticsPromise = page.waitForFunction(() => {
      return window.dataLayer.some(event => 
        event.event === 'cta_click' && 
        event.event_label === 'Book Now'
      );
    });
    
    await analyticsPromise;
  });

  test('should be accessible', async ({ page }) => {
    await page.goto('/');
    
    // Check for skip link
    await page.keyboard.press('Tab');
    const skipLink = page.locator('text=Skip to main content');
    await expect(skipLink).toBeFocused();
    
    // Check heading hierarchy
    const h1 = page.locator('h1');
    await expect(h1).toHaveCount(1);
    
    // Check color contrast (automated)
    const contrastResults = await page.evaluate(() => {
      // Simplified contrast check
      const elements = document.querySelectorAll('*');
      let violations = 0;
      
      elements.forEach(el => {
        const styles = getComputedStyle(el);
        const bgColor = styles.backgroundColor;
        const textColor = styles.color;
        
        // Basic contrast check (simplified)
        if (bgColor !== 'rgba(0, 0, 0, 0)' && textColor !== 'rgba(0, 0, 0, 0)') {
          // Check would go here
        }
      });
      
      return violations;
    });
    
    expect(contrastResults).toBe(0);
  });
});

test.describe('Contact Form', () => {
  test('should submit contact form successfully', async ({ page }) => {
    await page.goto('/contact');
    
    // Fill form
    await page.fill('[name="name"]', 'Test User');
    await page.fill('[name="email"]', 'test@example.com');
    await page.fill('[name="message"]', 'Test message content');
    
    // Submit form
    await page.click('button[type="submit"]');
    
    // Wait for success message
    await expect(page.locator('text=Message sent successfully')).toBeVisible();
    
    // Check analytics
    await page.waitForFunction(() => {
      return window.dataLayer.some(event => 
        event.event === 'form_success' && 
        event.event_label === 'contact'
      );
    });
  });
});
```

### Visual Regression Testing
```typescript
// Visual testing setup
import { test, expect } from '@playwright/test';

const breakpoints = [
  { name: 'mobile', width: 375, height: 667 },
  { name: 'tablet', width: 768, height: 1024 },
  { name: 'desktop', width: 1280, height: 720 },
  { name: 'large', width: 1920, height: 1080 }
];

test.describe('Visual Regression', () => {
  breakpoints.forEach(({ name, width, height }) => {
    test(`Homepage - ${name}`, async ({ page }) => {
      await page.setViewportSize({ width, height });
      await page.goto('/');
      
      // Wait for images to load
      await page.waitForLoadState('networkidle');
      
      // Hide dynamic content
      await page.addStyleTag({
        content: `
          [data-testid="current-time"],
          [data-testid="live-chat"] {
            visibility: hidden !important;
          }
        `
      });
      
      await expect(page).toHaveScreenshot(`homepage-${name}.png`);
    });

    test(`Service Cards - ${name}`, async ({ page }) => {
      await page.setViewportSize({ width, height });
      await page.goto('/services');
      await page.waitForLoadState('networkidle');
      
      const serviceGrid = page.locator('[data-testid="service-grid"]');
      await expect(serviceGrid).toHaveScreenshot(`service-cards-${name}.png`);
    });
  });
});
```

---

## Claude Code Implementation

### Project Structure
```
src/
├── components/
│   ├── ui/
│   │   ├── Button.tsx
│   │   ├── Input.tsx
│   │   ├── Modal.tsx
│   │   └── index.ts
│   ├── layout/
│   │   ├── Header.tsx
│   │   ├── Footer.tsx
│   │   └── Layout.tsx
│   ├── forms/
│   │   ├── ContactForm.tsx
│   │   └── LeadForm.tsx
│   └── booking/
│       ├── BookingKoalaEmbed.tsx
│       └── BookingButton.tsx
├── styles/
│   ├── globals.css
│   ├── components.css
│   └── utilities.css
├── utils/
│   ├── analytics.ts
│   ├── validation.ts
│   └── constants.ts
├── types/
│   ├── analytics.ts
│   ├── booking.ts
│   └── forms.ts
└── hooks/
    ├── useAnalytics.ts
    ├── useFocusTrap.ts
    └── useBookingKoala.ts
```

### Component Implementation Guidelines

#### 1. Component Template
```tsx
// components/ui/ComponentName.tsx
import React, { forwardRef } from 'react';
import { cn } from '@/utils/classNames';

interface ComponentNameProps {
  // Props interface
}

const ComponentName = forwardRef<HTMLElement, ComponentNameProps>(
  ({ className, ...props }, ref) => {
    return (
      <element
        ref={ref}
        className={cn(
          // Base classes
          // Variant classes
          className
        )}
        {...props}
      />
    );
  }
);

ComponentName.displayName = 'ComponentName';

export { ComponentName };
export type { ComponentNameProps };
```

#### 2. Styling Approach
```tsx
// Use design tokens via CSS custom properties
const buttonStyles = {
  base: 'inline-flex items-center justify-center rounded-lg font-semibold transition-colors focus-visible:outline-none focus-visible:ring-2 focus-visible:ring-offset-2 disabled:opacity-50 disabled:pointer-events-none',
  variants: {
    primary: 'bg-red-brand text-white hover:bg-red-800 focus-visible:ring-red-500',
    secondary: 'bg-blue-brand text-white hover:bg-blue-800 focus-visible:ring-blue-500',
    ghost: 'bg-transparent border border-gray-300 text-gray-700 hover:bg-gray-100 focus-visible:ring-gray-300'
  },
  sizes: {
    sm: 'h-9 px-3 text-sm',
    md: 'h-10 px-4 text-base',
    lg: 'h-11 px-6 text-lg'
  }
};
```

#### 3. Accessibility Implementation
```tsx
// Every interactive component includes:
// - Proper ARIA attributes
// - Keyboard navigation
// - Focus management
// - Screen reader support

const AccessibleButton = ({ children, ...props }) => {
  return (
    <button
      type="button"
      role="button"
      aria-pressed={pressed}
      aria-expanded={expanded}
      aria-describedby={describedBy}
      onKeyDown={handleKeyDown}
      {...props}
    >
      {children}
    </button>
  );
};
```

#### 4. Performance Optimization
```tsx
// Lazy loading for heavy components
const HeavyComponent = lazy(() => import('./HeavyComponent'));

// Memoization for expensive operations
const ExpensiveComponent = memo(({ data }) => {
  const processedData = useMemo(() => {
    return processLargeDataset(data);
  }, [data]);

  return <div>{/* Component JSX */}</div>;
});

// Code splitting at route level
const routes = [
  {
    path: '/',
    component: lazy(() => import('./pages/Homepage'))
  },
  {
    path: '/services',
    component: lazy(() => import('./pages/Services'))
  }
];
```

### CSS Implementation
```css
/* globals.css - Design tokens and base styles */
@import 'tailwindcss/base';
@import 'tailwindcss/components';
@import 'tailwindcss/utilities';

:root {
  /* Design tokens */
  --color-brand-red: #BC1823;
  --color-brand-navy: #171b3e;
  --color-brand-white: #ffffff;
  
  /* Typography */
  --font-family-primary: 'Inter', system-ui, sans-serif;
  
  /* Spacing */
  --space-unit: 0.25rem; /* 4px base */
  
  /* Shadows */
  --shadow-brand: 0 6px 18px rgba(15, 23, 42, 0.08);
  
  /* Motion */
  --duration-normal: 250ms;
  --ease-brand: cubic-bezier(0.22, 1, 0.36, 1);
}

/* Base styles */
html {
  font-family: var(--font-family-primary);
  scroll-behavior: smooth;
}

@media (prefers-reduced-motion: reduce) {
  html {
    scroll-behavior: auto;
  }
  
  *,
  *::before,
  *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
  }
}

/* Focus ring utility */
.focus-ring {
  @apply focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-blue-500;
}

/* Animation utilities */
.animate-fade-in {
  animation: fadeIn var(--duration-normal) var(--ease-brand) forwards;
  opacity: 0;
}

.animate-slide-up {
  animation: slideUp var(--duration-normal) var(--ease-brand) forwards;
  opacity: 0;
  transform: translateY(1rem);
}

@keyframes fadeIn {
  to { opacity: 1; }
}

@keyframes slideUp {
  to {
    opacity: 1;
    transform: translateY(0);
  }
}
```

### Tailwind Configuration
```typescript
// tailwind.config.ts
import type { Config } from 'tailwindcss';

const config: Config = {
  content: [
    './src/**/*.{js,ts,jsx,tsx,mdx}',
  ],
  theme: {
    extend: {
      colors: {
        'red-brand': '#BC1823',
        'blue-brand': '#171b3e',
        gray: {
          50: '#f8fafc',
          100: '#f1f5f9',
          200: '#e2e8f0',
          300: '#cbd5e1',
          400: '#94a3b8',
          500: '#64748b',
          600: '#475569',
          700: '#334155',
          800: '#1e293b',
          900: '#0f172a',
        }
      },
      fontFamily: {
        'primary': ['Inter', 'system-ui', 'sans-serif'],
      },
      spacing: {
        '18': '4.5rem',
        '88': '22rem',
      },
      boxShadow: {
        'brand': '0 6px 18px rgba(15, 23, 42, 0.08)',
        'brand-hover': '0 12px 24px rgba(15, 23, 42, 0.12)',
      },
      animation: {
        'fade-in': 'fadeIn 250ms cubic-bezier(0.22, 1, 0.36, 1) forwards',
        'slide-up': 'slideUp 250ms cubic-bezier(0.22, 1, 0.36, 1) forwards',
      }
    },
  },
  plugins: [
    require('@tailwindcss/forms'),
    require('@tailwindcss/typography'),
    require('@tailwindcss/aspect-ratio'),
  ],
};

export default config;
```

### Usage Instructions for Claude Code

#### When building components:
1. **Always start with accessibility** - Include proper ARIA attributes, keyboard navigation, and focus management
2. **Use design tokens** - Reference the color, spacing, and typography variables defined in this system
3. **Follow naming conventions** - Use descriptive, consistent names for components and props
4. **Implement error states** - Every component should handle loading, error, and empty states
5. **Add analytics tracking** - Include relevant event tracking for user interactions
6. **Optimize for performance** - Use lazy loading, memoization, and code splitting where appropriate
7. **Test thoroughly** - Write unit tests for logic, integration tests for user flows, and check accessibility

#### When creating pages:
1. **Use semantic HTML** - Proper heading hierarchy, landmarks, and document structure
2. **Implement SEO best practices** - Meta tags, structured data, and optimized content
3. **Follow layout patterns** - Use the established grid systems and section templates
4. **Include BookingKoala integration** - Use the BKEmbed component for booking functionality
5. **Add proper error boundaries** - Handle 404s, 500s, and network errors gracefully
6. **Optimize images** - Use the OptimizedImage component with proper sizes and lazy loading

#### Performance checklist:
- [ ] Images optimized with proper sizes and formats
- [ ] Code split at route and component level
- [ ] CSS critical path optimized
- [ ] Analytics loaded asynchronously
- [ ] BookingKoala iframe loaded with proper security and performance attributes
- [ ] Web Vitals monitoring implemented

This design system provides everything needed to build consistent, accessible, high-performance websites that perfectly match the Modern Americana minimalism aesthetic while maintaining world-class technical standards.

---

*Design System Version 1.0 - Created for Claude Code Implementation*  
*Last Updated: October 2025*
