# Kaos EUY!

**Bandung's Pride, Your Style** 🎨👕

반둥의 자부심을 담은 프리미엄 티셔츠 커스텀 주문 플랫폼

---

## 프로젝트 개요

Kaos EUY!는 인도네시아 반둥 지역의 문화와 특색을 담은 커스텀 티셔츠 브랜드입니다. 개인 및 단체 주문을 쉽고 빠르게 진행할 수 있는 온라인 플랫폼을 제공합니다.

### 주요 기능

- ✨ **커스텀 오더 시스템**: 개인(1-10장) 및 단체(10장 이상) 주문
- 🎨 **디자인 옵션**: 업로드, 템플릿, 요청 방식 지원
- 🛒 **장바구니 & 결제**: Zustand 기반 상태 관리
- 📱 **반응형 디자인**: Mobile-first 접근
- 🌏 **다국어 지원**: 인도네시아어 기반 (순다어 포함)

---

## 기술 스택

- **Framework**: Next.js 14 (App Router)
- **Language**: TypeScript
- **Styling**: Tailwind CSS
- **Animation**: Framer Motion
- **State Management**: Zustand
- **Form Handling**: React Hook Form + Zod
- **Icons**: Lucide React

---

## 시작하기

### 사전 요구사항

- Node.js 18.x 이상
- npm 또는 yarn

### 설치

1. **의존성 설치**

```bash
npm install
```

또는

```bash
yarn install
```

### 개발 서버 실행

```bash
npm run dev
```

또는

```bash
yarn dev
```

브라우저에서 [http://localhost:3000](http://localhost:3000)을 열어 확인하세요.

---

## 프로젝트 구조

```
kaos-euy/
├── src/
│   ├── app/                    # Next.js App Router 페이지
│   │   ├── layout.tsx          # 루트 레이아웃
│   │   ├── page.tsx            # 홈 페이지
│   │   ├── custom-order/       # 커스텀 오더 페이지
│   │   │   ├── page.tsx        # 오더 타입 선택
│   │   │   ├── personal/       # 개인 주문
│   │   │   └── bulk/           # 단체 주문
│   │   └── globals.css         # 글로벌 스타일
│   │
│   ├── components/             # 재사용 가능한 컴포넌트
│   │   ├── common/             # 공통 컴포넌트
│   │   │   └── Button.tsx
│   │   └── layout/             # 레이아웃 컴포넌트
│   │       ├── Header.tsx
│   │       └── Footer.tsx
│   │
│   ├── stores/                 # Zustand 스토어
│   │   ├── cart.ts             # 장바구니 스토어
│   │   └── customOrder.ts      # 커스텀 오더 스토어
│   │
│   └── types/                  # TypeScript 타입 정의
│       └── index.ts
│
├── public/                     # 정적 파일
├── tailwind.config.ts          # Tailwind 설정
├── tsconfig.json               # TypeScript 설정
├── next.config.js              # Next.js 설정
└── package.json
```

---

## 주요 라우트

| 경로 | 설명 |
|------|------|
| `/` | 홈 페이지 (Hero, Value Props) |
| `/products` | 제품 카탈로그 (예정) |
| `/custom-order` | 커스텀 오더 타입 선택 |
| `/custom-order/personal` | 개인 주문 폼 |
| `/custom-order/bulk` | 단체 주문 폼 (예정) |
| `/cart` | 장바구니 (예정) |
| `/about` | 브랜드 소개 (예정) |
| `/contact` | 문의 (예정) |

---

## 브랜드 가이드

### 컬러 팔레트

- **Primary**: `#FF6B35` (Sunset Orange) - 활기, 에너지
- **Secondary**: `#2D3436` (Charcoal) - 신뢰, 세련
- **Accent**: `#00B894` (Mint Green) - 신선함
- **Background**: `#FFEAA7` (Warm Cream) - 따뜻함

### 타이포그래피

- **Display**: Poppins (헤드라인)
- **Body**: Plus Jakarta Sans (본문)
- **Accent**: Pacifico (로고, 순다어)

### 브랜드 톤

- 친근하고 활기참 (Friendly & Energetic)
- 캐주얼 + 로컬 터치
- 순다어 표현 활용: "EUY!", "Hatur nuhun", "Wilujeng sumping"

---

## 커스텀 오더 필드

커스텀 오더 시스템은 다음 정보를 수집합니다:

1. **주문 타입**: Personal (1-10장) / Bulk (10장 이상)
2. **고객 정보**: 이름, 이메일, 전화번호
3. **제품 기본 옵션**: 카테고리, 색상, 소재
4. **사이즈 & 수량**: 사이즈별 수량
5. **디자인**: 업로드, 템플릿, 또는 요청
6. **프린트 옵션**: 위치, 기법
7. **순다 요소** (선택): 순다어 문구, 반둥 아이콘
8. **배송 정보**: 픽업 또는 배송

전체 타입 정의는 [src/types/index.ts](src/types/index.ts)를 참고하세요.

---

## 개발 가이드

### 새 페이지 추가

1. `src/app/` 아래에 폴더 생성
2. `page.tsx` 파일 추가
3. Next.js App Router가 자동으로 라우트 생성

### 컴포넌트 추가

1. `src/components/` 아래 적절한 폴더에 생성
2. TypeScript + TSX 사용
3. Props 타입 정의 필수

### 스토어 사용

```tsx
import { useCartStore } from '@/stores/cart';

// 컴포넌트 내부
const addItem = useCartStore((state) => state.addItem);
const items = useCartStore((state) => state.items);
```

---

## 빌드 & 배포

### 프로덕션 빌드

```bash
npm run build
```

### 프로덕션 실행

```bash
npm run start
```

### 권장 배포 플랫폼

- **Vercel** (추천)
- Netlify
- AWS Amplify

---

## 다음 단계

- [ ] Products 페이지 구현
- [ ] Cart 페이지 구현
- [ ] Checkout 프로세스
- [ ] Bulk Order 폼 완성
- [ ] About/Contact 페이지
- [ ] WhatsApp API 연동
- [ ] 결제 게이트웨이 연동 (Midtrans/Xendit)
- [ ] 이미지 업로드 기능
- [ ] 디자인 프리뷰 기능

---

## 라이선스

이 프로젝트는 Kaos EUY! 브랜드의 전용임

---

## 문의

- **Email**: hello@kaoseuy.com
- **WhatsApp**: +62 812-3456-7890
- **Location**: Bandung, Indonesia

---

**Hatur nuhun!** 🙏
