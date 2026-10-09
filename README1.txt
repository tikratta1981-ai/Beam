================================================================================
     🌾 BEAM FARM (B.P.) - เอกสารสถาปัตยกรรมและโครงสร้างระบบเกมฉบับสมบูรณ์ 🌾
================================================================================
เอกสารนี้ถูกจัดทำขึ้นเพื่อบันทึกโครงสร้างไฟล์ หน้าที่ของคอมโพเนนต์ ตรรกะระบบ (Game Logic)
และข้อมูลทั้งหมดของโปรเจกต์ "Beam Farm (B.P.)" อย่างละเอียดสูงสุด เพื่อใช้เป็นพิมพ์เขียว
ป้องกันข้อมูลสูญหาย และเป็นคู่มือหลักสำหรับการบำรุงรักษาและพัฒนาต่อยอดในอนาคต

เวอร์ชันระบบ: 6.2 (Vite + React 19 + TypeScript + Tailwind CSS + Three.js + AI นายชด TTS + Modular Security System + Responsive Dual-Farm Engine)
วันที่บันทึก: 2026-10-07

================================================================================
สารบัญ (TABLE OF CONTENTS)
================================================================================
1. ภาพรวมโปรเจกต์ (PROJECT OVERVIEW & HIGHLIGHTS)
2. แผนผังโครงสร้างไฟล์และโฟลเดอร์ทั้งหมด (COMPLETE DIRECTORY TREE)
3. รายละเอียดหน้าที่ของไฟล์ระดับ Root (CONFIGURATIONS & ENTRY POINTS)
4. แกนควบคุมระบบเกมหลัก (CORE GAME CONTROLLER - App.tsx)
5. สถาปัตยกรรมแผนที่และระบบจัดวางสิ่งก่อสร้าง (FarmWorld.tsx ENGINE)
   5.1 สถาปัตยกรรมลานไก่ 3D เสมือนจริง (Chicken3D & Avian Biomechanics)
   5.2 สถาปัตยกรรมตัวละคร 3D เดินในฟาร์ม (FarmCharacters3D Engine)
   5.3 สถาปัตยกรรมเตาอบขนมปัง 3D พร้อมควันไฟ (BakeryOven3D)
   5.4 สถาปัตยกรรมแปลงข้าวโพด 3D ลู่ลมพริ้วไหว (DraggableCorn3D)
   5.5 สถาปัตยกรรมระบบเคียวเก็บเกี่ยว (HarvestTool & HarvestSystem Swipe Engine)
   5.6 การแก้ปัญหา UI ซ้อนทับและการรวมแถบควบคุม (extraAction Toolbar Integration)
   5.7 สถาปัตยกรรมสลับฟาร์มคู่แบบไร้รอยต่อ (Dual Farm Architecture: Farm 1 & Farm 2)
6. สถาปัตยกรรมระบบทะเลสาบมรกตและมินิเกมตกปลา 3D (FISHING SYSTEM & LAKE ECOSYSTEM)
7. ระบบ AI นายชด ปราชญ์ชาวสวน พร้อมเสียงสังเคราะห์ภาษาไทย (AI CHOD ENGINE)
8. สถาปัตยกรรมการแยกโค้ดแบบโมดูลาร์ (MODULAR ARCHITECTURE REFACTORING)
9. แผงควบคุมและส่วนติดต่อผู้ใช้หลัก (HUD & DOCK INTERFACES)
   9.1 โปรไฟล์ปรับแต่งขนาดหน้าจอมือถือ (Mobile Profile: Vivo Y17 & Compact Viewports)
10. รายละเอียดหน้าต่างป๊อปอัปทั้งหมด (MODALS IN-DEPTH SPECIFICATION)
11. โครงสร้างประเภทข้อมูล (TYPES & DATA SCHEMAS - types/game.ts, auth.ts, fishing.ts)
12. คลังข้อมูลและค่าคงที่ (DATA & CONSTANTS - data/)
13. ระบบเสียงสังเคราะห์และพื้นผิว PBR (AUDIO & PBR UTILITIES - utils/)
14. สไตล์ ดีไซน์ซิสเต็ม และแอนิเมชัน (STYLING & CSS - index.css)
15. ทรัพยากรภาพและสินทรัพย์ (ASSETS & GRAPHICS - public/)
16. ระบบและตรรกะเกมเพลย์หลัก (GAMEPLAY MECHANICS & FORMULAS)
17. คู่มือการติดตั้ง คำสั่งคอมไพล์ และการแก้ปัญหา (SCRIPTS & TROUBLESHOOTING)
================================================================================
     🔐 ระบบรักษาความปลอดภัย (SECURITY SYSTEM) - BEAM FARM (B.P.) v6.1+ 🔐
================================================================================
18. ภาพรวมสถาปัตยกรรมความปลอดภัย (SECURITY ARCHITECTURE OVERVIEW)
19. โครงสร้างไฟล์ความปลอดภัย (SECURITY MODULE DIRECTORY)
20. รายละเอียดโมดูลความปลอดภัยเชิงลึก (SECURITY MODULES IN-DEPTH)
    20.1 security/crypto.ts — การเข้ารหัส Save Data (AES-GCM 256-bit & PBKDF2)
    20.2 security/integrity.ts — ตรวจสอบความสมบูรณ์ (SHA-256 Checksum & HMAC)
    20.3 security/sanitizer.ts — กรอง Input & ป้องกัน XSS / Injection / Zero-Width
    20.4 security/rateLimiter.ts — Token Bucket Rate Limiter (AI / TTS / Cloud / SFX)
    20.5 security/antiCheat.ts — Anti-Cheat Guard & Resource Clamping
    20.6 security/timeGuard.ts — Monotonic Clock & Clock Tampering Prevention
    20.7 security/secureStorage.ts — Secure Storage Wrapper & Rolling Auto-Backup 3 ชุด
21. การป้องกัน AI Prompt Injection & Jailbreak (AI CHOD SECURITY)
22. สถาปัตยกรรมความปลอดภัยเครือข่าย & CSP (NETWORK & CSP HARDENING)
23. แผนการกู้คืนข้อมูลและการตรวจสอบ (RECOVERY, AUDIT TRAIL & BACKUP LOG)
24. สรุปความพร้อมและสถานะการตรวจสอบความปลอดภัย (SECURITY READINESS CHECKLIST)

--------------------------------------------------------------------------------
1. ภาพรวมโปรเจกต์ (PROJECT OVERVIEW & HIGHLIGHTS)
--------------------------------------------------------------------------------
"Beam Farm (B.P.)" เป็นเว็บแอปพลิเคชันเกมจำลองชีวิตทำฟาร์ม (Farm Simulation Game)
แบบ Responsive Web App ที่ถูกออกแบบให้สามารถเล่นได้ลื่นไหลทั้งบนสมาร์ตโฟน (Touch-first,
Viewport-fit cover, ป้องกันจอดิ้น/จอขาว) แท็บเล็ต และคอมพิวเตอร์เดสก์ท็อป

คุณสมบัติเด่นของระบบ:
- แผนที่ฟาร์มแบบ Interactive Pan & Zoom (ซูมเข้า/ออก 1.0x - 2.5x เลื่อนมุมกล้องอิสระ)
- รองรับสลับอาณาเขตฟาร์ม 2 แห่งแบบทันที (Instant Seamless Map Switch):
  1) ฟาร์มหลักริมสายน้ำ (Farm 1 - Riverside Farm)
  2) อาณาเขตฟาร์มเกาะมรกต (Farm 2 - Emerald Island Farm)
- โหมดจัดวางสิ่งก่อสร้าง (Build Mode) ที่รองรับการลากย้าย (Drag & Drop),
  จัดตำแหน่งแม่เหล็กอัตโนมัติ (Snap to Grid 32px), หมุนสิ่งก่อสร้าง 90 องศา (Rotate),
  และพลิกด้านภาพซ้าย-ขวา (Flip/Mirror) พร้อมบันทึกลง LocalStorage อัตโนมัติ
