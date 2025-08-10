# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview

This is a Water Utility Prepaid Management Platform (水务预付费管理系统) prototype project containing HTML-based UI mockups for both administrative and mobile interfaces. The project has evolved to include comprehensive WaterMIS (Water Management Information System) requirements and design specifications. The project consists entirely of standalone HTML files with embedded CSS and JavaScript, designed to demonstrate the complete user experience for a water utility management system.

## Project Structure

### HTML Prototypes
- **Admin Interface**: `admin-*.html` - Desktop management interfaces with comprehensive functionality
- **Mobile Interface**: `wechat-*.html` - Mobile-optimized WeChat mini-program style interfaces
- **Design Documentation**: 
  - `Enhanced-UI-Design-System.md` - Comprehensive design system v4.0 with water industry theming
  - `WaterMIS-UI-Design-Implementation-Guide.md` - Implementation status and optimization roadmap  
  - `WaterMIS-UI-Redesign-Strategy.md` - Complete UI redesign strategy and guidelines
- **Requirements Documentation**: 
  - `WaterMIS智慧营业管理信息系统项目需求方案.md` - Complete WaterMIS system requirements specification
  - `水务预付费管理系统-完整项目需求解决方案.md` - Original prepaid system requirements
  - `xuqiu.md` - Original business requirements document

## Development Workflow

### HTML Prototype Development
**No build process required** - All HTML files are self-contained with embedded CSS and JavaScript.

**Preview and Testing**:
```bash
# Open HTML files directly in browser
# Windows:
start admin-dashboard.html
# Or drag and drop files into browser

# Mobile device testing:
# 1. Open browser DevTools (F12)
# 2. Toggle device toolbar (Ctrl+Shift+M / Cmd+Shift+M)
# 3. Select mobile device preset (iPhone, Android, etc.)

# Cross-browser testing:
# Test in Chrome, Firefox, Safari, and Edge
```

**Development Guidelines**:
- All HTML files contain complete, functional interfaces
- Embedded CSS uses consistent design system variables
- JavaScript is embedded for interactive functionality
- No external dependencies or build tools required

### Quality Assurance Process
1. **Design system consistency**: Reference `Enhanced-UI-Design-System.md` for v4.0 design standards
2. **Implementation status**: Check `WaterMIS-UI-Design-Implementation-Guide.md` for current redesign progress  
3. **Business requirements**: Cross-check with `WaterMIS智慧营业管理信息系统项目需求方案.md` for comprehensive requirements
4. **Cross-platform testing**: Verify admin interfaces on desktop, mobile interfaces on mobile devices
5. **Browser compatibility**: Test across Chrome, Firefox, Safari, and Edge
6. **WaterMIS compliance**: Ensure new features align with the 12-module WaterMIS architecture
7. **Redesign priority**: Use *-redesigned.html files as templates for new development

## Key Business Entities

### Core Data Models
Based on the WaterMIS requirements documentation:
- **UserInfo**: Customer management with regional organization and multi-meter support
- **Account**: Prepaid accounts linked to water meters and pricing tiers  
- **Transactions**: Balance changes, recharge history, consumption records with audit trails
- **PriceConfig**: Multi-tier pricing (1-6 levels) and rate scheduling with time-based variations
- **MeterDevices**: Water meter and smart card reader integration with remote monitoring
- **OperatorRoles**: Multi-level admin permissions with functional isolation
- **WaterPlants**: Water plant entities with regional hierarchy and production monitoring
- **RegionalStructure**: County → Township → Water Plant hierarchy with data isolation
- **BillingRecords**: Invoice management with multiple payment channels
- **ReportTemplates**: Configurable report generation with export capabilities

### Business Logic Requirements
- Identical business rules across admin and mobile interfaces
- Real-time balance synchronization between all touchpoints
- Multi-tier pricing support (1-6 levels) with automatic calculation
- Regional hierarchy (County → Township → Water Plant) with role-based data access
- Multi-level data isolation for water plant operations
- Comprehensive audit trails for all financial transactions
- Support for multiple meter reading methods (manual, handheld, remote)
- Integration with external payment systems (banks, mobile payment platforms)

## UI Design System

### Design Tokens
**Redesigned CSS Variables Structure** (implemented in *-redesigned.html files):
```css
:root {
  /* Smart water utility color palette */
  --primary-500: #2196f3;     /* WaterMIS brand blue */
  --success-500: #00bcd4;     /* Clear water blue - payments/success */
  --warning-500: #ff9800;     /* Sunshine orange - warnings */
  --danger-500: #f44336;      /* Coral red - errors/alerts */
  
  /* Extended color scales (50-900) for sophisticated theming */
  --primary-50: #e6f7ff;      /* Light backgrounds */
  --primary-900: #01579b;     /* Dark accents */
  
  /* Spacing system - 4px/8px base units */
  --space-1: 4px; --space-2: 8px; --space-4: 16px; --space-8: 32px;
  
  /* Border radius system */
  --radius-sm: 4px; --radius-md: 8px; --radius-lg: 12px; --radius-xl: 16px;
}
```

### Interface Patterns
- **Admin Interfaces**: Desktop-optimized with sidebar navigation, data tables, form layouts
- **Mobile Interfaces**: WeChat mini-program styling with bottom tab navigation
- **Responsive Breakpoints**: 320px-414px (mobile), 768px+ (desktop)
- **Accessibility**: Minimum 44px touch targets for mobile

