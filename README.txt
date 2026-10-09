📁 beam-farm/
├── 📁 public/                         # โฟลเดอร์สำหรับไฟล์ที่เรียกใช้ตรง ๆ (ไม่ผ่านการ Build)
│   ├── 🖼️ farm_bg.jpg                 # 🌟 [สำคัญ] รูปพื้นหลังทุ่งหญ้าฟาร์มที่แสดงบนจอ
│   └── 🔊 (ไฟล์เสียงต่าง ๆ เช่น bgm, sound effects)
│
├── 📁 src/
│   ├── 📁 assets/                     # โฟลเดอร์เก็บรูปภาพไอคอนหรือรูปประกอบย่อย
│   │   └── 📁 images/
│   │
│   ├── 📁 components/                 # คอมโพเนนต์หน้าจอหลัก
│   │   ├── 📄 FarmWorld.tsx           # 🌟 แผนที่ฟาร์ม, ระบบซูม/เลื่อนกล้อง, และโหมดลากย้ายสิ่งก่อสร้าง
│   │   ├── 📄 TopHUD.tsx              # แถบแสดง เหรียญ, เพชร, พลังงาน, เลเวล ด้านบน
│   │   ├── 📄 BottomDock.tsx          # แถบเมนูด้านล่าง (แผนที่, คลัง, ก่อสร้าง, สัตว์, ตลาด)
│   │   ├── 📄 LeftMenu.tsx            # เมนูด้านซ้าย (ภารกิจ, กิจกรรม, รางวัลรายวัน)
│   │   └── 📄 RightMenu.tsx           # เมนูด้านขวา (ร้านค้า, ตลาดรถกระบะ, กล่องของขวัญ)
│   │
│   ├── 📁 components/modals/          # หน้าต่าง Pop-up ต่าง ๆ เมื่อกดปุ่มหรือสิ่งก่อสร้าง
│   │   ├── 📄 BuildModal.tsx          # หน้าต่างเมนูก่อสร้างสิ่งต่าง ๆ
│   │   ├── 📄 SeedPickerModal.tsx     # หน้าต่างเลือกเมล็ดพันธุ์ตอนคลิกแปลงผัก
│   │   ├── 📄 InventoryModal.tsx      # หน้าต่างโรงนา/คลังเก็บผลผลิต
│   │   ├── 📄 ProductionModal.tsx     # หน้าต่างสั่งผลิตของในเตาอบ, โรงนม, โรงแยม
│   │   ├── 📄 AnimalCareModal.tsx     # หน้าต่างให้อาหารและดูแลสัตว์
│   │   ├── 📄 MarketModal.tsx         # หน้าต่างส่งออร์เดอร์รถกระบะ
│   │   ├── 📄 ShopModal.tsx           # ร้านค้าซื้อเมล็ดพันธุ์และไอเทม
│   │   ├── 📄 QuestsModal.tsx         # หน้าต่างภารกิจ
│   │   ├── 📄 DailyRewardsModal.tsx   # หน้าต่างเช็คอินรับรางวัลรายวัน
│   │   ├── 📄 EventsModal.tsx         # กิจกรรมเทศกาลเก็บเกี่ยว
│   │   ├── 📄 MailModal.tsx           # กล่องจดหมายรับของขวัญ
│   │   ├── 📄 FriendsModal.tsx        # ระบบเพื่อนบ้าน
│   │   ├── 📄 VisitFriendModal.tsx    # เยี่ยมชมฟาร์มเพื่อน
│   │   ├── 📄 WorldMapModal.tsx       # แผนที่โลกเดินทาง
│   │   ├── 📄 SettingsModal.tsx       # ตั้งค่าเสียงและชื่อฟาร์ม
│   │   ├── 📄 LevelUpModal.tsx        # ป๊อปอัปยินดีด้วยเมื่อเลเวลอัป
│   │   ├── 📄 GiftBoxModal.tsx        # กล่องของขวัญนำโชค
│   │   └── 📄 LogoInfoModal.tsx       # ข้อมูลผู้พัฒนาฟาร์ม
│   │
│   ├── 📁 data/
│   │   └── 📄 initialData.ts          # ข้อมูลพื้นฐาน (รายชื่อพืช CROPS, สูตรอาหาร RECIPES, เควสต์)
│   │
│   ├── 📁 types/
│   │   └── 📄 game.ts                 # 🌟 Type Definitions (Plot, AnimalPen, Factory, CropType ฯลฯ)
│   │
│   ├── 📁 utils/
│   │   └── 📄 audio.ts                # ระบบจัดการเสียงเอฟเฟกต์ในเกม (Web Audio API)
│   │
│   ├── 📄 App.tsx                     # 🌟 [สมองหลัก] ควบคุม State ทั้งหมด, วงลูปเวลา (Game Loop), บันทึกเกม
│   ├── 📄 main.tsx                    # จุดเริ่มต้นของ React (Mount เข้ากับ index.html)
│   └── 📄 index.css                   # สไตล์หลักและ Tailwind CSS directives
│
├── 📄 index.html                      # ไฟล์ HTML หลักที่แสดงบนเบราว์เซอร์
├── 📄 package.json                    # รายชื่อ Library (React, Lucide icons, Vite, Tailwind)
├── 📄 tailwind.config.js              # การตั้งค่า Tailwind CSS
├── 📄 tsconfig.json                   # การตั้งค่า TypeScript Compiler
└── 📄 vite.config.ts                  # การตั้งค่า Build Tool (Vite)