- แถบปุ่มควบคุมเครื่องมือรวมเป็นแถวเดียว (Unified Control Toolbar) ไม่ทับซ้อนกันแม้บนจอขนาดเล็ก
- ระบบเก็บเกี่ยวผลผลิตด้วยเคียวปัดกวาด (Harvest Sickle Tool & Swipe System) ลากผ่านแปลงเพื่อเก็บรวงข้าวต่อเนื่อง
- วงจรการเพาะปลูกพืช (Agriculture Cycle): หว่านเมล็ด รดน้ำ เจริญเติบโต เร่งโต และเก็บเกี่ยว
- วงจรการเลี้ยงสัตว์ (Animal Care): ให้อาหารสัตว์ตามผลผลิตที่กำหนด ผลิตผล และเก็บเกี่ยว
- โรงงานแปรรูปผลผลิต (Production Chain): เตาอบขนมปัง 3D, โรงงานนมเนย, โรงแยม และกังหันลม
- ระบบการค้าส่ง (Truck Delivery & Market): กระดานรับออร์เดอร์ชาวเมือง พร้อมรถกระบะขนส่ง
- ระบบคลังผลผลิต (Barn Silo): มีระบบเช็กความจุคลัง และอัปเกรดขยายขนาดคลัง
- ระบบพลังงาน (Energy) และหลอดประสบการณ์ (Level & XP Progression)
- กิจกรรมและมินิเกมตกปลา 3D ทะเลสาบมรกต: สะสมพันธุ์ปลา, คราฟต์เหยื่อ, บัฟแมวนำโชค, สลับเวลากลางวัน/เย็น/กลางคืน
- ระบบสมาชิกและบัญชี (Account & Cloud Sync): ผูกบัญชี Gmail / Facebook / Guest เซฟแยกบัญชี
- กล่องจดหมาย (Mailbox), ภารกิจ (Quests), เทศกาลเก็บเกี่ยว (Festival), และรางวัลเช็คอินรายวัน
- ระบบเพื่อนบ้านจำลอง (Simulated Friends & Visiting Neighbors): เยี่ยมชมฟาร์มเพื่อนและส่งของขวัญ
- ระบบเสียง Web Audio API ในตัว 100%: ไม่ต้องโหลดไฟล์ .mp3 ภายนอก ทำงานได้ทันทีไม่มี Delay
- กราฟิก 3 มิติ Three.js ผสานกลืนกับพื้นผิว 2.5D: ไก่อารมณ์ดี 3D, เตาอบขนมปัง 3D, แปลงข้าวโพด 3D
- ตัวละคร 3 มิติเดินตรวจฟาร์ม: สาวชาวสวน (Emma), ลุงบ็อบ, ลิลี่, เดซี่, ลุงสมชาย, มายด์ (สาวนักตกปลา), สมศักดิ์ (คนงานบ่อปลา)
- 👨‍🌾 ระบบ AI นายชด ปราชญ์ชาวสวน: ปรึกษาฟาร์ม วิเคราะห์ผลผลิต พร้อมเสียงสังเคราะห์ภาษาไทย (TTS)
- สถาปัตยกรรม Clean Code แบบ Modular Components แยกไฟล์เป็นสัดส่วน ดูแลง่าย สบายตา

