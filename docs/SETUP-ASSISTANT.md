# 🤖 راهنمای نصب GitHub Actions Assistant

## مشکل
فایل workflow نمی‌تونه مستقیم ایجاد بشه. لازم است دستی اضافه بشه.

## راه حل - 3 گام ساده:

### گام 1️⃣: فایل Workflow رو ایجاد کنید
1. برو به repository خودت: https://github.com/mahdis2006kamali-cmyk/marketing-workflow
2. برو به `.github/workflows/`
3. کلیک `Add file` → `Create new file`
4. اسم: `smart-assistant.yml`

### گام 2️⃣: کد زیر رو کپی کن:

```yaml
name: 🤖 AI Marketing Assistant

on:
  schedule:
    - cron: '45 4 * * *'
  workflow_dispatch:

jobs:
  assistant:
    runs-on: ubuntu-latest
    permissions:
      issues: write
      
    steps:
      - name: Create Daily Reminder
        uses: actions/github-script@v7
        with:
          script: |
            const today = new Date().toLocaleDateString('fa-IR');
            
            await github.rest.issues.create({
              owner: context.repo.owner,
              repo: context.repo.repo,
              title: `🤖 یادآوری امروز - ${today}`,
              body: `# 🤖 دستیار مارکتینگ ذهین\n\n**تاریخ**: ${today}\n\n## 📋 کارهای امروز\n- [ ] بررسی کمپین‌های جاری\n- [ ] تحلیل معیارهای موفقیت  \n- [ ] پاسخ به نظرات و پیام‌ها\n- [ ] به‌روزرسانی محتوا\n- [ ] تحلیل عملکرد کمپین‌های دیروز\n\n## 💡 سه ایده جدید\n\n### 1️⃣ کمپین رسانه‌های اجتماعی\n- 📱 کمپین تفاعلی با تخفیف\n- 🎥 محتوای ویدیویی کوتاه برای TikTok و Reels\n- 📸 چالش جذاب با هشتگ خاص\n\n### 2️⃣ کمپین ایمیل مارکتینگ\n- 💌 سری ایمیل خودکار برای مشتریان\n- 🎁 پیشنهادات شخصی‌شده\n- 📊 تست A/B برای بهبود نرخ باز‌شدن\n\n### 3️⃣ کمپین محتوا و SEO\n- 📝 نوشتن بلاگ درباره ترندها\n- 🔍 بهینه‌سازی کلمات کلیدی\n- 🎯 محتوای آموزشی برای جذب مخاطب\n\n## 🎯 نکات استراتژیک\n\n1. **تنوع محتوا** 📊\n   - انواع مختلف محتوا (ویدیو، متن، تصویر)\n   - برخورد متفاوت در هر پلتفرم\n\n2. **زمان‌بندی بهتر** ⏰\n   - بهترین زمان برای انتشار\n   - ساعات فعالیت دنبال‌کنندگان\n\n3. **تعامل بیشتر** 💬\n   - پاسخ سریع به نظرات\n   - تعامل با دنبال‌کنندگان جدید\n\n4. **تجزیه و تحلیل** 📈\n   - مرور روزانه معیارهای موفقیت\n   - تحلیل کمپین‌های قبلی\n\n5. **آزمایش و یادگیری** 🧪\n   - روش‌های جدید را امتحان کنید\n   - از نتایج بیاموزید\n\n## 📊 چک‌لیست امروز\n- [ ] بررسی Issues جدید\n- [ ] تحلیل معیارهای دیروز\n- [ ] انتخاب ایده برای اجرا امروز\n- [ ] برنامه‌ریزی برای فردا\n- [ ] یادداشت نکات مهم\n\n## 🔗 لینک‌های مفید\n- Issues: https://github.com/${context.repo.owner}/${context.repo.repo}/issues\n- Projects: https://github.com/${context.repo.owner}/${context.repo.repo}/projects\n- Discussions: https://github.com/${context.repo.owner}/${context.repo.repo}/discussions\n\n---\n*توسط 🤖 دستیار مارکتینگ ذهین تولید شد*\n*زمان: ${new Date().toLocaleTimeString('fa-IR')}*`,
              labels: ['🤖-assistant', '📅-daily-reminder']
            });
```

### گام 3️⃣: Commit کن
- کلیک `Commit changes`
- پیام: `افزودن GitHub Assistant خودکار`

---

## ✅ تنظیمات اضافی

### تغییر زمان یادآوری:
بدل کن این خط:
```yaml
- cron: '45 4 * * *'
```

- `45 4` = ساعت 8:15 صبح (بر حسب UTC+0)
- برای تهران (UTC+3:30): از `45 4` استفاده کنید

### اجرا دستی:
1. برو به **Actions**
2. انتخاب **🤖 AI Marketing Assistant**
3. کلیک **Run workflow**

---

## 🎉 بعد از نصب

**هر روز ساعت 8:15 صبح:**
- ✅ یک Issue جدید ایجاد میشه
- ✅ 3 ایده جدید برای مارکتینگ
- ✅ کارهای روز یادآوری میشه
- ✅ نکات استراتژیک قید میشه

---

**سؤال؟ دیسکاسیون یا Issue باز کنید!** 🚀
