# 🚗 FleetBook - ระบบจองรถยนต์ในองค์กร

<div align="center">

![Next.js](https://img.shields.io/badge/Next.js-16.0.7-black?style=for-the-badge&logo=next.js)
![React](https://img.shields.io/badge/React-19.2.0-61DAFB?style=for-the-badge&logo=react)
![TypeScript](https://img.shields.io/badge/TypeScript-5-3178C6?style=for-the-badge&logo=typescript)
![Tailwind CSS](https://img.shields.io/badge/Tailwind-4-38B2AC?style=for-the-badge&logo=tailwind-css)
![LINE](https://img.shields.io/badge/LINE_LIFF-2.27.2-00C300?style=for-the-badge&logo=line)

**FleetBook** เป็นแพลตฟอร์มจองรถยนต์ในองค์กรที่พัฒนาด้วยเทคโนโลยีสมัยใหม่ รองรับการใช้งานทั้งบนเว็บและผ่าน LINE LIFF พร้อม AI Chatbot สำหรับการจองผ่านการสนทนาภาษาไทย

[คุณสมบัติ](#-features) •
[Tech Stack](#-tech-stack) •
[เริ่มต้นใช้งาน](#-quick-start) •
[เอกสาร](#-documentation)

</div>

---

## ✨ Features

### 👥 สำหรับผู้ใช้งาน (User Features)

| Feature | Description |
|---------|-------------|
| 🚗 **จองรถยนต์ 4 ขั้นตอน** | เลือกรถ → กำหนดวันเวลา → กรอกรายละเอียด → ยืนยันการจอง |
| 📅 **ปฏิทินการจอง** | ดูตารางการจองทั้งหมดในรูปแบบปฏิทิน |
| 📋 **การจองของฉัน** | ติดตามสถานะ, ดูประวัติ, และจัดการการจอง |
| 💳 **ชำระเงินและค่าปรับ** | ดูรายการค่าใช้จ่าย, ชำระเงิน, ดาวน์โหลดใบเสร็จ |
| 🔄 **Real-time Availability** | ตรวจสอบรถว่างแบบ real-time พร้อมตรวจจับความขัดแย้ง |
| 📱 **LINE Integration** | ใช้งานผ่าน LINE LIFF ได้ทันที |
| 🤖 **AI Chatbot** | จองรถผ่าน LINE OA ด้วยภาษาไทยธรรมชาติ |
| 🇹🇭 **ภาษาไทยเต็มรูปแบบ** | UI และข้อความทั้งหมดเป็นภาษาไทย |

### 🔧 สำหรับผู้ดูแลระบบ (Admin Features)

| Feature | Description |
|---------|-------------|
| 📊 **Dashboard** | ภาพรวมสถิติและ Analytics แบบ real-time |
| ✅ **อนุมัติการจอง** | ระบบ approval workflow พร้อม bulk operations |
| 🚙 **จัดการยานพาหนะ** | CRUD รถยนต์, ติดตามการบำรุงรักษา |
| 👤 **จัดการผู้ใช้** | อนุมัติผู้ใช้ใหม่, กำหนด role |
| 💰 **จัดการการเงิน** | ดูแลการชำระเงิน, สร้างค่าปรับ |
| 📈 **รายงาน** | รายงานการใช้งานและสถิติต่างๆ |

### 🔒 ความปลอดภัยและประสิทธิภาพ

- **Content Security Policy** - CSP headers ครบถ้วน รองรับ LINE LIFF
- **Rate Limiting** - ป้องกัน API abuse
- **Authentication** - LINE LIFF authentication + Role-based access control
- **Type Safety** - End-to-end type safety ด้วย tRPC และ TypeScript
- **Real-time Updates** - Live data sync ด้วย React Query

---

## 🛠️ Tech Stack

### Core Framework

| Technology | Version | Purpose |
|------------|---------|---------|
| **Next.js** | 16.0.7 | App Router, React Server Components, Turbopack |
| **React** | 19.2.0 | UI Framework + React Compiler |
| **TypeScript** | 5.x | Full type safety |
| **Tailwind CSS** | 4.x | Modern styling with custom design system |

### Backend & Database

| Technology | Version | Purpose |
|------------|---------|---------|
| **tRPC** | 11.7.1 | End-to-end type-safe APIs |
| **Drizzle ORM** | 0.44.7 | Type-safe database queries & migrations |
| **PostgreSQL** | - | Database (hosted on Supabase) |
| **React Query** | 5.90.7 | Data fetching, caching, state management |
| **Zod** | 4.1.12 | Schema validation |

### External Integrations

| Technology | Version | Purpose |
|------------|---------|---------|
| **LINE LIFF** | 2.27.2 | LINE Front-end Framework integration |
| **LINE Bot SDK** | 10.5.0 | LINE Messaging API for chatbot |
| **Google Gemini AI** | 0.24.1 | Intent recognition for chatbot |
| **Stripe** | 19.3.0 | Payment processing |
| **Supabase** | 2.80.0 | Auth & Database hosting |

### Development

| Tool | Purpose |
|------|---------|
| **pnpm** 9.0.0 | Package manager |
| **ESLint** 9.x | Code linting |
| **Drizzle Kit** | Database migrations |

---

## 🚀 Quick Start

### Prerequisites

- Node.js 18+ 
- pnpm 9.0.0+
- Supabase account
- LINE LIFF app (optional)

### Installation

1. **Clone และติดตั้ง dependencies:**

```bash
git clone <repository-url>
cd fleetbook-repo
pnpm install
```

2. **ตั้งค่า Environment Variables:**

```bash
cp .env.local.example .env.local
```

3. **แก้ไข `.env.local`:**

```env
# === Required ===
# Supabase Configuration
NEXT_PUBLIC_SUPABASE_URL=https://your-project.supabase.co
NEXT_PUBLIC_SUPABASE_ANON_KEY=your_supabase_anon_key
DATABASE_URL=postgresql://postgres.your-project-ref:password@aws-0-region.pooler.supabase.com:5432/postgres

# === LINE LIFF (Optional) ===
NEXT_PUBLIC_LIFF_ID=your_liff_app_id
NEXT_PUBLIC_SKIP_LIFF=true  # Skip LIFF in development

# === LINE Official Account Chatbot (Optional) ===
LINE_CHANNEL_ACCESS_TOKEN=your_line_channel_access_token
LINE_CHANNEL_SECRET=your_line_channel_secret
GOOGLE_GEMINI_API_KEY=your_gemini_api_key

# === Development ===
TRPC_DEBUG=true  # Enable tRPC debugging
```

4. **ตั้งค่า Database:**

```bash
# Generate migration files
pnpm db:generate

# Apply migrations
pnpm db:migrate

# หรือ Push schema โดยตรง (development)
pnpm db:push

# เพิ่มข้อมูลทดสอบ
pnpm db:seed
```

5. **เริ่ม Development Server:**

```bash
pnpm dev
```

เปิด [http://localhost:3000](http://localhost:3000) เพื่อดูแอพพลิเคชัน

---

## 📱 Available Scripts

### Development

| Command | Description |
|---------|-------------|
| `pnpm dev` | Start development server |
| `pnpm build` | Create production build |
| `pnpm start` | Start production server |
| `pnpm lint` | Run ESLint |

### Database Management

| Command | Description |
|---------|-------------|
| `pnpm db:generate` | Generate Drizzle migration files |
| `pnpm db:migrate` | Run database migrations |
| `pnpm db:push` | Push schema to database |
| `pnpm db:studio` | Open Drizzle Studio (Database GUI) |
| `pnpm db:seed` | Seed test data |

---

## 🏗️ Project Architecture

### Directory Structure

```
src/
├── app/                    # Next.js App Router pages
│   ├── admin/             # Admin routes (protected)
│   │   ├── approvals/     # Booking approval management
│   │   ├── dashboard/     # Admin dashboard & analytics
│   │   ├── fines/         # Fine management
│   │   ├── payments/      # Payment administration
│   │   ├── returns/       # Vehicle return processing
│   │   ├── reports/       # Reports & statistics
│   │   ├── settings/      # System settings
│   │   ├── users/         # User management
│   │   └── vehicles/      # Fleet management
│   ├── api/
│   │   ├── trpc/          # tRPC API endpoint
│   │   └── line/webhook/  # LINE chatbot webhook
│   ├── book/              # 4-step booking flow
│   ├── calendar/          # Calendar view
│   ├── my-bookings/       # User's booking history
│   ├── payments/          # User payments & fines
│   └── profile/           # User profile
├── components/
│   ├── admin/             # Admin-specific components
│   ├── auth/              # Auth guards (AuthGuard, ApprovalGuard)
│   ├── bookings/          # Booking flow components
│   ├── common/            # Reusable UI patterns
│   ├── layout/            # Header, Navigation, DashboardLayout
│   ├── profile/           # Profile components
│   ├── ui/                # Base UI components (Button, Card, etc.)
│   └── vehicles/          # Vehicle display components
├── context/
│   └── liff-context.tsx   # LINE LIFF React context
├── hooks/
│   ├── use-auth.ts        # Unified auth hook
│   ├── use-booking-state.ts
│   ├── use-liff-profile.ts
│   └── use-trpc.ts        # tRPC hooks
├── lib/
│   ├── ai/                # Gemini AI integration
│   ├── auth/              # Auth utilities & permissions
│   ├── db/
│   │   ├── schema/        # Drizzle table definitions
│   │   └── migrations/    # SQL migration files
│   ├── line/              # LINE chatbot handlers
│   ├── trpc/
│   │   ├── routers/       # tRPC procedure routers
│   │   └── context.ts     # Request context
│   └── utils/             # Utility functions
└── middleware.ts          # Edge middleware
```

### Route Structure

```
/                    # Homepage - Quick actions & available vehicles
/book                # 4-step vehicle booking process
/calendar            # Calendar view of bookings
/my-bookings         # User's booking history
  /[id]              # Individual booking details
/payments            # Payment management
/profile             # User profile

/admin/              # Admin area (requires admin role)
  /dashboard         # Overview & statistics
  /approvals         # Booking approval workflow
  /vehicles          # Fleet management (CRUD)
  /users             # User management & approvals
  /payments          # Payment administration
  /fines             # Fine management
  /returns           # Vehicle return processing
  /reports           # Reports & analytics
  /settings          # System configuration
```

---

## 🗄️ Database Schema

### Core Tables

**`users`** - บัญชีผู้ใช้เชื่อมกับ LINE
```typescript
{
  id: uuid
  lineUserId: string          // LINE user identifier
  displayName: string         // Display name from LINE
  email?: string
  phone?: string
  department?: string
  status: 'pending' | 'approved' | 'suspended' | 'rejected'
  role: 'user' | 'admin' | 'fleet_manager'
  isApproved: boolean
  rating: decimal             // User rating
  totalBookings: number
  completedBookings: number
}
```

**`vehicles`** - รายการรถยนต์
```typescript
{
  id: uuid
  make: string                // ยี่ห้อ (Toyota, Honda)
  model: string               // รุ่น (Camry, Civic)
  year: number
  licensePlate: string        // ทะเบียนรถ (unique)
  category: 'sedan' | 'suv' | 'pickup' | 'van'
  fuelType: 'gasoline' | 'diesel' | 'hybrid' | 'electric'
  seats: number
  isAvailable: boolean
  mileage: number             // กิโลเมตร
  dailyRate?: number          // ค่าเช่า (satang)
}
```

**`bookings`** - รายการจอง
```typescript
{
  id: uuid
  userId: uuid
  vehicleId: uuid
  startDate: timestamp
  endDate: timestamp
  purpose: string             // จุดประสงค์
  destination: string         // จุดหมาย
  passengerCount: number
  status: 'pending' | 'approved' | 'rejected' | 'in_progress' | 'completed' | 'cancelled'
  // Approval tracking
  approvedBy?: uuid
  approvedAt?: timestamp
  rejectionReason?: string
  // Trip tracking
  actualStartTime?: timestamp
  actualEndTime?: timestamp
  startMileage?: number
  endMileage?: number
  startFuelLevel?: string
  endFuelLevel?: string
}
```

**`payments`** - การชำระเงินและค่าปรับ
```typescript
{
  id: uuid
  userId: uuid
  bookingId?: uuid
  type: 'fine' | 'deposit' | 'damage' | 'fuel'
  amount: number              // จำนวนเงิน (satang = THB × 100)
  status: 'pending' | 'completed' | 'failed' | 'refunded'
  paymentMethod?: 'stripe' | 'promptpay' | 'cash' | 'bank_transfer'
  reason?: string             // เหตุผล (สำหรับค่าปรับ)
  dueDate?: timestamp
}
```

**`line_conversations`** - สถานะการสนทนา Chatbot
```typescript
{
  id: uuid
  lineUserId: string
  state: 'idle' | 'selecting_date' | 'selecting_vehicle' | ...
  context: jsonb              // ข้อมูลการจองที่รวบรวมได้
  lastIntent?: string
  expiresAt: timestamp        // หมดอายุหลัง 30 นาที
}
```

---

## 🤖 LINE Official Account Chatbot

FleetBook รองรับการจองรถผ่าน LINE Official Account ด้วย AI Chatbot ที่เข้าใจภาษาไทย

### ความสามารถ

| Feature | ตัวอย่างข้อความ |
|---------|------------------|
| **จองรถ** | "จองรถไปกรุงเทพ วันจันทร์หน้า" |
| **เช็ครถว่าง** | "วันศุกร์มีรถว่างไหม" |
| **ดูการจอง** | "การจองของฉัน" |
| **ยกเลิกการจอง** | "ยกเลิกการจอง" |
| **เช็คค่าปรับ** | "มีค่าปรับอะไรบ้าง" |
| **ดูรถทั้งหมด** | "มีรถอะไรบ้าง" |

### ตัวอย่างการสนทนา

```
User: อยากจองรถไปเชียงใหม่วันศุกร์หน้า 9 โมง ถึง บ่าย 3

Bot: 🚗 รถว่างสำหรับวันศุกร์ที่ 27 ธ.ค.
     [Vehicle Carousel: Toyota Camry, Honda Civic, ...]
     พิมพ์หมายเลขเพื่อเลือกรถ

User: 1

Bot: ✅ สรุปการจอง
     🚗 Toyota Camry (กข-1234)
     📅 ศุกร์ 27 ธ.ค. 2567
     ⏰ 09:00 - 15:00
     📍 เชียงใหม่
     
     ยืนยันการจองหรือไม่?
     [ยืนยัน] [ยกเลิก]
```

### การตั้งค่า LINE Chatbot

1. สร้าง LINE Official Account ที่ [LINE Developers Console](https://developers.line.biz/)
2. เปิดใช้งาน Messaging API และรับ Channel Access Token/Secret
3. ตั้งค่า Webhook URL: `https://your-domain.com/api/line/webhook`
4. รับ Gemini API Key จาก [Google AI Studio](https://makersuite.google.com/)
5. ตั้งค่า Environment Variables และ restart server

รายละเอียดเพิ่มเติม: [`docs/LINE_CHATBOT.md`](./docs/LINE_CHATBOT.md)

---

## 🔐 Authentication & Authorization

### LINE LIFF Integration

- **Automatic Authentication** - Login ผ่าน LINE app โดยอัตโนมัติ
- **Profile Sync** - ดึงข้อมูล profile จาก LINE
- **Development Bypass** - ตั้งค่า `NEXT_PUBLIC_SKIP_LIFF=true` สำหรับ development

### Role-Based Access Control

| Role | Permissions |
|------|-------------|
| `user` | จองรถ, ดูการจองของตัวเอง, ชำระเงิน |
| `fleet_manager` | เข้าถึง admin panel, อนุมัติการจอง, จัดการรถ |
| `admin` | สิทธิ์เต็มรูปแบบ, จัดการผู้ใช้, ตั้งค่าระบบ |

### Auth Guards

```tsx
// Basic approval check
<ApprovalGuard requireApproval={true}>
  <ProtectedContent />
</ApprovalGuard>

// Admin-only route (ใช้ใน admin layout)
<AuthGuard requireRole="admin" autoRedirect>
  <AdminContent />
</AuthGuard>
```

---

## 💰 Fine Calculation System

### ค่าปรับอัตโนมัติ

เมื่อ trip สิ้นสุด ระบบจะคำนวณค่าปรับอัตโนมัติ:

| ประเภท | อัตรา | เงื่อนไข |
|--------|-------|---------|
| **Late Return** | ฿100/ชั่วโมง | เกิน 15 นาที, สูงสุด ฿2,000 |
| **Fuel Fine** | ฿500 | น้ำมันลด >10% |
| **Damage (minor)** | ฿1,000 | ความเสียหายเล็กน้อย |
| **Damage (major)** | ฿5,000 | ความเสียหายร้ายแรง |

### หมายเหตุเรื่อง Amount

**จำนวนเงินทั้งหมดเก็บเป็น satang (THB × 100)**

```typescript
// ฿100 บาท = 10000 satang
amount: 10000

// แสดงผล
const thb = amount / 100  // 100
```

---

## 🧪 Development & Debugging

### Debug Tools

| Page | Purpose |
|------|---------|
| `/debug-trpc` | ทดสอบ tRPC API endpoints |
| `/liff-test` | ทดสอบ LINE LIFF features |

### Testing Locally with LINE Chatbot

1. ติดตั้ง ngrok: `brew install ngrok`
2. เริ่ม dev server: `pnpm dev`
3. เริ่ม ngrok: `ngrok http 3000`
4. ตั้ง webhook URL ใน LINE Developers Console
5. ส่งข้อความไปที่ LINE Official Account

### Test Data

รัน `pnpm db:seed` เพื่อสร้างข้อมูลทดสอบ:

| ประเภท | จำนวน | รายละเอียด |
|--------|-------|------------|
| Vehicles | 8 | Sedan, SUV, Pickup, Van, Electric |
| Users | 6 | Admin, Fleet Manager, Users, Pending |
| Bookings | 7 | สถานะต่างๆ |
| Payments | 4 | ค่าปรับและการชำระเงิน |

---

## 🌐 Deployment

### Vercel (Recommended)

1. เชื่อมต่อ repository กับ Vercel
2. ตั้งค่า environment variables ใน Vercel dashboard
3. Deploy อัตโนมัติผ่าน CI/CD

### Self-Hosted

```bash
# Build
pnpm build

# Start production server
pnpm start
```

### Environment Variables สำหรับ Production

ต้องตั้งค่าทั้งหมดสำหรับ production:
- Supabase credentials (URL, Anon Key, Database URL)
- LINE LIFF ID
- LINE Channel Access Token & Secret (ถ้าใช้ chatbot)
- Google Gemini API Key (ถ้าใช้ chatbot)

---

## 📚 Documentation

| Document | Description |
|----------|-------------|
| [`CLAUDE.md`](./CLAUDE.md) | Development guidelines & architecture |
| [`docs/DATABASE_SETUP.md`](./docs/DATABASE_SETUP.md) | Database configuration guide |
| [`docs/SECURITY_IMPLEMENTATION.md`](./docs/SECURITY_IMPLEMENTATION.md) | Security implementation details |
| [`docs/LINE_CHATBOT.md`](./docs/LINE_CHATBOT.md) | LINE OA AI Chatbot integration |

---

## 🤝 Contributing

1. Fork the repository
2. Create feature branch: `git checkout -b feature/amazing-feature`
3. Commit changes: `git commit -m 'Add amazing feature'`
4. Push to branch: `git push origin feature/amazing-feature`
5. Open a Pull Request

### Development Guidelines

- ✅ Follow TypeScript best practices
- ✅ Maintain end-to-end type safety
- ✅ Add appropriate error handling
- ✅ Include Thai language for user-facing text
- ✅ Test with both LIFF and non-LIFF environments
- ✅ Follow file naming conventions (kebab-case)

---

## 📄 License

This project is private and proprietary. All rights reserved.

---

<div align="center">

**FleetBook** — จองรถ โปร่งใส ตรวจสอบได้

ใช้งานง่ายผ่าน LINE และเว็บ 🚗

</div>