--------------------------------------------------------------------------------
2. แผนผังโครงสร้างไฟล์และโฟลเดอร์ทั้งหมด (COMPLETE DIRECTORY TREE)
--------------------------------------------------------------------------------
/
├── .env.example                               # แม่แบบตัวแปรสภาพแวดล้อม
├── .gitignore                                 # รายการไฟล์ที่ไม่รวมใน Git
├── index.html                                 # HTML Entry Point (Viewport, Fonts, CSP, CSS Reset)
├── metadata.json                              # ข้อมูลแอปและ Major Capabilities สำหรับ AI Studio
├── package.json                               # Dependencies, Scripts, DevDependencies
├── tsconfig.json                              # TypeScript Compiler Options (ES2022, React-JSX)
├── vite.config.ts                             # การตั้งค่า Vite Build, React Plugin & Path Alias
├── README.txt                                 # เอกสารภาพรวมการพัฒนาเวอร์ชันแรก
├── README1.txt                                # เอกสารโครงสร้างสถาปัตยกรรมฉบับสมบูรณ์ (ไฟล์นี้)
│
├── public/                                    # ไฟล์ Static สาธารณะ (โหลดตรงไม่ผ่าน Bundler)
│   ├── farm_bg.jpg                            # ภาพพื้นหลังฟาร์มหลักริมสายน้ำ (1440x960)
│   ├── farm2_bg.jpg                           # ภาพพื้นหลังอาณาเขตฟาร์มเกาะมรกต (1440x960)
│   ├── loading_screen.jpg                     # ภาพ Splash Screen หน้าจอโหลด
│   ├── logo_bp.png                            # ตราสัญลักษณ์เหรียญทองทานตะวัน B.P.
│   ├── avatar.png                             # ภาพโปรไฟล์ชาวสวนเริ่มต้น
│   └── buildings/                             # ภาพไอคอนสิ่งก่อสร้างและแปลงผลผลิต (.png)
│       ├── bakery_oven.png                    # เตาอบขนมปัง
│       ├── barn_silo.png                      # โรงนาและยุ้งฉาง
│       ├── chicken_coop.png                   # เล้าไก่อารมณ์ดี
│       ├── cow_pen.png                        # คอกโคนมฮอลสไตน์
│       ├── dairy_stall.png                    # โรงแปรรูปนมเนย
│       ├── farmhouse.png                      # บ้านพักชาวสวน
│       ├── flower_bed.png                     # แปลงดอกไม้ประดับ
│       ├── jam_house.png                      # โรงงานแยมผลไม้
│       ├── pig_pen.png                        # คอกหมู
│       ├── plot_corn.png                      # แปลงข้าวโพด
│       ├── plot_cucumber.png                  # แปลงแตงกวา
│       ├── plot_lavender.png                  # แปลงดอกลาเวนเดอร์
│       ├── plot_tomato.png                    # แปลงมะเขือเทศ
│       ├── plot_wheat.png                     # แปลงข้าวสาลี
│       ├── sheep.png                          # ทุ่งแกะขนปุย
│       ├── tree_apple.png                     # ต้นแอปเปิล
│       ├── tree_orange.png                    # ต้นส้มสายน้ำผึ้ง
│       ├── truck_blue.png                     # รถกระบะส่งของสีน้ำเงิน
│       ├── water_well.png                     # บ่อน้ำโบราณ
│       ├── wood_bridge.png                    # สะพานไม้ข้ามคลอง
│       └── wooden_boat.png                    # เรือพายไม้ริมตลิ่ง
│
├── src/
│   ├── main.tsx                               # จุด Mount React Root สู่ #root ใน DOM
│   ├── App.tsx                                # Game State Controller แกนหลักของทั้งระบบ
│   ├── index.css                              # Tailwind CSS v4, Wood UI, Scrollbars, Mobile Profiles
│   │
│   ├── types/
│   │   ├── game.ts                            # Data Types & Interfaces หลัก (CropType, Plot, AnimalPen ฯลฯ)
│   │   ├── auth.ts                            # Data Types สำหรับระบบสมาชิก (UserProfile, AuthProvider ฯลฯ)
│   │   └── fishing.ts                         # Data Types สำหรับระบบตกปลา (FishSpecies, FishingState ฯลฯ)
│   │
│   ├── data/
│   │   ├── initialData.ts                     # แคตตาล็อกพืช, สูตรอาหาร, สัตว์, เควสต์, รางวัล
│   │   ├── farmWorldData.ts                   # ผังเริ่มต้น Farm 1 & 2, แคตตาล็อกสิ่งก่อสร้าง, Stage 1440x960, Grid 32px
│   │   ├── gameConstants.ts                   # เลเวลปลดล็อกพืช, แม่แบบสัตว์, Storage Keys, GameSnapshot
│   │   ├── fishingData.ts                     # แคตตาล็อกพันธุ์ปลา อัตราการดรอป (Drop Rates)
│   │   └── worldMapData.ts                    # แผนที่โลกและคำสั่งสลับฟาร์มแบบไร้รอยต่อ (switchFarmMap)
│   │
│   ├── utils/
│   │   ├── audio.ts                           # SoundEngine สังเคราะห์เสียงผ่าน Web Audio API
│   │   ├── aiSpeech.ts                        # NaiChodVoiceEngine สังเคราะห์เสียงพูดภาษาไทย (TTS)
│   │   ├── aiChodBrain.ts                     # askNaiChod วิเคราะห์ฟาร์ม ตอบคำถามการเกษตร
│   │   ├── auth.ts                            # ระบบล็อกอิน Google / Facebook / Guest, บันทึกเซฟแยกตามบัญชี
│   │   ├── orderGenerator.ts                  # สุ่มเควสต์ออร์เดอร์รถกระบะตามเลเวลผู้เล่น
│   │   └── threeTextures.ts                   # โปรซีเดอรัล PBR Textures (ขนไก่, ยีนส์, ลายสก็อต, ดิน, ไม้)
│   │
│   ├── security/                              # 🔐 สถาปัตยกรรมความปลอดภัย (7-Layer Defense)
│   │   ├── index.ts                           # รวมและส่งออกโมดูลความปลอดภัย & ฟังก์ชัน initSecurity()
│   │   ├── crypto.ts                          # AES-GCM 256-bit + PBKDF2 Web Crypto API
│   │   ├── integrity.ts                       # SHA-256 Checksum และ HMAC-SHA256 ลงนามข้อมูล
│   │   ├── sanitizer.ts                       # กรองข้อความ XSS, HTML Escape, Zero-Width & Prompt Injection
│   │   ├── rateLimiter.ts                     # Token Bucket: จำกัดการเรียก AI, TTS, Cloud Sync, SFX
│   │   ├── antiCheat.ts                       # ตรวจสอบขอบเขตทรัพยากรเกม ป้องกันการปั๊มค่าและโกงเวลา
│   │   ├── secureStorage.ts                   # Wrapper ปลอดภัยของ localStorage พร้อม Rolling Backup 3 ชุด
│   │   ├── timeGuard.ts                       # MonotonicClock ป้องกันการปรับเปลี่ยนเวลาเครื่อง (Clock Tamper)
│   │   └── securityLog.ts                     # บันทึกประวัติเหตุการณ์ความปลอดภัย (Audit Trail Log)
│   │
│   └── components/                            # คอมโพเนนต์หน้าจอหลัก (Main Viewports & HUD)
│       ├── LoadingScreen.tsx                  # หน้าจอโหลดเตรียมระบบครั้งแรก (0% - 100% พร้อมเสียง)
│       ├── FarmWorld.tsx                      # เอนจินแผนที่ ซูม เลื่อนกล้อง ระบบจัดวาง และ Ground Contact AO
│       ├── TopHUD.tsx                         # แถบด้านบน: เลเวล, เหรียญ, เพชร, พลังงาน, ฟาร์ม
│       ├── BottomDock.tsx                     # เมนูด้านล่าง: แผนที่, คลัง, ก่อสร้าง, สัตว์, โรงงาน
│       ├── LeftMenu.tsx                       # เมนูด้านซ้าย: เควสต์, กิจกรรม, เช็คอินรายวัน
│       ├── RightMenu.tsx                      # เมนูด้านขวา: ตลาดรถกระบะ, ร้านค้า, กล่องของขวัญ
│       │
│       ├── common/                            # คอมโพเนนต์ส่วนกลาง
│       │   └── Toast.tsx                      # Floating System Toast แจ้งเตือนสถานะเกม
│       │
│       ├── farm/                              # คอมโพเนนต์ย่อยของแผนที่ฟาร์ม
│       │   ├── FarmControls.tsx               # แถบปุ่มควบคุมการซูม, จัดผังอัตโนมัติ, Snap, เปิด/ปิด 3D + extraAction
│       │   ├── BuildableCatalogModal.tsx      # หน้าต่างเลือกสิ่งก่อสร้าง สัตว์ และของตกแต่ง
│       │   ├── EntityToolbar.tsx              # แถบเครื่องมือ หมุน 90° / พลิก / ลบ / ยืนยัน ในโหมดจัดวาง
│       │   ├── HarvestTool.tsx                # ปุ่มสลับโหมดเคียวและตัวเคียวเรนเดอร์ผ่าน React Portal
│       │   └── HarvestSystem.ts               # ระบบ Swipe Detection ฟันเคียวเก็บเกี่ยวรวดเดียวหลายแปลง
│       │
│       ├── 3d/                                # คอมโพเนนต์กราฟิก 3 มิติเสมือนจริง (Three.js)
│       │   ├── Chicken3D.tsx                  # ไก่ 3D กายวิภาคสมจริง + Avian Biomechanics + โปรยข้าว
│       │   ├── FarmCharacters3D.tsx           # ตัวละคร 3D เดินในฟาร์ม (เอ็มม่า, บ็อบ, ลิลี่, เดซี่, สมชาย, มายด์, สมศักดิ์)
│       │   ├── BakeryOven3D.tsx               # เตาอบขนมปัง 3D พร้อมควันไฟ Volumetric และแสงเตาอบ
│       │   ├── DraggableCorn3D.tsx            # แปลงข้าวโพด 3D ลู่ลมพริ้วไหว ปลอดภัย ไม่กินแรม
│       │   ├── EmeraldLake3D.tsx              # ทะเลสาบมรกต 3D น้ำระลอกคลื่น หิ่งห้อย แสงจันทร์/อาทิตย์/เย็น
│       │   ├── Bakery3D.tsx                   # โมเดลโรงงานเบเกอรี่ 3D
│       │   ├── Dairy3D.tsx                    # โมเดลโรงงานนมเนย 3D
│       │   ├── Jam3D.tsx                      # โมเดลโรงงานแยม 3D
│       │   ├── House3D.tsx                    # โมเดลบ้านพักชาวสวน 3D
│       │   ├── Tree3D.tsx                     # โมเดลต้นไม้ 3D
│       │   ├── Truck3D.tsx                    # โมเดลรถกระบะ 3D
│       │   ├── Well3D.tsx                     # โมเดลบ่อน้ำโบราณ 3D
│       │   ├── Cow3D.tsx                      # โมเดลวัวนม 3D
│       │   ├── Pig3D.tsx                      # โมเดลหมู 3D
│       │   ├── Sheep3D.tsx                    # โมเดลแกะ 3D
│       │   ├── Plot3D.tsx                     # โมเดลแปลงดิน 3D
│       │   ├── CornPlot3D.tsx                 # โมเดลแปลงข้าวโพด 3D
│       │   └── FarmCrops3D.tsx                # โมเดลพืชผล 3D
│       │
│       └── modals/                            # หน้าต่าง Pop-up ทั้งหมด
│           ├── AppModals.tsx                  # เลเยอร์จัดการเรนเดอร์ Modal หลัก
│           ├── AuthModal.tsx                  # 🔐 ระบบสมาชิกเข้าสู่ระบบ Gmail (Google) / Facebook / Guest เซฟแยกบัญชี
│           ├── AiChodChatModal.tsx            # 👨‍🌾 หน้าต่างแชต AI นายชด ปราชญ์ชาวสวน (มีเสียงพูดภาษาไทย)
│           ├── FishingDockModal.tsx           # 🎣 หน้าต่างฉากตกปลา 3D ทะเลสาบมรกต 4K, สมุดพันธุ์ปลา, คราฟต์เหยื่อ
│           ├── AnimalCareModal.tsx            # หน้าต่างให้อาหารและเก็บผลิตผลสัตว์
│           ├── BuildModal.tsx                 # หน้าต่างเลือกสร้างแปลงผัก, คอกสัตว์, ของตกแต่ง
│           ├── CloudSyncModal.tsx             # ระบบ Cloud Save & Sync ย้ายเครื่องและสำรองข้อมูล
│           ├── DailyRewardsModal.tsx          # หน้าต่างเช็คอิน 7 วัน รับเหรียญและเพชร
│           ├── EventsModal.tsx                # เทศกาลเก็บเกี่ยว แลกรางวัล Tier Milestone
│           ├── FriendsModal.tsx               # รายชื่อเพื่อนในเกม ช่วยเหลือฟาร์มเพื่อน
│           ├── GiftBoxModal.tsx               # กล่องของขวัญสุ่มรายชั่วโมง
│           ├── InventoryModal.tsx             # หน้าต่างโรงนา จัดหมวดหมู่ ขายของ และอัปเกรด
│           ├── LevelUpModal.tsx               # ป๊อปอัปเฉลิมฉลองเมื่อเลเวลอัป ปลดล็อกพืชใหม่
│           ├── LogoInfoModal.tsx              # หน้าต่างข้อมูลโปรเจกต์และผู้พัฒนา
│           ├── MailModal.tsx                  # กล่องจดหมายข่าวสารและรับไอเทมของขวัญ
│           ├── MarketModal.tsx                # ตลาดสั่งซื้อสินค้าเมืองบางแคและส่งรถกระบะ
│           ├── ProductionModal.tsx            # แผงควบคุมเตาอบ โรงนม โรงแยม เร่งผลิต/เก็บของ
│           ├── QuestsModal.tsx                # กระดานภารกิจประจำวัน รับเหรียญและ EXP
│           ├── SeedPickerModal.tsx            # หน้าต่างเลือกเมล็ดพันธุ์เมื่อคลิกแปลงเพาะปลูก
│           ├── SettingsModal.tsx              # ปรับระดับเสียง ดนตรี รีเซ็ตข้อมูลเกม
│           ├── ShopModal.tsx                  # ร้านค้าซื้อเมล็ด ปุ๋ย และเพชร
│           ├── VisitFriendModal.tsx           # หน้าต่างจำลองการแวะไปเยี่ยมชมฟาร์มเพื่อน
│           └── WorldMapModal.tsx              # แผนที่โลกและแหล่งท่องเที่ยวรอบเมือง (สลับ Farm 1 / Farm 2)

