---
notion_id: "31743c23-a5e2-8023-8e93-d51dd8839efb"
notion_last_edited: "2026-05-06T12:00:00.000Z"
banner: "https://images.unsplash.com/photo-1478760329108-5c3ed9d495a0?ixlib=rb-4.0.3&auto=format&fit=crop&w=1440&q=80"
banner_y: 0.5
---

# 🌌 Command Center

> [!abstract] **Daily Overview**
> "The secret of your future is hidden in your daily routine." — *Unknown*

---

## 📊 Quick Stats
> [!multi-column]
>
>> [!success] **Solved Today**
>> `$= dv.pages('"Tickets"').filter(p => p.status == "Done" && p.date && p.date.isSame(moment(), 'day')).length`
>
>> [!info] **This Week**
>> `$= dv.pages('"Tickets"').filter(p => p.status == "Done" && p.date && p.date.isSame(moment(), 'week')).length`
>
>> [!note] **Active Docs**
>> `$= dv.pages().filter(p => p.file.mday.isSame(moment(), 'day')).length`

---

## 🟢 Solved Today
> [!list] Tickets completed on `$= moment().format('LL')`
> ```dataview
> TABLE ticket_id as "ID", tags as "Category", url as "Link"
> FROM "Tickets"
> WHERE status = "Done" AND date = date(today)
> SORT file.mtime DESC
> ```

---

## 🔵 Weekly Performance
> [!todo] Tickets resolved this week
> ```dataview
> TABLE date as "Resolved Date", tags as "Tags"
> FROM "Tickets"
> WHERE status = "Done" AND date.week = date(today).week AND date.year = date(today).year
> SORT date DESC
> ```

---

## 📝 Recent Knowledge & Logs
> [!example] Files updated or created today
> ```dataview
> LIST
> FROM !"Tickets"
> WHERE file.mday = date(today) OR notion_last_edited >= date(today)
> SORT file.mtime DESC
> LIMIT 10
> ```

---

### 🛠️ Maintenance
- [ ] Review pending tickets
- [ ] Clean up `Untitled` notes
- [ ] Sync Notion (Last Run: `$= moment().format('LLL')`)