### Available Prototypes
**Admin Management Pages (14 total)**:
- `admin-login.html` - Authentication
- `admin-dashboard-redesigned.html` ⭐ - **Redesigned** overview dashboard with 12-module navigation
- `admin-billing-center.html` ⭐ - **New** comprehensive billing management center
- `admin-user-management.html` - Customer management
- `admin-user-recharge.html` - Operator recharge processing
- `admin-account-management.html` - Account and meter management
- `admin-price-management.html` - Pricing configuration
- `admin-device-management.html` - Device monitoring
- `admin-report-center.html` - Reporting and analytics
- `admin-system-settings.html` - System configuration
- `admin-waterplant-management.html` - Water plant management
- `admin-region-management.html` - Regional hierarchy
- `admin-operator-management.html` - Operator accounts
- `admin-waterplant-monitor.html` - Plant monitoring

**Mobile User Pages (8 total)**:
- `wechat-login.html` - Mobile authentication
- `wechat-home-redesigned.html` ⭐ - **Redesigned** user dashboard with water-themed UI
- `mobile-meter-reading-redesigned.html` ⭐ - **New** mobile-optimized meter reading interface
- `wechat-recharge.html` - Self-service recharge
- `wechat-account-details.html` - Account information
- `wechat-transaction-history.html` - Transaction history
- `wechat-user-profile.html` - Profile management
- `wechat-notifications.html` - System notifications

## Development Guidelines

### Design Consistency

**Current Design Evolution**:
- **Legacy interfaces**: Basic color theming with limited design system
- **Redesigned interfaces** (*-redesigned.html): Advanced water industry theming with comprehensive design tokens

**Design System Guidelines**:
1. **Water industry color semantics**: Clear water blue for success/payments, coral red for errors, sunshine orange for warnings
2. **Advanced spacing system**: 4px/8px base units with systematic scaling (4px, 8px, 12px, 16px, 20px, 24px, 32px, 40px, 48px, 64px)
3. **Component patterns**: Water-themed card layouts, form styling with enhanced visual hierarchy
4. **Responsive approach**: Mobile-first for `wechat-*` files, desktop-first for `admin-*` files
5. **Progressive enhancement**: Use redesigned files as templates, gradually update legacy interfaces

### Business Logic Alignment
- Reference `WaterMIS智慧营业管理信息系统项目需求方案.md` for comprehensive system requirements (primary reference)
- Cross-check with `水务预付费管理系统-完整项目需求解决方案.md` for original requirements context
- Maintain UI flow consistency with documented business processes
- Ensure feature parity between admin and mobile interfaces where applicable

### WaterMIS System Architecture
The project implements a 12-module enterprise system:
1. **营业分区管理** - Regional business management with multi-level hierarchy
2. **抄表管理** - Meter reading with multiple input methods (manual, handheld, remote)
3. **收费管理** - Comprehensive billing with multiple payment channels
4. **预存水费管理** - Prepaid balance management and automatic deduction
5. **用户管理** - Customer lifecycle management with multi-meter support
6. **计量管理** - Meter device management and maintenance tracking
7. **数据查询** - Flexible query system with complex filter combinations
8. **统计报表** - Automated report generation with multiple output formats
9. **分析图表** - Visual analytics for operational insights
10. **人事管理** - Staff management with role-based permissions
11. **基本设置** - System configuration and parameter management
12. **系统维护** - System administration and data backup/recovery

## Common Development Tasks

### Prototype Development Workflow
1. **Template Selection**: Use *-redesigned.html files as starting templates for new interfaces
2. **Design System Check**: Reference `Enhanced-UI-Design-System.md` for v4.0 color/spacing/component guidelines  
3. **Implementation Status**: Check `WaterMIS-UI-Design-Implementation-Guide.md` for interface optimization priorities
4. **Requirements Validation**: Cross-check with `WaterMIS智慧营业管理信息系统项目需求方案.md`
5. **Preview Testing**: Open in browser, test responsive behavior with DevTools mobile simulation
6. **Cross-Device Validation**: Test admin interfaces on desktop, mobile interfaces on mobile devices
7. **Module Integration**: Ensure new features align with the 12-module WaterMIS architecture and redesign strategy

### Development Commands
```bash
# No build commands needed - static HTML files

# Preview files (Windows)
start admin-dashboard-redesigned.html    # Use redesigned version for new projects
start wechat-home-redesigned.html       # Use redesigned mobile interface
start admin-billing-center.html         # New billing management interface

# Development workflow commands
start admin-login.html                   # Standard interfaces for reference
start mobile-meter-reading-redesigned.html  # Mobile meter reading interface

# Validation commands (if tools available)
html5validator --root . --match "*.html"

# Quality checks for WaterMIS compliance
# - UTF-8 encoding for Chinese text support
# - CSS variable consistency across files (check against Enhanced-UI-Design-System.md)
# - Mobile viewport meta tag present
# - 12-module WaterMIS architecture alignment
# - Water industry color theming consistency
```

### File Organization
- **HTML files**: All in root directory with clear naming (`admin-*` vs `wechat-*`)
- **Documentation**: `.md` files for specifications and requirements
- **Assets**: All CSS/JS embedded in HTML files (no external dependencies)
- **Encoding**: UTF-8 for HTML files, maintain Chinese text support

## Troubleshooting

### Common Issues
- **Display Problems**: Check CSS `:root` variables are properly defined in each HTML file
- **Mobile Layout**: Verify responsive breakpoints (320px-414px mobile, 768px+ desktop)
- **JavaScript Errors**: Use browser DevTools (F12) Console for debugging
- **Design Inconsistencies**: Cross-reference `UI-Design-Specification.md`

### Performance Notes
- All assets embedded in HTML files - no build process or external dependencies
- Test across modern browsers: Chrome, Firefox, Safari, Edge
- Mobile interfaces optimized for touch (minimum 44px targets)