--------------------------------------------------------------------------------
3. รายละเอียดหน้าที่ของไฟล์ระดับ Root (CONFIGURATIONS & ENTRY POINTS)
--------------------------------------------------------------------------------
- /index.html:
  - กำหนด Viewport ล็อกหน้าจอ `width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no, viewport-fit=cover`
  - ปรับ Apple Mobile Web App & Theme Color สำหรับมือถือ
  - โหลด Google Fonts: 'Kanit' (ภาษาไทย) และ 'Fredoka' (ตัวเลขอังกฤษและปุ่มสไตล์การ์ตูน)
  - Content-Security-Policy (CSP) ป้องกัน XSS
  - CSS Reset ป้องกันขอบขาว จอดิ้น และการ Drag พื้นหลังที่ไม่ต้องการ

- /metadata.json:
  - กำหนดชื่อแอป: "Beam Farm (B.P.)"
  - รายละเอียดแอป: เกมจำลองฟาร์มแสนสุข Beam Farm (B.P.) ปลูกพืช เลี้ยงสัตว์ แปรรูปสินค้า
  - Major Capabilities: MAJOR_CAPABILITY_SERVER_SIDE_GEMINI_API

- /package.json:
  - Dependencies: React 19, React-DOM 19, Three.js, Lucide-React, Motion, Canvas-Confetti, Tailwind CSS v4, Vite 8
  - Scripts: `dev` (port 3000 host 0.0.0.0), `build` (vite build), `lint` (tsc --noEmit)

- /vite.config.ts:
  - กำหนด Alias `@` ชี้มาที่ Root Directory
  - โหลดปลั๊กอิน `@vitejs/plugin-react` และ `@tailwindcss/vite`

--------------------------------------------------------------------------------
4. แกนควบคุมระบบเกมหลัก (CORE GAME CONTROLLER - App.tsx)
--------------------------------------------------------------------------------
ไฟล์ `src/App.tsx` ทำหน้าที่เป็น State Authoritative Hub รวบรวมข้อมูลทั้งหมดและประมวลผล
Gameloop ต่อวินาที:

ตัวแปรสถานะที่จัดการ (Main States):
1. Currencies & Progress:
   - `coins`: จำนวนเหรียญทอง (เริ่มต้น 500)
   - `gems`: จำนวนเพชร (เริ่มต้น 10)
   - `energy` / `maxEnergy`: ค่าพลังงานในการทำกิจกรรม (30/30) พร้อม Timer รีเจนเนอเรชัน 180 วินาที
   - `level` / `xp` / `maxXp`: ระดับเลเวลและประสบการณ์ พร้อมคำนวณ Threshold อัตโนมัติ
   - `farmName`: ชื่อฟาร์มของผู้เล่น (บันทึกใน LocalStorage)
2. Farm Entities:
   - `plots`: อาร์เรย์แปลงเกษตร (สถานะ: รหัสพืช, เวลาเริ่มปลูก, พร้อมเก็บ, การรดน้ำ)
   - `animals`: คอกสัตว์ (ไก่, วัว, แกะ, หมู) พร้อมตัวจับเวลาให้อาหารและสถานะพร้อมเก็บ
   - `factories`: โรงงานแปรรูป (bakery, dairy, jam, windmill) พร้อมคิวและรายการผลิตเสร็จ
   - `inventory`: สต็อกผลผลิตทุกชนิด Typed เป็น `Record<string, InventoryItem>`
   - `barnCapacity`: ความจุโรงนาสูงสุด (เริ่มต้น 30 ขยายได้ด้วยเหรียญ)
3. การคำนวณ Dynamic HUD Offset (`--hud-h`):
   - มี ResizeObserver คอยวัดความสูงจริงของแถบ TopHUD แล้วส่งค่าเข้า CSS Variable `--hud-h`
   - ป้องกันไม่ให้แถบเครื่องมือบนแผนที่ (FarmToolbar) ลอยทับแถบเงินและหลอดเลเวลบนสมาร์ตโฟน
4. Social & Quests & Fishing:
   - `orders`: ออร์เดอร์รถกระบะส่งของ มีการสุ่มเควสต์ตามเลเวลผู้เล่นและร้านอาหารปลา
   - `quests`: ภารกิจประจำวัน (รวมถึงเควสต์ตกปลา `q_fish_1`, `q_fish_2`)
   - `luckyFisherBuff`: บัฟตกปลาโชคดีที่ได้รับจากการป้อนปลาสดให้น้องแมวส้ม
   - `friends`: รายชื่อเพื่อนบ้าน และระบบขอความช่วยเหลือ
   - `dailyRewards`: เช็คอินรับรางวัล 7 วัน
   - `festivalPoints`: คะแนนเทศกาลเก็บเกี่ยว
   - `mails`: กล่องจดหมายพร้อมไอเทมแนบ
5. Game Loops & Effects:
   - `setInterval(..., 1000)`: อัปเดตเวลาการเติบโตของพืช, การให้อาหารสัตว์, การผลิตในโรงงาน
   - `Offline Progress`: คำนวณความคืบหน้าย้อนหลังจากเวลาที่ปิดเกมไป (Last Active Time สูงสุด 12 ชม.)
   - `Sound Management`: เชื่อมต่อกับ `sound` Engine ส่งเสียง SFX และควบคุม BGM
6. AI Chod Integration:
   - `isAiChodOpen`: ควบคุมการเปิด/ปิดหน้าต่างสนทนากับนายชด AI

--------------------------------------------------------------------------------
5. สถาปัตยกรรมแผนที่และระบบจัดวางสิ่งก่อสร้าง (FarmWorld.tsx ENGINE)
--------------------------------------------------------------------------------
`src/components/FarmWorld.tsx` เป็นหัวใจด้านการแสดงผลเชิงภาพและฟิสิกส์การควบคุม:
1. การควบคุมกล้องและมาตราส่วน (Camera Pan & Zoom):
   - Stage Canvas ขนาดฐาน 1440 x 960 พิกเซล
   - คำนวณ `baseScale` อัตโนมัติให้พอดีกับความกว้าง/ความสูงของหน้าจออุปกรณ์ (Fit-contain)
   - ตัวคูณ `userZoom` (1.0x ถึง 2.5x) พร้อมระบบ Pinch / Touch Drag เลื่อนแผนที่ลื่นไหล
2. ระบบแก้ไขตำแหน่งสิ่งก่อสร้าง (Build & Edit Mode):
   - โหมดสลับ `isEditMode`: เปิด/ปิด การคลิกใช้งานสิ่งของ vs การลากย้ายตำแหน่ง
   - ระบบ Snap to Grid 32px: จัดระเบียบสิ่งก่อสร้างลงตามช่องตารางอย่างสวยงาม
   - การหมุน 90 องศา (Rotate): รองรับมุม 0°, 90°, 180°, 270°
   - การพลิกด้านกระจก (Flip Horizontally): สลับซ้าย-ขวา เหมาะสำหรับจัดทางเข้าอาคาร
   - บันทึกการจัดวางลง LocalStorage (`beam_farm_placed_items_v5`) ทันที
3. สระน้ำมรกต (Fishing Pond):
   - คลิกที่สระน้ำมรกตเพื่อเปิดหน้าต่างฉากตกปลา 3D ระดับ 4K
4. ไม้ผล (Fruit Trees):
   - ต้นส้มและแอปเปิล มีระบบคูลดาวน์นับถอยหลัง คลิกเก็บเกี่ยวผลไม้สดได้
5. ระบบกลืนกับพื้นหลังและเงาสัมผัสผืนดินธรรมชาติ (Seamless Terrain Blending & Ground Contact AO):
   - ปลดล็อกปัญหาภาพคัดแปะ (Zero Sticker Cutout Effect)
   - ใช้เงาตกกระทบแบบ Soft Isometric Contact Shadow สีเขียวเข้ม-ดินปนหญ้า (`rgba(18, 38, 12, 0.48)`)
   - Three.js `ShadowMaterial({ opacity: 0.32 })` ไร้ขอบแข็ง แสดงผลทะลุผ่านลวดลายหญ้าอย่างเป็นธรรมชาติ

