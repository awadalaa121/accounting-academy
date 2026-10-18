<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>الأكاديمية المحاسبية المتقدمة | نظام آمن ومحمي</title>
    <link href="https://fonts.googleapis.com/css2?family=Tajawal:wght@400;500;700;800&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary: #0f172a;
            --secondary: #1e293b;
            --accent: #0284c7;
            --accent-light: #e0f2fe;
            --odoo-color: #714B67;
            --odoo-light: #f3ecf1;
            --success: #16a34a;
            --danger: #dc2626;
            --bg: #f8fafc;
            --text: #334155;
            --white: #ffffff;
            --border: #e2e8f0;
        }

        * { box-sizing: border-box; margin: 0; padding: 0; font-family: 'Tajawal', sans-serif; }
        body { background-color: var(--bg); color: var(--text); line-height: 1.8; }

        header { background-color: var(--primary); color: var(--white); position: sticky; top: 0; z-index: 1000; box-shadow: 0 4px 6px rgba(0,0,0,0.1); }
        .nav-container { max-width: 1300px; margin: 0 auto; padding: 0.8rem 1rem; display: flex; justify-content: space-between; align-items: center; }
        .logo { font-size: 1.2rem; font-weight: 800; color: var(--white); text-decoration: none; cursor: pointer; display: flex; align-items: center; gap: 0.4rem; }
        .logo span { color: #38bdf8; }

        .nav-links { display: flex; gap: 0.4rem; list-style: none; align-items: center; flex-wrap: wrap; }
        .nav-links button { background: none; border: none; color: #cbd5e1; font-weight: 600; font-size: 0.9rem; cursor: pointer; padding: 0.4rem 0.6rem; border-radius: 6px; transition: 0.3s; white-space: nowrap; }
        .nav-links button:hover, .nav-links button.active-nav { color: #38bdf8; background: rgba(255,255,255,0.08); }

        .auth-btn { background-color: var(--accent) !important; color: var(--white) !important; padding: 0.4rem 0.9rem !important; border-radius: 6px; }
        .owner-btn { background-color: #714B67 !important; color: var(--white) !important; display: none; }

        .page-view { display: none; }
        .page-view.active-page { display: block; animation: fadeIn 0.3s ease-in-out; }
        @keyframes fadeIn { from { opacity: 0; transform: translateY(4px); } to { opacity: 1; transform: translateY(0); } }

        .hero { background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%); color: var(--white); padding: 4.5rem 1.5rem; text-align: center; }
        .hero h1 { font-size: 2.3rem; margin-bottom: 1rem; font-weight: 800; }
        .hero p { font-size: 1.1rem; max-width: 750px; margin: 0 auto 2rem; color: #cbd5e1; }

        .btn { display: inline-block; background-color: var(--accent); color: var(--white); padding: 0.8rem 1.8rem; border-radius: 8px; text-decoration: none; font-weight: 700; border: none; cursor: pointer; font-size: 1rem; transition: 0.2s; }
        .btn:hover { background-color: #0369a1; }
        .btn-danger { background-color: var(--danger); }
        .btn-danger:hover { background-color: #b91c1c; }

        .container { max-width: 1200px; margin: 0 auto; padding: 3rem 1.5rem; }
        .card { background: var(--white); border-radius: 12px; padding: 2rem; box-shadow: 0 4px 6px rgba(0,0,0,0.05); border: 1px solid var(--border); margin-bottom: 1.5rem; }
        .card h3 { color: var(--primary); margin-bottom: 1rem; font-size: 1.3rem; }

        .entry-table { width: 100%; border-collapse: collapse; margin-top: 1rem; background: var(--white); border-radius: 8px; overflow: hidden; border: 1px solid var(--border); }
        .entry-table th { background-color: var(--secondary); color: var(--white); padding: 0.9rem; text-align: right; font-size: 0.95rem; }
        .entry-table td { padding: 0.9rem; border-bottom: 1px solid var(--border); font-size: 0.95rem; }
        .debit-val { color: #0284c7; font-weight: 700; }
        .credit-val { color: #16a34a; font-weight: 700; }
        .entry-desc { color: #475569; background-color: #f1f5f9; font-weight: 500; }

        .tabs { display: flex; gap: 0.5rem; margin-bottom: 1.5rem; flex-wrap: wrap; }
        .tab-btn { padding: 0.7rem 1.2rem; background: var(--white); border: 1px solid var(--border); border-radius: 8px; cursor: pointer; font-weight: 700; color: var(--text); transition: all 0.2s; }
        .tab-btn.active { background: var(--accent); color: var(--white); border-color: var(--accent); }
        .tab-content { display: none; }
        .tab-content.active { display: block; }

        .generator-wrapper { background: var(--white); border-radius: 16px; border: 2px solid var(--accent); box-shadow: 0 12px 24px -6px rgba(2, 132, 199, 0.12); overflow: hidden; }
        .generator-header { background: linear-gradient(135deg, var(--primary) 0%, #1e3a8a 100%); color: var(--white); padding: 1.5rem 2rem; display: flex; justify-content: space-between; align-items: center; flex-wrap: wrap; gap: 1rem; }
        .generator-body { padding: 2rem; display: grid; grid-template-columns: 1fr 1.6fr; gap: 2rem; }
        .form-group { margin-bottom: 1.2rem; }
        .form-group label { display: block; font-weight: 700; margin-bottom: 0.4rem; color: var(--primary); font-size: 0.95rem; }
        .form-control { width: 100%; padding: 0.75rem 1rem; border: 1px solid #cbd5e1; border-radius: 8px; font-size: 1rem; background-color: #f8fafc; }
        
        .calc-summary { display: grid; grid-template-columns: repeat(3, 1fr); gap: 1rem; margin-bottom: 1.5rem; }
        .summary-box { background: #f8fafc; border: 1px solid var(--border); padding: 1rem; border-radius: 10px; text-align: center; }
        .summary-box span { display: block; font-size: 0.85rem; color: #64748b; }
        .summary-box strong { font-size: 1.15rem; color: var(--primary); }
        .odoo-hint-box { margin-top: 1.2rem; background: var(--odoo-light); border-right: 4px solid var(--odoo-color); padding: 1rem 1.2rem; border-radius: 8px; font-size: 0.95rem; }

        .auth-container { max-width: 480px; margin: 2rem auto; background: var(--white); padding: 2.5rem; border-radius: 16px; box-shadow: 0 10px 25px rgba(0,0,0,0.08); border: 1px solid var(--border); }
        .auth-container h2 { text-align: center; margin-bottom: 1.5rem; color: var(--primary); }
        .library-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 1.2rem; margin-top: 1.5rem; }
        .book-card { background: var(--white); padding: 1.5rem; border-radius: 10px; border: 1px solid var(--border); display: flex; flex-direction: column; justify-content: space-between; }
        .btn-download { display: inline-block; background-color: var(--success); color: var(--white); padding: 0.5rem 1rem; border-radius: 6px; text-decoration: none; font-weight: 700; font-size: 0.9rem; text-align: center; margin-top: 1rem; }
        .locked-msg { background: #fef2f2; color: #991b1b; padding: 0.8rem; border-radius: 6px; font-size: 0.85rem; text-align: center; margin-top: 1rem; font-weight: 600; border: 1px solid #fecaca; }

        footer { background: var(--primary); color: #94a3b8; text-align: center; padding: 2rem; margin-top: 3rem; }

        @media (max-width: 992px) {
            .generator-body { grid-template-columns: 1fr; }
            .nav-links { display: none; }
        }
    </style>
</head>
<body>

    <!-- القائمة العلوية -->
    <header>
        <div class="nav-container">
            <a class="logo" onclick="switchPage('home')">📊 الأكاديمية <span>المحاسبية</span></a>
            <ul class="nav-links">
                <li><button onclick="switchPage('home')" id="nav-home" class="active-nav">🧮 مولّد القيود</button></li>
                <li><button onclick="switchPage('basics')" id="nav-basics">📖 الأساسيات والمكتبة</button></li>
                <li><button onclick="switchPage('advanced')" id="nav-advanced">📚 أمثلة متقدمة وموسعة</button></li>
                <li><button onclick="switchPage('odoo')" id="nav-odoo">⚙️ شرح Odoo</button></li>
                <li><button onclick="switchPage('owner-dashboard')" id="nav-owner" class="owner-btn">👥 لوحة الأعضاء</button></li>
                <li><button onclick="switchPage('login')" id="nav-login" class="auth-btn">تسجيل الدخول</button></li>
            </ul>
        </div>
    </header>

    <!-- 1. مولّد القيود (الرئيسية) -->
    <div id="page-home" class="page-view active-page">
        <section class="hero">
            <h1>مولّد القيود المحاسبية الذكي والمتقدم</h1>
            <p>أكثر من 15 قيداً محاسبياً متقدماً ومعقداً مع حساب الضريبة 15% وتوجيه أودو.</p>
        </section>
        <div class="container" style="padding-top: 2rem;">
            <div class="generator-wrapper">
                <div class="generator-header">
                    <div><h3 style="font-size: 1.3rem; color:#fff;">⚙️ محاكي القيود المحاسبية المتقدم</h3></div>
                    <span class="badge" style="background: #714B67; color:#fff; padding:0.4rem 0.8rem; border-radius:50px; font-size:0.85rem;">محاسبة مالية</span>
                </div>
                <div class="generator-body">
                    <div>
                        <div class="form-group"><label>قيمة العملية (بالريال):</label><input type="number" id="txAmount" class="form-control" value="20000" oninput="generateAdvancedEntry()"></div>
                        <div class="form-group">
                            <label>اختر القيد المحاسبي:</label>
                            <select id="txType" class="form-control" onchange="generateAdvancedEntry()">
                                <option value="sales_credit">1. مبيعات بالآجل شامل الضريبة 15%</option>
                                <option value="purchase_credit">2. مشتريات بضاعة بالآجل شامل الضريبة 15%</option>
                                <option value="compound_purchase">3. فاتورة مشتريات مركبة (أصل + مخزون + مصاريف)</option>
                                <option value="depreciation">4. قيد إهلاك الأصول الثابتة</option>
                                <option value="zakat_provision">5. إثبات مخصص الزكاة الشرعية</option>
                            </select>
                        </div>
                        <div class="form-group" id="vatGroup">
                            <label>معالجة الضريبة:</label>
                            <select id="vatStatus" class="form-control" onchange="generateAdvancedEntry()">
                                <option value="exclusive">المبلغ غير شامل الضريبة (إضافة 15%)</option>
                                <option value="inclusive">المبلغ شامل الضريبة (استخراج 15%)</option>
                                <option value="none" selected>بدون ضريبة (0%)</option>
                            </select>
                        </div>
                        <div class="form-group">
                            <label>مركز التكلفة (Odoo):</label>
                            <select id="analyticCenter" class="form-control" onchange="generateAdvancedEntry()">
                                <option value="قطاع المشاريع الهندسية">قطاع المشاريع الهندسية</option>
                                <option value="قطاع الأمن والحراسات">قطاع الأمن والحراسات</option>
                            </select>
                        </div>
                    </div>
                    <div>
                        <div class="calc-summary">
                            <div class="summary-box"><span>المبلغ الأساسي</span><strong id="resNet">20,000.00</strong></div>
                            <div class="summary-box"><span>الضريبة (15%)</span><strong id="resVat" style="color: var(--accent);">0.00</strong></div>
                            <div class="summary-box" style="background: #f0fdf4;"><span>الإجمالي المتوازن</span><strong id="resTotal" style="color: var(--success);">20,000.00</strong></div>
                        </div>
                        <table class="entry-table" style="margin-top: 0;">
                            <thead><tr><th>مدين</th><th>دائن</th><th>اسم الحساب المحاسبي</th><th>مركز التكلفة</th></tr></thead>
                            <tbody id="generatedEntryBody"></tbody>
                        </table>
                        <div class="odoo-hint-box" id="odooGuidance"></div>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- 2. الأساسيات والمكتبة -->
    <div id="page-basics" class="page-view">
        <div class="container">
            <div class="card">
                <h3>📖 أساسيات المحاسبة والتحليل المالي</h3>
                <p>تشمل القوائم المالية، المعادلة المحاسبية، وتوجيه العمليات في النظام.</p>
            </div>
            <div class="card">
                <h3>📚 المكتبة الرقمية (رفع الكتب والملفات)</h3>
                <p id="libraryNotice" style="color: var(--danger); font-weight: 700; margin-bottom: 1rem;">⚠️ تنبيه: المحتوى مقفل، يتطلب تسجيل الدخول لفتح وتحميل الكتب أو رفع ملفات جديدة.</p>
                
                <!-- صندوق إضافة كتاب يظهر لكل عضو مسجل (برابط أو ملف PDF) -->
                <div id="memberUploadBox" style="display: none; margin-bottom: 1.5rem; padding: 1.5rem; background: #f8fafc; border-radius: 10px; border: 2px dashed var(--accent);">
                    <h4 style="color: var(--accent); margin-bottom: 0.8rem;">📖 إضافة كتاب أو ملف جديد للمكتبة</h4>
                    <div class="form-group">
                        <label>عنوان الكتاب / الملف:</label>
                        <input type="text" id="userBookTitle" class="form-control" placeholder="اكتب اسم الكتاب...">
                    </div>
                    <div class="form-group">
                        <label>اختر طريقة الإضافة:</label>
                        <select id="uploadType" class="form-control" onchange="toggleUploadInput()">
                            <option value="file">رفع ملف PDF من جهازك</option>
                            <option value="link">إدخال رابط مباشر (URL)</option>
                        </select>
                    </div>
                    <div class="form-group" id="fileInputGroup">
                        <label>اختر ملف الـ PDF:</label>
                        <input type="file" id="userBookFile" class="form-control" accept=".pdf">
                    </div>
                    <div class="form-group" id="linkInputGroup" style="display: none;">
                        <label>رابط التحميل (URL):</label>
                        <input type="text" id="userBookUrl" class="form-control" placeholder="https://...">
                    </div>
                    <button class="btn" onclick="addBookByMember()">➕ نشر الكتاب في المكتبة</button>
                </div>

                <div class="library-grid" id="libraryContainer"></div>
            </div>
        </div>
    </div>

    <!-- 3. لوحة تحكم المالك الخاصة ببيانات المستخدمين -->
    <div id="page-owner-dashboard" class="page-view">
        <div class="container">
            <div class="card">
                <h3 style="color: var(--odoo-color); margin-bottom: 0.5rem;">👥 لوحة تحكم المالك - بيانات الأعضاء والمستخدمين</h3>
                <p style="color: #64748b; margin-bottom: 1.5rem;">هذه الصفحة سرية ولا يراها سوى مالك المنصة. تعرض تفاصيل جميع المسجلين:</p>
                
                <table class="entry-table">
                    <thead>
                        <tr>
                            <th>الاسم الكامل</th>
                            <th>رقم الهاتف</th>
                            <th>البريد الإلكتروني</th>
                            <th>سؤال الأمان</th>
                            <th>الإجابة السرية</th>
                            <th>إجراء</th>
                        </tr>
                    </thead>
                    <tbody id="usersTableBody"></tbody>
                </table>
            </div>
        </div>
    </div>

    <!-- 4. أمثلة متقدمة وموسعة بالكامل -->
    <div id="page-advanced" class="page-view">
        <div class="container">
            <div class="section-title" style="text-align: center; margin-bottom: 2rem;">
                <h2>📚 الموسوعة المحاسبية والأمثلة المتقدمة الشاملة</h2>
                <p style="color: #64748b;">تحليل عميق ومعالجات دقيقة لأهم العمليات المالية المعقدة</p>
            </div>

            <!-- الحالة الأولى -->
            <div class="card">
                <h3>🏢 1. المعالجة المحاسبية الشاملة لبيع الأصول الثابتة (ربح / خسارة / تعادل)</h3>
                <p style="margin-bottom: 1rem; color: #475569;">عندما تقرر المنشأة التخلص من أصل ثابت (مثل سيارة أو آلة)، يجب إثبات استبعاد تكلفته التاريخية وإلغاء مجمع إهلاكه، ومقارنة القيمة الدفترية بسعر البيع الفعلي:</p>
                
                <div class="grid-2" style="display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 1rem; margin-top: 1rem;">
                    <div style="background: #f8fafc; padding: 1.2rem; border-radius: 8px; border: 1px solid var(--border);">
                        <h4 style="color: var(--success); margin-bottom: 0.5rem;">أ. حالة بيع الأصل بربح رأسمالي</h4>
                        <p style="font-size: 0.9rem; margin-bottom: 0.5rem;">إذا كانت القيمة الدفترية 20,000 ريال وتم البيع بمبلغ 25,000 ريال (مكسب 5,000).</p>
                        <table class="entry-table" style="font-size: 0.85rem;">
                            <tr><th>مدين</th><th>دائن</th><th>الحساب</th></tr>
                            <tr><td class="debit-val">25,000</td><td>-</td><td>حـ/ البنك / الصندوق (سعر البيع)</td></tr>
                            <tr><td class="debit-val">30,000</td><td>-</td><td>حـ/ مجمع إهلاك الأصل</td></tr>
                            <tr><td>-</td><td class="credit-val">50,000</td><td>حـ/ الأصل الثابت (بالتكلفة)</td></tr>
                            <tr><td>-</td><td class="credit-val">5,000</td><td>حـ/ أرباح بيع أصول ثابتة (قائمة الدخل)</td></tr>
                        </table>
                    </div>

                    <div style="background: #f8fafc; padding: 1.2rem; border-radius: 8px; border: 1px solid var(--border);">
                        <h4 style="color: var(--danger); margin-bottom: 0.5rem;">ب. حالة بيع الأصل بخسارة رأسمالية</h4>
                        <p style="font-size: 0.9rem; margin-bottom: 0.5rem;">إذا كانت القيمة الدفترية 20,000 ريال وتم البيع بمبلغ 16,000 ريال (خسارة 4,000).</p>
                        <table class="entry-table" style="font-size: 0.85rem;">
                            <tr><th>مدين</th><th>دائن</th><th>الحساب</th></tr>
                            <tr><td class="debit-val">16,000</td><td>-</td><td>حـ/ البنك / الصندوق (سعر البيع)</td></tr>
                            <tr><td class="debit-val">30,000</td><td>-</td><td>حـ/ مجمع إهلاك الأصل</td></tr>
                            <tr><td class="debit-val">4,000</td><td>-</td><td>حـ/ خسائر بيع أصول ثابتة (قائمة الدخل)</td></tr>
                            <tr><td>-</td><td class="credit-val">50,000</td><td>حـ/ الأصل الثابت (بالتكلفة)</td></tr>
                        </table>
                    </div>
                </div>
            </div>

            <!-- الحالة الثانية -->
            <div class="card">
                <h3>📦 2. معالجة تسوية جرد المخزون (العجز والزيادة)</h3>
                <p style="margin-bottom: 1rem; color: #475569;">عند إجراء الجرد الفعلي للمستودعات، تظهر فروق بين الرصيد الدفتري والرصيد الفعلي:</p>
                <ul style="padding-right: 1.5rem; font-size: 0.95rem; display: flex; flex-direction: column; gap: 0.5rem;">
                    <li><strong>حالة العجز الطبيعي:</strong> يعتبر تكلفة إضافية تحمل على النشاط (من حـ/ عجز مخزون مسموح به إلى حـ/ المخزون).</li>
                    <li><strong>حالة العجز غير الطبيعي (مسؤولية أمين المستودع):</strong> يعتبر عهدة شخصية على الموظف (من حـ/ عهدة أمين المستودع إلى حـ/ المخزون).</li>
                    <li><strong>حالة الزيادة في المخزون:</strong> تثبت كإيرادات أخرى أو تسوية مخزنية بعد التحقيق (من حـ/ المخزون إلى حـ/ إيرادات متنوعة).</li>
                </ul>
            </div>

            <!-- الحالة الثالثة -->
            <div class="card">
                <h3>⏳ 3. تسوية المصروفات والإيرادات (المقدمة والمستحقة)</h3>
                <p style="margin-bottom: 1rem; color: #475569;">تطبيقاً لمبدأ الاستحقاق المحاسبي (Accrual Basis)، يجب تحميل السنة المالية بما يخصها فقط بغض النظر عن السداد النقدي:</p>
                <div style="background: #f8fafc; padding: 1rem; border-radius: 8px; border: 1px solid var(--border);">
                    <p><strong>مثال المصروف المقدم (إيجار مدفوع مقدماً لمدة سنتين):</strong> عند السداد (من حـ/ إيجار مقدم إلى حـ/ البنك). في نهاية السنة يتم إثبات ما يخص السنة الحالية فقط بقيد التسوية: <br><code>(من حـ/ مصروف الإيجار إلى حـ/ إيجار مقدم)</code>.</p>
                </div>
            </div>

        </div>
    </div>

    <!-- 5. شرح Odoo -->
    <div id="page-odoo" class="page-view">
        <div class="container">
            <div class="card" style="text-align: center; background: linear-gradient(135deg, #714B67 0%, #4a2f43 100%); color: #fff;">
                <h3>⚙️ شرح نظام Odoo المحاسبي</h3>
                <a href="https://www.youtube.com/watch?v=wQG2tDhDTa0&list=PLNUk9qMoRCS8Bl2eOTzm8wmJuw2semQuN&index=15" target="_blank" rel="noopener noreferrer" class="btn" style="background-color: #ff0000; color: #fff; text-decoration: none; padding: 0.8rem 2rem; border-radius: 50px; font-weight: 800; margin-top: 1rem;">
                    ▶ مشاهدة الدرس على يوتيوب
                </a>
            </div>
        </div>
    </div>

    <!-- 6. تسجيل الدخول -->
    <div id="page-login" class="page-view">
        <div class="auth-container">
            <h2>تسجيل الدخول</h2>
            <div class="form-group"><label>رقم الهاتف:</label><input type="text" id="loginPhone" class="form-control" placeholder="05xxxxxxxx"></div>
            <div class="form-group"><label>كلمة المرور:</label><input type="password" id="loginPassword" class="form-control" placeholder="********"></div>
            <button class="btn" style="width: 100%; margin-bottom: 1rem;" onclick="handleLogin()">دخول</button>
            <div style="text-align: center; display: flex; justify-content: space-between; font-size: 0.9rem;">
                <a href="#" onclick="switchPage('register'); return false;" style="color: var(--accent);">إنشاء حساب جديد</a>
                <a href="#" onclick="switchPage('forgot'); return false;" style="color: var(--danger);">نسيت رقمك السري؟</a>
            </div>
        </div>
    </div>

    <!-- صفحة إنشاء حساب جديد (مع اسم المستخدم) -->
    <div id="page-register" class="page-view">
        <div class="auth-container">
            <h2>إنشاء حساب جديد</h2>
            <div class="form-group"><label>الاسم الكامل:</label><input type="text" id="regName" class="form-control" placeholder="ادخل اسمك الكامل..."></div>
            <div class="form-group"><label>البريد الإلكتروني:</label><input type="email" id="regEmail" class="form-control" placeholder="name@example.com"></div>
            <div class="form-group"><label>رقم الهاتف:</label><input type="text" id="regPhone" class="form-control" placeholder="05xxxxxxxx"></div>
            <div class="form-group"><label>كلمة المرور:</label><input type="password" id="regPassword" class="form-control" placeholder="********"></div>
            <div class="form-group">
                <label>سؤال الأمان لاسترجاع الرقم السري:</label>
                <select id="regSecurityQuestion" class="form-control">
                    <option value="ما هو اسم أول مدرسة درست بها؟">ما هو اسم أول مدرسة درست بها؟</option>
                    <option value="ما هو كتابك المفضل؟">ما هو كتابك المفضل؟</option>
                    <option value="ما هو اسم خالك؟">ما هو اسم خالك؟</option>
                </select>
            </div>
            <div class="form-group"><label>إجابة سؤال الأمان:</label><input type="text" id="regSecurityAnswer" class="form-control" placeholder="إجابتك السرية..."></div>
            <button class="btn" style="width: 100%; margin-bottom: 1rem;" onclick="handleRegister()">تسجيل الحساب</button>
            <div style="text-align: center;"><a href="#" onclick="switchPage('login'); return false;" style="color: var(--accent);">لديك حساب بالفعل؟ تسجيل الدخول</a></div>
        </div>
    </div>

    <!-- استعادة كلمة المرور -->
    <div id="page-forgot" class="page-view">
        <div class="auth-container">
            <h2>استعادة كلمة المرور</h2>
            <div id="forgotStep1">
                <div class="form-group"><label>البريد الإلكتروني:</label><input type="email" id="forgotEmail" class="form-control"></div>
                <div class="form-group"><label>رقم الهاتف:</label><input type="text" id="forgotPhone" class="form-control"></div>
                <button class="btn" style="width: 100%; margin-bottom: 1rem;" onclick="verifyForgotUser()">التحقق من البيانات</button>
            </div>
            <div id="forgotStep2" style="display: none;">
                <p id="displaySecurityQuestion" style="color: var(--accent); font-weight: 800; margin-bottom: 1rem;"></p>
                <div class="form-group"><label>إجابة سؤال الأمان:</label><input type="text" id="forgotAnswerInput" class="form-control"></div>
                <div class="form-group"><label>الرقم السري الجديد:</label><input type="password" id="newPasswordInput" class="form-control"></div>
                <button class="btn" style="width: 100%; margin-bottom: 1rem;" onclick="resetPasswordFinal()">حفظ الرقم السري الجديد</button>
            </div>
            <div style="text-align: center;"><a href="#" onclick="switchPage('login'); return false;" style="color: var(--accent);">العودة لتسجيل الدخول</a></div>
        </div>
    </div>

    <footer>
        <p>جميع الحقوق محفوظة © 2026 - الأكاديمية المحاسبية المتقدمة</p>
    </footer>

    <script>
        function switchPage(pageId) {
            document.querySelectorAll('.page-view').forEach(p => p.classList.remove('active-page'));
            document.querySelectorAll('.nav-links button').forEach(b => b.classList.remove('active-nav'));
            document.getElementById('page-' + pageId).classList.add('active-page');
            
            if(pageId === 'home') document.getElementById('nav-home').classList.add('active-nav');
            if(pageId === 'basics') document.getElementById('nav-basics').classList.add('active-nav');
            if(pageId === 'advanced') document.getElementById('nav-advanced').classList.add('active-nav');
            if(pageId === 'odoo') document.getElementById('nav-odoo').classList.add('active-nav');
            if(pageId === 'owner-dashboard') {
                document.getElementById('nav-owner').classList.add('active-nav');
                renderUsersTable();
            }
            
            window.scrollTo(0, 0);
            renderBooks();
        }

        let currentUser = JSON.parse(localStorage.getItem('currentUser')) || null;
        let books = JSON.parse(localStorage.getItem('appBooks')) || [
            { id: 1, title: 'دليل المعايير الدولية (IFRS)', type: 'link', url: 'https://www.ifrs.org', uploader: 'المدير' },
            { id: 2, title: 'دليل المحاسبة والتكاليف في Odoo', type: 'link', url: 'https://www.odoo.com', uploader: 'المدير' }
        ];
        let targetResetUserEmail = null;

        function isOwner() {
            return currentUser && (currentUser.phone === '0500169090' || currentUser.phone === '0500000000' || currentUser.isAdmin === true);
        }

        function checkAuthStatus() {
            const authBtn = document.getElementById('nav-login');
            const ownerBtn = document.getElementById('nav-owner');
            const memberUploadBox = document.getElementById('memberUploadBox');
            const libraryNotice = document.getElementById('libraryNotice');

            if (currentUser) {
                authBtn.innerText = 'خروج (' + currentUser.phone + ')';
                authBtn.className = 'auth-btn btn-danger';
                authBtn.onclick = handleLogout;
                if(libraryNotice) libraryNotice.style.display = 'none';
                if(memberUploadBox) memberUploadBox.style.display = 'block'; // متاح لأي عضو مسجل

                if (isOwner()) {
                    if(ownerBtn) ownerBtn.style.display = 'inline-block';
                } else {
                    if(ownerBtn) ownerBtn.style.display = 'none';
                }
            } else {
                authBtn.innerText = 'تسجيل الدخول';
                authBtn.className = 'auth-btn';
                authBtn.onclick = () => switchPage('login');
                if(ownerBtn) ownerBtn.style.display = 'none';
                if(memberUploadBox) memberUploadBox.style.display = 'none';
                if(libraryNotice) libraryNotice.style.display = 'block';
            }
            renderBooks();
        }

        function toggleUploadInput() {
            const type = document.getElementById('uploadType').value;
            if (type === 'file') {
                document.getElementById('fileInputGroup').style.display = 'block';
                document.getElementById('linkInputGroup').style.display = 'none';
            } else {
                document.getElementById('fileInputGroup').style.display = 'none';
                document.getElementById('linkInputGroup').style.display = 'block';
            }
        }

        function handleRegister() {
            const name = document.getElementById('regName').value.trim();
            const email = document.getElementById('regEmail').value.trim();
            const phone = document.getElementById('regPhone').value.trim();
            const password = document.getElementById('regPassword').value.trim();
            const question = document.getElementById('regSecurityQuestion').value;
            const answer = document.getElementById('regSecurityAnswer').value.trim();

            if (!name || !email || !phone || !password || !answer) {
                alert('الرجاء إكمال جميع الحقول وإدخال الاسم الكامل.');
                return;
            }

            let users = JSON.parse(localStorage.getItem('appUsers')) || [];
            if(users.some(u => u.phone === phone)) {
                alert('رقم الهاتف مسجل مسبقاً!');
                return;
            }

            users.push({ name, email, phone, password, question, answer, isAdmin: false });
            localStorage.setItem('appUsers', JSON.stringify(users));
            alert('تم إنشاء الحساب بنجاح! سجل دخولك الآن.');
            switchPage('login');
        }

        function handleLogin() {
            const phone = document.getElementById('loginPhone').value.trim();
            const password = document.getElementById('loginPassword').value.trim();

            if ((phone === '0500169090' && password === '12341234') || (phone === '0500000000' && password === 'admin123')) {
                currentUser = { name: 'المالك الرئيسي', phone: phone, email: 'admin@academy.com', isAdmin: true };
                localStorage.setItem('currentUser', JSON.stringify(currentUser));
                alert('مرحباً بك يا مالك المنصة!');
                switchPage('home');
                checkAuthStatus();
                return;
            }

            let users = JSON.parse(localStorage.getItem('appUsers')) || [];
            let validUser = users.find(u => u.phone === phone && u.password === password);

            if (validUser) {
                currentUser = validUser;
                localStorage.setItem('currentUser', JSON.stringify(currentUser));
                alert('تم تسجيل الدخول بنجاح.');
                switchPage('home');
                checkAuthStatus();
            } else {
                alert('رقم الهاتف أو كلمة المرور غير صحيحة.');
            }
        }

        function handleLogout() {
            currentUser = null;
            localStorage.removeItem('currentUser');
            alert('تم تسجيل الخروج بنجاح.');
            checkAuthStatus();
            switchPage('home');
        }

        function renderUsersTable() {
            if (!isOwner()) return;
            const tbody = document.getElementById('usersTableBody');
            tbody.innerHTML = '';

            let users = JSON.parse(localStorage.getItem('appUsers')) || [];
            if (users.length === 0) {
                tbody.innerHTML = `<tr><td colspan="6" style="text-align: center; color: #64748b;">لا توجد حسابات مسجلة حتى الآن.</td></tr>`;
                return;
            }

            users.forEach((u, index) => {
                tbody.innerHTML += `
                    <tr>
                        <td><strong>${u.name}</strong></td>
                        <td>${u.phone}</td>
                        <td>${u.email}</td>
                        <td>${u.question}</td>
                        <td><code>${u.answer}</code></td>
                        <td><button class="btn btn-danger" style="padding: 0.3rem 0.7rem; font-size: 0.8rem;" onclick="deleteUser(${index})">🗑️ حذف</button></td>
                    </tr>
                `;
            });
        }

        function deleteUser(index) {
            if (confirm('هل أنت متأكد من حذف هذا المستخدم؟')) {
                let users = JSON.parse(localStorage.getItem('appUsers')) || [];
                users.splice(index, 1);
                localStorage.setItem('appUsers', JSON.stringify(users));
                renderUsersTable();
            }
        }

        function verifyForgotUser() {
            const email = document.getElementById('forgotEmail').value.trim();
            const phone = document.getElementById('forgotPhone').value.trim();
            let users = JSON.parse(localStorage.getItem('appUsers')) || [];
            let user = users.find(u => u.email === email && u.phone === phone);

            if (user) {
                targetResetUserEmail = email;
                document.getElementById('displaySecurityQuestion').innerText = "سؤال الأمان: " + user.question;
                document.getElementById('forgotStep1').style.display = 'none';
                document.getElementById('forgotStep2').style.display = 'block';
            } else {
                alert('لم يتم العثور على حساب.');
            }
        }

        function resetPasswordFinal() {
            const answerInput = document.getElementById('forgotAnswerInput').value.trim();
            const newPassword = document.getElementById('newPasswordInput').value.trim();
            let users = JSON.parse(localStorage.getItem('appUsers')) || [];
            let userIndex = users.findIndex(u => u.email === targetResetUserEmail);

            if (userIndex !== -1 && users[userIndex].answer.trim().toLowerCase() === answerInput.toLowerCase()) {
                users[userIndex].password = newPassword;
                localStorage.setItem('appUsers', JSON.stringify(users));
                alert('🎉 تم تغيير الرقم السري بنجاح!');
                switchPage('login');
            } else {
                alert('❌ إجابة سؤال الأمان خاطئة!');
            }
        }

        // دالة رفع الكتب من قبل الأعضاء (ملف PDF أو رابط)
        function addBookByMember() {
            const title = document.getElementById('userBookTitle').value.trim();
            const type = document.getElementById('uploadType').value;
            
            if (!title) {
                alert('الرجاء إدخال عنوان الكتاب أو الملف.');
                return;
            }

            if (type === 'link') {
                const url = document.getElementById('userBookUrl').value.trim();
                if (!url) { alert('أدخل الرابط المباشر.'); return; }
                saveBookData({ id: Date.now(), title, type: 'link', url, uploader: currentUser.name });
            } else {
                const fileInput = document.getElementById('userBookFile');
                if (fileInput.files.length === 0) { alert('اختر ملف PDF من جهازك.'); return; }
                
                const file = fileInput.files;
                const reader = new FileReader();
                reader.onload = function(e) {
                    const base64Data = e.target.result; // حفظ الملف كبيانات محلية
                    saveBookData({ id: Date.now(), title, type: 'file', url: base64Data, uploader: currentUser.name, fileName: file.name });
                };
                reader.readAsDataURL(file);
            }
        }

        function saveBookData(bookObj) {
            books.push(bookObj);
            localStorage.setItem('appBooks', JSON.stringify(books));
            document.getElementById('userBookTitle').value = '';
            document.getElementById('userBookUrl').value = '';
            document.getElementById('userBookFile').value = '';
            renderBooks();
            alert('✅ تمت إضافة ونشر الكتاب في المكتبة بنجاح!');
        }

        function deleteBook(id) {
            books = books.filter(b => b.id !== id);
            localStorage.setItem('appBooks', JSON.stringify(books));
            renderBooks();
        }

        function renderBooks() {
            const container = document.getElementById('libraryContainer');
            if(!container) return;
            container.innerHTML = '';

            books.forEach(b => {
                const card = document.createElement('div');
                card.className = 'book-card';
                
                let actionContent = '';
                if (currentUser) {
                    let downloadBtn = `<a href="${b.url}" target="_blank" rel="noopener noreferrer" class="btn-download" ${b.type === 'file' ? 'download="' + (b.fileName || 'book.pdf') + '"' : ''}>📥 تحميل أو قراءة الكتاب</a>`;
                    
                    // المالك يمكنه حذف أي كتاب، والعضو يمكنه حذف كتابه الذي رفعه فقط
                    let canDelete = isOwner() || (b.uploader && currentUser && b.uploader === currentUser.name);
                    let deleteBtn = canDelete ? `<button class="btn btn-danger" style="padding:0.3rem; font-size:0.8rem; margin-top:0.5rem; width:100%;" onclick="deleteBook(${b.id})">🗑️ حذف الكتاب</button>` : '';
                    
                    actionContent = downloadBtn + deleteBtn;
                } else {
                    actionContent = `<div class="locked-msg">🔒 المحتوى مقفل<br>يجب تسجيل الدخول لفتح او تحميل الكتاب</div>`;
                }

                card.innerHTML = `
                    <div>
                        <span style="background: #e0f2fe; color: #0284c7; padding: 0.2rem 0.6rem; border-radius: 50px; font-size: 0.75rem; font-weight: 700;">بواسطة: ${b.uploader || 'المدير'}</span>
                        <h4 style="margin-top:0.4rem;">${b.title}</h4>
                    </div>
                    <div>${actionContent}</div>
                `;
                container.appendChild(card);
            });
        }

        function formatMoney(num) { return num.toLocaleString('en-US', { minimumFractionDigits: 2, maximumFractionDigits: 2 }); }

        function generateAdvancedEntry() {
            const rawAmount = parseFloat(document.getElementById('txAmount').value) || 0;
            const txType = document.getElementById('txType').value;
            const vatSelect = document.getElementById('vatStatus');
            const analytic = document.getElementById('analyticCenter').value;

            let netAmount = rawAmount, vatAmount = 0, totalAmount = rawAmount;
            if (vatSelect.value === 'exclusive') { vatAmount = rawAmount * 0.15; totalAmount = netAmount + vatAmount; }
            else if (vatSelect.value === 'inclusive') { netAmount = rawAmount / 1.15; vatAmount = rawAmount - netAmount; totalAmount = rawAmount; }

            document.getElementById('resNet').innerText = formatMoney(netAmount);
            document.getElementById('resVat').innerText = formatMoney(vatAmount);
            document.getElementById('resTotal').innerText = formatMoney(totalAmount);

            let rows = [], desc = '', odoo = '';
            if (txType === 'sales_credit') {
                rows.push({ debit: formatMoney(totalAmount), credit: '-', account: 'من حـ/ العملاء' });
                rows.push({ debit: '-', credit: formatMoney(netAmount), account: 'إلى حـ/ إيراد المبيعات' });
                if(vatAmount > 0) rows.push({ debit: '-', credit: formatMoney(vatAmount), account: 'إلى حـ/ ضريبة القيمة المضافة' });
                desc = 'إثبات مبيعات بالآجل'; odoo = 'تُرحل في يومية فواتير العملاء (Customer Invoices).';
            } else {
                rows.push({ debit: formatMoney(netAmount), credit: '-', account: 'من حـ/ المصروفات / الأصل' });
                rows.push({ debit: '-', credit: formatMoney(totalAmount), account: 'إلى حـ/ الموردين / البنك' });
                desc = 'قيد تسوية أو تشغيلي'; odoo = 'تُرحل في اليوميات العامة لـ Odoo.';
            }

            const tbody = document.getElementById('generatedEntryBody');
            tbody.innerHTML = '';
            rows.forEach(r => {
                tbody.innerHTML += `<tr><td class="debit-val">${r.debit}</td><td class="credit-val">${r.credit}</td><td>${r.account}</td><td>${analytic}</td></tr>`;
            });
            tbody.innerHTML += `<tr class="entry-desc"><td colspan="4">📝 ${desc} | الإجمالي متوازن</td></tr>`;
            document.getElementById('odooGuidance').innerHTML = `<strong>💡 في Odoo:</strong> ${odoo}`;
        }

        window.onload = function() { checkAuthStatus(); generateAdvancedEntry(); };
    </script>
</body>
</html>
