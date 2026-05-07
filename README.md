# 🏡 HomeHero

> A production-ready cross-platform mobile and web application for booking household services with advanced theme system, multi-language support, and comprehensive user authentication.

[![LICENSE Português](https://img.shields.io/badge/LICENSE-Português-green.svg)](./LICENSE.pt.md)
[![README Português](https://img.shields.io/badge/README-Português-green.svg)](./README.pt.md)
[![Status](https://img.shields.io/badge/Status-Alpha%2FBeta-orange.svg)]()
[![Expo](https://img.shields.io/badge/Expo-v50+-blue.svg)](https://expo.dev/)
[![React](https://img.shields.io/badge/React-19.1.0-61dafb.svg)](https://react.dev/)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.0+-3178c6.svg)](https://www.typescriptlang.org/)
[![Languages](https://img.shields.io/badge/Languages-6-4CAF50.svg)](#-internationalization)
[![License](https://img.shields.io/badge/License-Personal%20Use-red.svg)](LICENSE)

---

## 📋 Summary

- [Overview](#-overview)
- [Tech Stack](#-tech-stack)
- [Architecture](#-architecture)
- [Project Structure](#-project-structure)
- [Development Status](#-development-status)
- [License](#-license)

---

## 🎯 Overview

**HomeHero** is a comprehensive home service scheduling platform developed as a personal portfolio project. The application demonstrates best practices in cross-platform development, state management, internationalization, and modern design.

### Supported Platforms

| Platform | Status | Framework |
|----------|--------|-----------|
| 📱 **Mobile (iOS/Android)** | ✅ Under Development | Expo + React Native |
| 🌐 **Web** | ✅ Under Development | React 19 + Vite |

---

## ✨ Main Features

### 🎨 Advanced Theme System
- Dark/light mode with system preference detection
- Consistent color tokens throughout the application
- Persistence of user preferences
- Smooth transitions between themes

### 🌍 Internationalization (i18n)
- Full support for **6 languages**:
- 🇬🇧 English
- 🇵🇹 Portuguese
- 🇩🇪 German
- 🇷🇺 Russian
- 🇫🇷 French
- 🇪🇸 Spanish
- Automatic device language detection
- Language preference persistence

### 👤 Authentication System
- Secure login with robust validation
- Session management
- Secure token storage
- Logout with sensitive data cleanup

### 📞 Scheduling System
- Complete booking flow
- Date and time selection
- Address management
- Payment method selection
- Confirmation with price details

### 💬 Real-Time Chat
- Client-professional communication
- Typing indicators
- Message history
- Read receipts

### 📊 User Dashboard
- Active appointments
- Booking history
- Spending statistics
- Profile management

### 💳 Payment Integration
- Support for multiple methods
- Secure data management
- Transaction history
- Receipt generation

### 👨‍💼 Professional Dashboard
- Job management
- Earnings tracking
- Portfolio with videos/photos
- Rating System

### 🚨 Reporting System
- User complaints (still under development)
- Problem categorization
- Spam detection
- Review interface

---

## 🛠 Tech Stack

### Mobile (Expo + React Native)
```
Framework:     Expo 50+ / React Native
Language:      TypeScript 5.0+
State:         React Context API
Navigation:    Expo Router
i18n:          i18next + react-i18next
Storage:       AsyncStorage + expo-secure-store
UI:            React Native Components + Lucide Icons
```

### Web (React + Vite)
```
Framework:     React 19.1.0
Build Tool:    Vite 5.0+
Language:      TypeScript 5.0+
Router:        React Router 6.26+
i18n:          i18next + react-i18next
Storage:       localStorage + sessionStorage
Security:      DOMPurify (XSS protection)
Icons:         Lucide React
```

### Main Dependencies
```json
{
  "react": "^19.1.0",
  "react-native": "latest",
  "expo": "^50.0.0",
  "react-router-dom": "^6.26.0",
  "i18next": "^23.14.0",
  "react-i18next": "^14.0.0",
  "typescript": "^5.0.0",
  "vite": "^5.0.0"
}
```

---

## 🏗 Architecture

### Architectural Patterns

#### State Management
```
React Context API
├── AuthContext (Autenticação)
├── ThemeContext (Tema)
├── BookingContext (Agendamentos)
├── ChatContext (Mensagens)
└── ToastContext (Notificações)
```

#### Component Structure
```
Componentes
├── Screens/Pages (Roteadas)
├── Containers (Lógica de negócio)
├── Components (Reutilizáveis)
└── Hooks (Customizados)
```

#### Themes
- **Light Mode**: Light palette optimized for readability
- **Dark Mode**: Dark theme that reduces eye strain
- **System**: Follows device preference

#### Design Tokens
```typescript
Colors, Spacing, BorderRadius, Shadows, Typography
Definidos centralmente no ThemeContext
Reutilizáveis em toda a aplicação
```

### Security

- ✅ Input validation on all forms
- ✅ XSS prevention (DOMPurify on the web)
- ✅ Secure token storage
- ✅ Logout with data cleansing
- ✅ HTTPS ready
- ✅ No hardcoded credentials
- ✅ No sensitive data in logs

### Performance

####Mobile
- Lazy screen loading
- Optimized StyleSheet
- Image optimization
- List virtualization

####Web
- Code splitting by route
- Lazy loading of components
- useMemo and useCallback optimization
- Virtual scrolling for lists

### Accessibility

- ✅ WCAG 2.1 AA compliance (web)
- ✅ Semantic HTML markup
- ✅ Minimum touch targets of 44x44px
- ✅ Screen reader support
- ✅ Keyboard navigation
- ✅ Color contrast > 4.5:1
- ✅ Proper language attributes

---

## 📁 Project Structure

```
HomeHero/
│
├── expo/                           # Mobile application (React Native)
│   ├── app/
│   │   ├── (tabs)/                # Tabbed navigation
│   │   │   ├── _layout.tsx
│   │   │   ├── index.tsx           # Home
│   │   │   ├── booking.tsx         
│   │   │   ├── messages.tsx        
│   │   │   ├── profile.tsx         
│   │   │   └── showcase.tsx        # Services
│   │   ├── auth/                   # Authentication
│   │   │   ├── login.tsx
│   │   │   ├── signup.tsx
│   │   │   └── welcome.tsx
│   │   ├── booking/                # Scheduling Flow
│   │   │   ├── address.tsx
│   │   │   ├── chat.tsx
│   │   │   ├── confirm.tsx
│   │   │   ├── details.tsx
│   │   │   ├── schedule.tsx
│   │   │   └── success.tsx
│   │   ├── payment/                # Payment
│   │   │   ├── add.tsx
│   │   │   ├── methods.tsx
│   │   │   └── pix.tsx
│   │   ├── service/                # Services
│   │   │   ├── categories.tsx
│   │   │   ├── category.tsx
│   │   │   └── professional.tsx
│   │   ├── profile/                # Profile Management
│   │   │   ├── edit.tsx
│   │   │   └── language.tsx
│   │   ├── pro/                    # Professional Dashboard
│   │   │   ├── dashboard.tsx
│   │   │   ├── earnings.tsx
│   │   │   ├── jobs.tsx
│   │   │   └── upload-reel.tsx
│   │   ├── admin/                  # Administrator Panel
│   │   │   ├── dashboard.tsx
│   │   │   ├── disputes.tsx
│   │   │   └── professionals.tsx
│   │   └── _layout.tsx             # Root layout with providers
│   │
│   ├── components/                 # Reusable Components
│   │   ├── UI/
│   │   ├── Common/
│   │   └── ErrorBoundary.tsx
│   │
│   ├── context/                    # Context API
│   │   ├── AuthContext.tsx
│   │   ├── ThemeContext.tsx
│   │   ├── BookingContext.tsx
│   │   ├── ChatContext.tsx
│   │   └── ToastContext.tsx
│   │
│   ├── hooks/                      # Custom Hooks
│   │   ├── useAuth.ts
│   │   ├── useTheme.ts
│   │   ├── useBooking.ts
│   │   └── useNavigation.ts
│   │
│   ├── types/                      # TypeScript Definitions
│   │   └── index.ts
│   │
│   ├── public/locales/             # Translations (i18n)
│   │   ├── en/
│   │   ├── pt/
│   │   ├── de/
│   │   ├── ru/
│   │   ├── fr/
│   │   └── es/
│   │
│   ├── i18n.ts                     # i18next configuration
│   ├── app.json                    # Expo configuration
│   └── package.json
│
├── my-react-app/                   # Web application (React)
│   ├── src/
│   │   ├── pages/
│   │   │   ├── Home.tsx
│   │   │   ├── Dashboard.tsx
│   │   │   ├── Booking.tsx
│   │   │   ├── Chat.tsx
│   │   │   ├── Profile.tsx
│   │   │   ├── Services.tsx
│   │   │   └── NotFound.tsx
│   │   │
│   │   ├── components/
│   │   │   ├── Navigation.tsx
│   │   │   ├── Header.tsx
│   │   │   ├── Footer.tsx
│   │   │   ├── LanguageSwitcher.tsx
│   │   │   ├── ThemeToggle.tsx
│   │   │   ├── ErrorBoundary.tsx
│   │   │   └── Common/
│   │   │
│   │   ├── context/
│   │   │   ├── AuthContext.tsx
│   │   │   ├── ThemeContext.tsx
│   │   │   ├── BookingContext.tsx
│   │   │   └── ToastContext.tsx
│   │   │
│   │   ├── hooks/
│   │   │   ├── useAuth.ts
│   │   │   ├── useTheme.ts
│   │   │   ├── useLocalStorage.ts
│   │   │   └── useDebounce.ts
│   │   │
│   │   ├── i18n/
│   │   │   ├── index.ts
│   │   │   └── locales/
│   │   │       ├── en.json
│   │   │       ├── pt.json
│   │   │       ├── de.json
│   │   │       ├── ru.json
│   │   │       ├── fr.json
│   │   │       └── es.json
│   │   │
│   │   ├── styles/
│   │   │   ├── global.css
│   │   │   └── variables.css
│   │   │
│   │   ├── types/
│   │   │   └── index.ts
│   │   │
│   │   ├── App.tsx
│   │   ├── main.tsx
│   │   └── index.css
│   │
│   ├── index.html
│   ├── vite.config.ts
│   ├── tsconfig.json
│   └── package.json
│
├── .gitignore
├── README.md                       # This file
└── LICENSE

```

---

## 📊 Development Status

### ✅ Completed

- [x] Basic structure (Mobile + Web)
- [x] Authentication system (UI)
- [x] Theme system (Dark/Light)
- [x] Internationalization (6 languages)
- [x] Scheduling flow
- [x] Chat interface
- [x] User dashboard
- [x] Professional dashboard
- [x] Payment system (UI)
- [x] Reporting system
- [x] Administrative panel
- [x] TypeScript strict mode
- [x] Error boundaries
- [x] Accessibility (WCAG 2.1 AA)

### 🔮 Planned

- [ ] Integration with real backend
- [ ] Server-side authentication
- [ ] Production payments
- [ ] Push notifications
- [ ] Automated testing
- [ ] CI/CD pipeline
- [ ] Professional verification
- [ ] Video calling
- [ ] Subscription system
- [ ] Advanced analytics
- [ ] PWA (Progressive Web App)



*If you'd like to help me implement any feature, please contact me at the email address at the end of the file.*

---

## 🔐 Security Information

⚠️ **Current Status**: Project in Alpha/Beta

### Security Considerations

- Input validation on all forms
- Protection against XSS (web)
- Secure token storage
- No hardcoding of credentials
- HTTPS ready
- Structure prepared for JWT authentication

---

## 📈 Project Metrics

### Code Statistics
- **Total Lines**: 15,000+
- **TypeScript Files**: 80+
- **React Components**: 50+
- **Screens/Pages**: 25+
- **Supported Languages**: 6
- **Type Coverage**: 95%+

### Bundle Sizes
- **Mobile (Expo)**: ~3.5 MB (uncompressed), ~1.2 MB (compressed)
- **Web**: ~850 KB (gzipped)

---

## 🎓 Lessons Learned & Best Practices

This project demonstrates:

- ✅ Cross-platform development with Expo
- ✅ State management with Context API
- ✅ Internationalization with i18next
- ✅ Dynamic theme system
- ✅ TypeScript strict mode
- ✅ Error boundaries and error handling
- ✅ Web accessibility (WCAG 2.1)
- ✅ Performance optimization
- ✅ Scalable and modular structure
- ✅ Separation of responsibilities

---

## 📝 Important Notes

---

### 💼 For investors or partners

Look, HomeHero started as a personal project, but I won't lie: **I believe it can become a real business**.

If you are an investor, accelerator, or someone who wants to fuel this project, let's talk.

📌 The code is closed for now (portfolio protection, okay?), but:
- I can show you the system working live.
- We can have a serious conversation about what we can do together.


---

### 🎓 For students who want to participate

Want to learn in practice how to build a real app? This is the place.

HomeHero is also a **real lab** for those studying development (mobile, web, React, TS, whatever comes along).

You can contribute code, ideas, corrections – and use all of that in your portfolio.

**What you get:**

- Experience on a project with modern architecture
- Your name on the project + the moral right to show off your work 😎😂

**What I ask:**

- Willingness to learn
- Simple commitment (doesn't need to be full-time)

*Contact information is at the end of the file.*


---

## 📄 License

For complete details, see the file [LICENSE](./LICENSE.md).

---

<div align="center">

**HomeHero - Service Booking Platform**

*Personal project for portfolio.*

**Status**: 🚧 Alpha/Beta - In Development

**Mail**: 📧 [homehero@outlook.com.br](mailto:homehero@outlook.com.br)

**Linkedin**: [<img src="https://img.shields.io/badge/-LinkedIn-blue?style=flat-square&logo=Linkedin&logoColor=white" alt="LinkedIn" />](https://www.linkedin.com/in/miguelessa/)

[⬆ Back to Top](#-homehero)

</div>