--------------------------------------------------------------------------------
5.5 สถาปัตยกรรมระบบเคียวเก็บเกี่ยว (HarvestTool & HarvestSystem Swipe Engine)
--------------------------------------------------------------------------------
ระบบเก็บเกี่ยวพืชผลแบบลากกวาดต่อเนื่อง (Continuous Swipe Harvest):
1. `HarvestTool.tsx`:
   - ปุ่มสลับโหมดเคียว "🌾 เลือกเคียว" / "🌾 กำลังถือเคียว"
   - เมื่อเปิดใช้งาน ตัวเคียว 3D ขนาดใหญ่และประกายดาวจะถูกเรนเดอร์ผ่าน `createPortal` ไปที่ `document.body` โดยตรง เพื่อไม่ให้ถูกตัดขอบตาม Parent Container
   - มีฟิสิกส์การฟันกวาด (Swinging Rotation) เมื่อกดลากผ่านหน้าจอ
2. `HarvestSystem.ts`:
   - บริหารจัดการเซ็ต `harvestedThisSwipe: Set<number>` ป้องกันการเก็บเกี่ยวแปลงเดิมซ้ำในการปัดรอบเดียว
   - ตรวจสอบการสัมผัส (Collision Detection) ด้วย `document.elementFromPoint(x, y)` ค้นหา Attribute `data-plot-id`
   - เมื่อโดนแปลงที่สุกพร้อมเก็บ จะเรียกเสียง `sound.playHarvest()`, ทริกเกอร์ `onHarvestPlot()` และปล่อยเอฟเฟกต์ตัวเลขลอยทันที
3. การตัดการแย่งชิง Gesture (Gesture Isolation):
   - เมื่อกำลังถือเคียว ระบบจะระงับการเลื่อนแผนที่ (Map Pan) ชั่วคราว เพื่อให้ผู้เล่นสามารถใช้นิ้วลากตัดรวงข้าวได้อย่างอิสระโดยที่แผนที่ไม่เลื่อนตาม

--------------------------------------------------------------------------------
5.6 การแก้ปัญหา UI ซ้อนทับและการรวมแถบควบคุม (extraAction Toolbar Integration)
--------------------------------------------------------------------------------
ปัญหาเดิม:
- ปุ่มเคียว (`HarvestTool`) เคยถูกวางเป็นกล่องอิสระที่พิกัด `top-20 right-4` ซึ่งเป็นพิกัดเดียวกับแถบควบคุมฟาร์ม (`FarmControls`) ทำให้ปุ่ม "เลือกเคียว", "สิ่งก่อสร้าง" และ "จัดวางฟาร์ม" ทับซ้อนกัน โดยเฉพาะบนหน้าจอมือถือ

แนวทางแก้ไขเชิงสถาปัตยกรรม:
1. ปรับปรุง `FarmControls.tsx`:
   - เพิ่ม Prop เสริม `extraAction?: React.ReactNode` ใน `FarmControlsProps`
   - นำ `extraAction` มารวมไว้ในคอนเทนเนอร์เดียวกัน (`.farm-toolbar-top`)
   - เพิ่มคลาส `flex items-center justify-end flex-wrap gap-2` เพื่อให้ปุ่มตัดขึ้นบรรทัดใหม่อัตโนมัติเมื่อจอแคบ
2. ปรับปรุง `FarmWorld.tsx`:
   - ส่งคอมโพเนนต์ `<HarvestTool />` ผ่าน Prop `extraAction` ของ `FarmControls`
   - ลบคอนเทนเนอร์ลอยตำแหน่งเดิม (`absolute top-20 right-4 z-40`) ออกทั้งหมด
3. ผลลัพธ์:
   - นอกโหมดจัดวาง: ปุ่มเรียงลำดับอย่างเป็นระเบียบ: `🌾 เลือกเคียว` → `🏗️ สิ่งก่อสร้าง` → `จัดวางฟาร์ม`
   - ในโหมดจัดวาง: ปุ่มเคียวจะซ่อนตัวอัตโนมัติ และแสดงปุ่ม `จัดผังอัตโนมัติ` และ `Snap กริด` ขึ้นมาแทนอย่างสมบูรณ์

--------------------------------------------------------------------------------
5.7 สถาปัตยกรรมสลับฟาร์มคู่แบบไร้รอยต่อ (Dual Farm Architecture: Farm 1 & Farm 2)
--------------------------------------------------------------------------------
ระบบรองรับการสลับแผนที่ฟาร์มขนาดใหญ่ 2 แบบผ่าน `WorldMapModal`:
1. **Farm 1: ฟาร์มหลักริมสายน้ำ (Riverside Farm)**
   - ใช้ภาพพื้นหลัง `farm_bg.jpg`
   - ผังเริ่มต้น `LAYOUT_FARM_1`: สิ่งก่อสร้างกระจายรอบแม่น้ำและสระมรกต
2. **Farm 2: อาณาเขตฟาร์มเกาะมรกต (Emerald Island Farm)**
   - ใช้ภาพพื้นหลัง `farm2_bg.jpg`
   - ผังเริ่มต้น `LAYOUT_FARM_2`: จัดวางสิ่งก่อสร้างเข้ากับร่องดินธรรมชาติ ทุ่งหญ้า และน้ำตกอย่างพอดี
3. กลไกการสลับทันทีโดยไม่ต้องโหลดหน้าเว็บใหม่ (`switchFarmMap` ใน `worldMapData.ts`):
   - บันทึก ID ฟาร์มปัจจุบันลง LocalStorage (`ACTIVE_FARM_STORAGE_KEY`)
   - ค้นหาและเปลี่ยน `src` ของแท็ก `<img>` และ `style.backgroundImage` บน DOM ทันที
   - อัปเดตสถานะป้าย "คุณอยู่ที่นี่" ในแผนที่โลก และปิดหน้าต่างแผนที่โดยอัตโนมัติ

--------------------------------------------------------------------------------
6. สถาปัตยกรรมระบบทะเลสาบมรกตและมินิเกมตกปลา 3D (FISHING SYSTEM & LAKE ECOSYSTEM)
--------------------------------------------------------------------------------
`FishingDockModal.tsx` & `EmeraldLake3D.tsx` มอบประสบการณ์ตกปลา 3D เสมือนจริง:
1. การเรนเดอร์ฉาก 3 มิติ (EmeraldLake3D):
   - ทะเลสาบมรกต PBR วัสดุ Transmission โปร่งแสงมองเห็นฝูงปลาแหวกว่ายใต้น้ำ
   - สะพานไม้เทียบเรือ (Wooden Dock) พร้อมโคมไฟไม้ญี่ปุ่นริมน้ำ
   - ใบบัวและดอกบัวหลวงลอยน้ำ 3D
   - ระบบจำลองบรรยากาศตามเวลา: กลางวัน (แดดอุ่น) / ยามเย็น (แสงส้มอำพัน) / กลางคืน (แสงจันทร์สีคราม + หิ่งห้อย 3D บินวนรอบสระ)
2. วงจรการตกปลา (Fishing State Machine):
   - `idle` → `casting` (เหวี่ยงเบ็ด) → `waiting` (ทุ่นลอยน้ำนิ่ง) → `nibbling` (ปลาตอดเหยื่อ) → `hooked` (ปลากินเบ็ดเต็มตัว กดตวัด) → `reeling` (มินิเกมประคองสายเบ็ด) → `caught` / `escaped`
3. มินิเกมประคองสายเบ็ด (Tension Gauge Minigame):
   - ผู้เล่นต้องกดค้างเพื่อหมุนรอก ดึงแถบสีเขียวให้อยู่ตรงกับตำแหน่งของตัวปลาที่ดิ้นไปมา
   - หากประคองได้แถบความตึงจะเพิ่มขึ้นจนครบ 100% จึงจับปลาสำเร็จ
4. สมุดบันทึกพันธุ์ปลา (Fish Encyclopedia) & ฉายายอดนักตกปลา:
   - บันทึกสถิติน้ำหนักตัวใหญ่ที่สุด (Personal Best - PB) และจำนวนที่เคยจับ
   - หากจับครบทั้ง 4 ชนิด (ปลาคาร์ปมรกต, ปลากะพงลายเสือ, ปลาเทราต์สายรุ้ง, ปลาดุกทองคำโบราณ) จะปลดล็อกฉายา "ยอดนักตกปลามือทอง" พร้อมรับ 5,000🪙 และ 25💎
5. กล่องผสมเหยื่อตกปลา (Bait Crafting Box):
   - คราฟต์เหยื่อจากผลผลิตในฟาร์ม:
     - เหยื่อแป้งสาลี (ข้าวสาลี x2): ปลากินเบ็ดไวขึ้น 30%
     - เหยื่อข้าวโพดหวาน (ข้าวโพด x2): เพิ่มโอกาสเจอปลาเทราต์สายรุ้ง +40%
     - เหยื่อประกายทอง (ขนมปัง x1, เนย x1): เพิ่มโอกาสเจอปลาดุกทองคำโบราณ 25%
6. น้องแมวส้มริมบ่อปลา (Pond Guardian Cat):
   - น้องแมวนั่งริมสะพานไม้ สามารถนำปลาสดที่ตกได้มาป้อนให้น้องแมวเพื่อรับเหรียญ, เพชร, EXP และบัฟ "แมวนำโชค" (Lucky Fisher Buff) 5 ครั้ง

--------------------------------------------------------------------------------
7. ระบบ AI นายชด ปราชญ์ชาวสวน พร้อมเสียงสังเคราะห์ภาษาไทย (AI CHOD ENGINE)
--------------------------------------------------------------------------------
ระบบผู้ช่วยอัจฉริยะประจำฟาร์ม "นายชด" ผสาน AI Context Analysis และ Web Speech API:
1. การเข้าถึง (Entry Point):
   - ปุ่มลอยรูปนายชด 👨‍🌾 ประจำอยู่ที่มุมซ้ายล่างเหนือ BottomDock
   - มีไฟสถานะสีเขียวแสดงความพร้อมสนทนา และข้อความ "มีเสียงพูด • ปรึกษาฟาร์ม"
2. สถาปัตยกรรมเสียงพูดภาษาไทย (TTS Engine - utils/aiSpeech.ts):
   - คลาส `NaiChodVoiceEngine` ดึงเสียง `th-TH` จากเบราว์เซอร์อัตโนมัติ
   - กรองสัญลักษณ์และอีโมจิออกก่อนส่งเข้า SpeechSynthesisUtterance เพื่อให้การออกเสียงลื่นไหล
   - ปรับแต่งโทนเสียงนายชด: ทุ้ม อบอุ่น มีจังหวะแบบผู้เฒ่าใจดี (`pitch: 0.88`, `rate: 0.95`, `volume: 1.0`)
   - ปุ่มสลับเปิด/ปิดเสียงพูด (`Volume2` / `VolumeX`) บันทึกสถานะ Mute ทันที
3. สมองกลวิเคราะห์ฟาร์ม (Brain Engine - utils/aiChodBrain.ts):
   - ฟังก์ชัน `askNaiChod(query, farmContext)` ประมวลผลจากข้อมูลจริงของผู้เล่น (Realtime Context):
     - **ตรวจสภาพฟาร์ม**: ตรวจนับแปลงที่พร้อมเก็บ, แปลงที่ลืมรดน้ำ, สัตว์ที่หิว, สินค้าที่ผลิตเสร็จ, และ % ความจุโรงนา
     - **แนะนำการปลูก**: วิเคราะห์ตามเลเวลผู้เล่น (Lv.1-2 แนะนำข้าวสาลี, Lv.3-5 แนะนำข้าวโพด, Lv.6-9 แนะนำมะเขือเทศ, Lv.10+ แนะนำลาเวนเดอร์และสตรอว์เบอร์รี่)
     - **โรงนาและคลัง**: แจ้งจำนวนไอเทมคงเหลือและอัตราความจุ พร้อมแนะนำวิธีระบายสินค้า
     - **สัตว์เลี้ยง**: แนะนำชนิดอาหารของสัตว์แต่ละประเภท
     - **ออร์เดอร์รถกระบะ**: แจ้งจำนวนออร์เดอร์ที่รอจัดส่งและวิธีเก็บ EXP ให้ไวที่สุด
     - **พลังงาน**: แจ้งจำนวนพลังงานปัจจุบันและเวลาฟื้นฟู
4. หน้าต่างแชท (Modal View - components/modals/AiChodChatModal.tsx):
   - กรอบไม้สไตล์คันทรี่ พร้อม Avatar นายชดแสดงแอนิเมชันวงแหวนเปล่งประกายและตัวโน้ตดนตรีขณะกำลังพูด
   - แถบปุ่มคำถามลัด (Quick Prompts): ตรวจสภาพฟาร์ม, ปลูกอะไรกำไรดี, คลังโรงนา, เลี้ยงสัตว์

--------------------------------------------------------------------------------
8. สถาปัตยกรรมการแยกโค้ดแบบโมดูลาร์ (MODULAR ARCHITECTURE REFACTORING)
--------------------------------------------------------------------------------
เพื่อรองรับการบำรุงรักษาในระยะยาว ได้ทำการแยกโค้ด (Decomposition) ออกจาก Monolithic Files:
1. การแยก FarmWorld.tsx:
   - สกัด `BakeryOven3D.tsx`, `DraggableCorn3D.tsx`, `EmeraldLake3D.tsx`, `FarmCharacters3D.tsx` สู่โฟลเดอร์ `src/components/3d/`
   - สกัด `FarmControls.tsx`, `BuildableCatalogModal.tsx`, `EntityToolbar.tsx`, `HarvestTool.tsx`, `HarvestSystem.ts` สู่โฟลเดอร์ `src/components/farm/`
   - สกัดข้อมูลคงที่ ผังเริ่มต้น และแคตตาล็อกสู่ `src/data/farmWorldData.ts`
2. การแยก App.tsx:
   - สกัดการเรนเดอร์หน้าต่างป๊อปอัปทั้งหมดสู่ `src/components/modals/AppModals.tsx`
   - สกัดข้อมูลแม่แบบสัตว์และเลเวลปลดล็อกสู่ `src/data/gameConstants.ts`
   - สกัดฟังก์ชันคำนวณออร์เดอร์สู่ `src/utils/orderGenerator.ts`
   - สกัดระบบล็อกอินและบัญชีสู่ `src/utils/auth.ts`
   - สกัดการแจ้งเตือน Floating Toast สู่ `src/components/common/Toast.tsx`

--------------------------------------------------------------------------------
9. แผงควบคุมและส่วนติดต่อผู้ใช้หลัก (HUD & DOCK INTERFACES)
--------------------------------------------------------------------------------
- LoadingScreen.tsx:
  - โหลดภาพอาร์ตเวิร์ก Beam Farm (B.P.) เต็มหน้าจอ
  - หลอด Progress Bar 3D สีทอง พร้อมเอฟเฟกต์ Shimmer แสงสะท้อน
  - กรงเล็บสายฟ้า 3D (3D Lightning Claws Overlay) โอบรอบเหรียญทานตะวัน B.P.
  - ข้อความแสดงขั้นตอนเตรียมระบบตามจริง และระบบเสียง Web Audio API
- TopHUD.tsx:
  - แสดง Avatar ชาวสวน, ชื่อฟาร์ม, เลเวล, EXP, เหรียญ, เพชร, พลังงาน
  - ปุ่มล็อกอิน Gmail / Facebook, Cloud Sync, ปุ่มเปิด/ปิดเสียง SFX และ BGM
- BottomDock.tsx:
  - แถบเมนูด้านล่างสไตล์ไม้ธรรมชาติ: แผนที่, โรงนา, ก่อสร้าง, สัตว์เลี้ยง, โรงงาน, ตลาด, เพื่อน, ข้อมูลเกม
  - แถบ Live Logs แสดงความคืบหน้าแบบ Realtime
- LeftMenu.tsx & RightMenu.tsx:
  - เมนูปุ่มลอยแนวตั้งซ้าย-ขวา สามารถกดพับเก็บ (Collapse) ได้บนหน้าจอมือถือเพื่อเพิ่มพื้นที่มองเห็น

--------------------------------------------------------------------------------
9.1 โปรไฟล์ปรับแต่งขนาดหน้าจอมือถือ (Mobile Profile: Vivo Y17 & Compact Viewports)
--------------------------------------------------------------------------------
ใน `src/index.css` (Section 8) ได้บรรจุ CSS Rules พิเศษสำหรับสมาร์ตโฟนที่มีหน้าจอแคบหรือยาว (เช่น Vivo Y17 ขนาด ~360x760 px):
1. โหมดแนวตั้ง (Portrait <= 480px):
   - แถบเหรียญ/เพชร/พลังงานเลื่อนข้างได้แบบแนวนอน (`overflow-x: auto; touch-action: pan-x`)
   - แถบเครื่องมือจัดวาง (`.farm-toolbar-top`) ปรับตำแหน่งอยู่ใต้ TopHUD โดยอิงตัวแปร `var(--hud-h)`
   - ซ่อน Label ตัวหนังสือขนาดยาวบนปุ่มเสริม (`.tb-label { display: none; }`) เพื่อไม่ให้ปุ่มล้นขอบจอ
   - ปุ่ม Dock ด้านล่าง 7 ปุ่มแบ่งสัดส่วนกว้างเท่ากัน (`flex: 1 1 0`) พอดีความกว้างหน้าจอ 360px โดยไม่ต้องเลื่อน
2. โหมดแนวนอน (Landscape Height <= 480px):
   - ย่ออัตราส่วน HUD ลงเหลือ Zoom 82-85% เพื่อประหยัดพื้นที่แนวตั้ง
   - ปุ่มลอยนายชด AI ย้ายไปแนบชิดมุมซ้ายล่าง ไม่กินพื้นที่ความสูงของหน้าจอ
   - ปรับปุ่มซูมมุมขวาล่างเป็นแบบตาราง 2 คอลัมน์ 3 แถว ประหยัดพื้นที่ความสูง

--------------------------------------------------------------------------------
10. รายละเอียดหน้าต่างป๊อปอัปทั้งหมด (MODALS IN-DEPTH SPECIFICATION)
--------------------------------------------------------------------------------
1. AppModals.tsx: เลเยอร์รวบรวมและเชื่อมต่อ Event Handlers ของ Modal ทุกตัว
2. AiChodChatModal.tsx: แชต AI นายชด ปราชญ์ชาวสวน พร้อมระบบเสียงพูดภาษาไทย
3. FishingDockModal.tsx: ฉากตกปลา 3D ทะเลสาบมรกต 4K, สมุดพันธุ์ปลา, กล่องผสมเหยื่อ
4. AuthModal.tsx: ระบบสมาชิกเข้าสู่ระบบ Gmail (Google) / Facebook / Guest เซฟแยกบัญชี
5. SeedPickerModal.tsx: ป๊อปอัปเลือกเมล็ดพันธุ์เมื่อคลิกที่แปลงเกษตรว่าง
6. InventoryModal.tsx: ตรวจสอบสินค้าในโรงนา ขายสินค้าเดี่ยว/จำนวนมาก และอัปเกรดความจุ
7. ProductionModal.tsx: ควบคุมการผลิตของเตาอบ โรงนม โรงแยม และกังหันลม
8. AnimalCareModal.tsx: ดูแลสัตว์เลี้ยง ให้อาหาร และเก็บผลผลิต
9. BuildModal.tsx: เมนูก่อสร้างแปลงเกษตรใหม่ คอกสัตว์ และของประดับ
10. MarketModal.tsx: กระดานออร์เดอร์ส่งของชุมชนบางแคและส่งรถกระบะ
11. QuestsModal.tsx: รายการภารกิจ 5 ประการ พร้อมรับเหรียญและ EXP
12. EventsModal.tsx: กิจกรรมเทศกาลเก็บเกี่ยวสะสมแต้ม Harvest Points
13. DailyRewardsModal.tsx: ปฏิทินเช็คอิน 7 วัน รับเหรียญและเพชร
14. FriendsModal.tsx & VisitFriendModal.tsx: เพื่อนบ้านจำลองและแวะไปเยี่ยมชมฟาร์ม
15. ShopModal.tsx: ร้านค้าจัดซื้อเมล็ดพันธุ์จำนวนมาก และแลกซื้อเพชร/พลังงาน
16. MailModal.tsx: กล่องข้อความทางการจากผู้ช่วยนายกเทศมนตรีและเพื่อนบ้าน
17. GiftBoxModal.tsx: กล่องของขวัญสุ่ม เปิดรับไอเทมฟรีทุก 30 นาที
18. LevelUpModal.tsx: ป๊อปอัปเฉลิมฉลองเมื่อเลเวลอัป พร้อม Confetti
19. SettingsModal.tsx: ปรับระดับเสียง ดนตรี รีเซ็ตข้อมูลฟาร์ม และเปิด Cloud Sync
20. CloudSyncModal.tsx: ระบบ Cloud Save, รหัสย้ายเครื่อง, สำรองไฟล์ .beamfarm
21. LogoInfoModal.tsx: ข้อมูลลิขสิทธิ์และเรื่องราวของฟาร์ม Beam Farm (B.P.)
22. WorldMapModal.tsx: แผนที่โลกและคำสั่งสลับฟาร์มแบบไร้รอยต่อ (Farm 1 / Farm 2)

--------------------------------------------------------------------------------
11. โครงสร้างประเภทข้อมูล (TYPES & DATA SCHEMAS)
--------------------------------------------------------------------------------
รายการ Interface หลักที่ขับเคลื่อน TypeScript ในโปรเจกต์:
- `UserProfile`: id, email, displayName, photoURL, provider ('google' | 'facebook' | 'guest'), createdAt, lastLoginAt, token
- `CropType`: id, name, thaiName, icon, growTimeSec, cost, sellPrice, xpReward, minLevel
- `Plot`: id, cropId, plantedAt, isReady, watered
- `AnimalPen`: id, type, name, thaiName, icon, count, maxCount, fedAt, durationSec, produceItem, produceName, produceIcon, produceQuantity, feedCropId, feedRequired, isReady
- `Recipe`: id, name, thaiName, icon, durationSec, ingredients, outputCount, xpReward, sellPrice, minLevel
- `Factory`: id, name, thaiName, icon, level, currentProduction, queue, completedItems
- `InventoryItem`: id, name, thaiName, category, count, icon, sellPrice
- `Order`: id, customerName, customerAvatar, items, rewardCoins, rewardXp, expiresInSec, status
- `Quest`: id, title, thaiTitle, description, type, targetType, current, target, rewardCoins, rewardXp, rewardGems, completed, claimed
- `FishSpecies`: id, name, thaiName, icon, rarity, minWeightKg, maxWeightKg, sellPrice, xpReward, description, shadowSpeed
- `ChatMessage`: id, sender ('user' | 'chod'), text, timestamp

--------------------------------------------------------------------------------
12. คลังข้อมูลและค่าคงที่ (DATA & CONSTANTS - data/)
--------------------------------------------------------------------------------
1. `src/data/initialData.ts`: แคตตาล็อกพืช CROPS, สูตรอาหาร RECIPES, รายการสัตว์เริ่มต้น, เควสต์, รางวัลเช็คอิน
2. `src/data/farmWorldData.ts`: ขนาดเวที 1440x960, กริด 32px, ผังเริ่มต้น LAYOUT_FARM_1 และ LAYOUT_FARM_2
3. `src/data/gameConstants.ts`: STORAGE_KEY v6, เลเวลปลดล็อกพืช, แม่แบบสัตว์, GameSnapshot
4. `src/data/fishingData.ts`: LAKE_FISH_CATALOG ข้อมูลปลา 4 ชนิด และอัลกอริทึมสุ่ม rollRandomFish()
5. `src/data/worldMapData.ts`: รายชื่อเมือง WORLD_ZONES และฟังก์ชัน switchFarmMap()

--------------------------------------------------------------------------------
13. ระบบเสียงสังเคราะห์และพื้นผิว PBR (AUDIO & PBR UTILITIES - utils/)
--------------------------------------------------------------------------------
1. `src/utils/audio.ts`: SoundEngine พัฒนาด้วย Web Audio API ทำงานแบบ Offline 100% มี Master Compressor ป้องกันเสียงแตก
   - SFX: playClick, playHarvest, playWater, playPlant, playSuccessChime, playCoin, playLevelUp, playTruckHorn, playAnimal
   - BGM: startBGM, stopBGM, startCountryTune
2. `src/utils/aiSpeech.ts`: NaiChodVoiceEngine สังเคราะห์เสียงพูดภาษาไทยผ่าน SpeechSynthesis API
3. `src/utils/aiChodBrain.ts`: สมองกลวิเคราะห์ฟาร์ม ตอบคำถามการเกษตรตามสถานการณ์จริง
4. `src/utils/orderGenerator.ts`: ฟังก์ชันสุ่มและคำนวณเควสต์ออร์เดอร์รถกระบะตามเลเวล
5. `src/utils/threeTextures.ts`: เอนจินสร้าง Procedural PBR Textures ความละเอียดสูง (ขนไก่, ขนวัว, ดิน, ไม้, อิฐ, ผ้าเดนิม)

--------------------------------------------------------------------------------
14. สไตล์ ดีไซน์ซิสเต็ม และแอนิเมชัน (STYLING & CSS - index.css)
--------------------------------------------------------------------------------
Custom Utility Classes ที่สร้างสรรค์ขึ้นสำหรับเกม:
- `.game-wood-board`, `.game-wood-panel`: พื้นหลังลายแผ่นไม้ธรรมชาติสีน้ำตาลอบอุ่น พร้อมขอบนูน 3D
- `.game-btn-green`, `.game-btn-yellow`, `.game-btn-blue`: ปุ่มกดมีมิติสไตล์การ์ตูน พร้อม Spring Feedback (`active:scale-95`)
- `.game-scroll`: Custom Scrollbar สไตล์ไม้โทนทองแดง เรียบเนียน ไม่บดบังเนื้อหา
- Keyframes แอนิเมชัน: `gentle-bounce`, `gentle-pulse`, `float-pop`, `gentle-breathe`, `tree-sway`

--------------------------------------------------------------------------------
15. ทรัพยากรภาพและสินทรัพย์ (ASSETS & GRAPHICS - public/)
--------------------------------------------------------------------------------
1. `public/farm_bg.jpg`: แผนที่ทุ่งหญ้าฟาร์มหลักริมสายน้ำ
2. `public/farm2_bg.jpg`: แผนที่อาณาเขตฟาร์มเกาะมรกต
3. `public/loading_screen.jpg` & `public/logo_bp.png`: อาร์ตเวิร์กหน้าจอเริ่มเกมและตราสัญลักษณ์เหรียญทอง
4. `public/buildings/*`: รูปภาพสิ่งก่อสร้างและแปลงพืชแบบ Transparent PNG

--------------------------------------------------------------------------------
16. ระบบและตรรกะเกมเพลย์หลัก (GAMEPLAY MECHANICS & FORMULAS)
--------------------------------------------------------------------------------
1. การคำนวณ EXP และ Level Up:
   - Max XP ต่อเลเวลคำนวณตามสูตร: `Math.round(100 * Math.pow(1.35, level - 1))`
   - เมื่อ XP สะสมถึงเกณฑ์ จะทริกเกอร์ `LevelUpModal` พร้อมมอบรางวัลเหรียญ/เพชร และฟื้นฟูพลังงานเต็มหลอด
2. การฟื้นฟูพลังงาน (Energy Regeneration):
   - รีเจนเนอเรต +1 ⚡ ทุกๆ 180 วินาที (3 นาที) จนถึง `maxEnergy`
3. ความจุโรงนา (Barn Storage Limit):
   - ระบบเช็ก `totalInventoryCount + incomingItems <= barnCapacity` ป้องกันไอเทมสูญหาย
4. การบันทึกข้อมูลถาวร (Save System):
   - บันทึกข้อมูลแยกตาม ID บัญชีผู้เล่น (`beam_farm_save_data_v6_${userId}`) หรือค่าเริ่มต้นสำหรับ Guest
   - การจัดวางสิ่งของบนแผนที่บันทึกภายใต้ Key: `beam_farm_placed_items_v5`

--------------------------------------------------------------------------------
17. คู่มือการติดตั้ง คำสั่งคอมไพล์ และการแก้ปัญหา (SCRIPTS & TROUBLESHOOTING)
--------------------------------------------------------------------------------
คำสั่งหลักในโปรเจกต์:
- ติดตั้งไลบรารี: `npm install` (จำเป็นเฉพาะเมื่อยังไม่มีโฟลเดอร์ `node_modules`)
- รัน Development Server: `npm run dev` (เข้าใช้งานผ่านพอร์ต 3000)
- ตรวจสอบ Type และไวยากรณ์: `npm run lint` (tsc --noEmit)
- บิลด์โปรเจกต์สำหรับ Production: `npm run build`

แนวทางแก้ไขปัญหาทั่วไป:
1. การแก้ปัญหาปุ่มซ้อนทับ: ปุ่มเคียวถูกรวมเข้ากับ `FarmControls` ผ่าน `extraAction` เรียบร้อยแล้ว หากพบอาการข้อความล้น ให้ตรวจสอบว่าคลาส `.farm-toolbar-top` มี `flex-wrap: wrap` ครบถ้วน
2. หากไม่มีโฟลเดอร์ `node_modules`: ให้รัน `npm install` ก่อนรัน `npm run dev`
3. หากแก้ไขเฉพาะไฟล์ `.tsx` และมี `node_modules` อยู่แล้ว: ไม่ต้องรัน `npm install` ใหม่ สามารถรัน `npm run dev` ได้ทันที

================================================================================
     🔐 ระบบรักษาความปลอดภัย (SECURITY SYSTEM) - BEAM FARM (B.P.) v6.1+ 🔐
================================================================================
18. ภาพรวมสถาปัตยกรรมความปลอดภัย (SECURITY ARCHITECTURE OVERVIEW)
ระบบแบ่งเป็น 7 เลเยอร์ป้องกัน (Defense-in-Depth):
| เลเยอร์ | ชื่อ | หน้าที่ |
|---------|------|---------|
| L1 | Input Sanitization | กรองข้อความ, ชื่อฟาร์ม, แชต AI ก่อนนำไปใช้ |
| L2 | Data Integrity | ตรวจ Checksum/HMAC ก่อนโหลด |
| L3 | Save Encryption | เข้ารหัส Save Data ด้วย AES-GCM (Web Crypto) |
| L4 | Anti-Cheat Guard | ตรวจเวลา, เหรียญ, XP, ไอเทมผิดปกติ |
| L5 | Rate Limiter | จำกัดการเรียก AI / TTS / Cloud Sync / SFX |
| L6 | Network & CSP | Content-Security-Policy, Same-Origin, Env Vars |
| L7 | Recovery & Backup | Auto-backup, Rollback Save, Integrity Log |

19. โครงสร้างไฟล์ความปลอดภัย (SECURITY MODULE DIRECTORY)
src/security/
├── index.ts, crypto.ts, integrity.ts, sanitizer.ts, rateLimiter.ts
├── antiCheat.ts, secureStorage.ts, timeGuard.ts, securityLog.ts

20. รายละเอียดโมดูลความปลอดภัยเชิงลึก (SECURITY MODULES IN-DEPTH)
- crypto.ts: AES-GCM 256-bit + PBKDF2 100,000 รอบ สุ่ม IV 12 bytes ผูก Device Key
- integrity.ts: SHA-256 Checksum และ HMAC-SHA256 ลงนามข้อมูลป้องกันการปลอมแปลง
- sanitizer.ts: กรอง HTML Escape, ตัด Zero-Width และดักจับ Prompt Injection
- rateLimiter.ts: Token Bucket (AI Chat 10/3s, TTS 6/2s, Cloud Sync 3/60s, SFX 30/1s)
- antiCheat.ts: Clamp ทรัพยากรให้อยู่ในขอบเขตที่ถูกต้อง และจำกัด Offline Progress สูงสุด 12 ชม.
- timeGuard.ts: MonotonicClock อิง `performance.now()` ป้องกันการหมุนนาฬิกาเครื่อง
- secureStorage.ts: จัดเก็บ Envelope เข้ารหัสพร้อมระบบ Rolling Auto-Backup 3 ชุด กู้คืนอัตโนมัติ

21. การป้องกัน AI Prompt Injection (AI CHOD SECURITY)
- ดักจับ Pattern เช่น `ignore all previous`, `system:`, `jailbreak`, `{{...}}`, `<script>`
- ส่งคำตอบ Fallback ปลอดภัยเมื่อตรวจพบคำสั่งแทรกแซง

22. สถาปัตยกรรมความปลอดภัยเครือข่าย & CSP
- กำหนด CSP ใน `index.html` ป้องกันการเชื่อมต่อสคริปต์ภายนอกที่ไม่ได้รับอนุญาต

23. แผนการกู้คืนข้อมูลและการตรวจสอบ (RECOVERY & AUDIT LOG)
- บันทึกประวัติเหตุการณ์ความปลอดภัยสูงสุด 200 รายการ สามารถตรวจสอบได้ในหน้าต่าง Settings

24. สรุปความพร้อมและสถานะการตรวจสอบความปลอดภัย
[x] L1: Input Sanitization 100%
[x] L2: Data Integrity (SHA-256 / HMAC) 100%
[x] L3: Save Encryption (AES-GCM 256-bit) 100%
[x] L4: Anti-Cheat Guard 100%
[x] L5: Token Bucket Rate Limiter 100%
[x] L6: Content-Security-Policy 100%
[x] L7: Rolling Auto-Backup 3 ชุด & Audit Log 100%

================================================================================
จบเอกสารสถาปัตยกรรมระบบ BEAM FARM (B.P.) v6.2 - โครงสร้างและระบบความปลอดภัยสมบูรณ์ครบถ้วน 🌾🔐
================================================================================