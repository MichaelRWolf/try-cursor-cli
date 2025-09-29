# Timezone Interval Section Rules

## **Rules for Generating Timezone Interval Sections**

### **1. Section Heading Format**
- Use `###` level heading
- Format as ISO8601 interval: `YYYY-MM-DD/YYYY-MM-DD`
- Start date = when the interval begins
- End date = when the next timezone change occurs

### **2. Comment Line Format**
```
<Date> - <Why> - (<original offset> -> <new offset>)
```
**Examples:**
- `2025-03-30 - Start Daylight Time: Central Europe - (+01 -> +02)`
- `2025-10-26 - Stop Daylight Time: Central Europe - (+02 -> +01)`
- `2025-11-02 - Stop Daylight Time: East Coast - (-04 -> -05)`
- `2025-11-02 - No timezone changes (winter period)`

### **3. Table Structure**
```
| UTC   | Diana         | Michael          | Nitsan       | Gregor       |
| (Z)   | Phoenix (-07) | East Coast (-04) | Malaga (+01) | Vienna (+01) |
|-------|---------------|------------------|--------------|--------------|
| 14:00 | 7:00 AM       | 9:00 AM          | 3:00 PM      | 3:00 PM      |
| 15:00 | 8:00 AM       | 10:00 AM         | 4:00 PM      | 4:00 PM      |
| ...   | ...           | ...              | ...          | ...          |
```

### **4. TZ Offset Rules**
- **Phoenix**: Always `-07` (MST, no DST)
- **East Coast**: `-04` (EDT) or `-05` (EST) based on DST
- **Malaga/Vienna**: `+01` (CET) or `+02` (CEST) based on DST
- Get offsets from TZ Intervals table for the specific date

### **5. Time Calculation Rules**
- **Phoenix**: UTC - 7 hours
- **East Coast**: UTC - 4 or -5 hours (based on DST)
- **Malaga/Vienna**: UTC + 1 or +2 hours (based on DST)
- **Gregor's constraint**: End times should respect his 8:00 PM preference

### **6. UTC Time Range**
- Start at UTC 14:00 (7:00 AM Phoenix, Diana's earliest)
- End at UTC 19:00 (8:00 PM Vienna, Gregor's latest)
- Include all hours in between

### **7. Special Cases**
- **No timezone changes**: Use comment "No timezone changes (winter period)"
- **Multiple regions change**: Focus on the primary triggering event
- **Stable periods**: Between major DST transitions

### **8. Validation Checklist**
- ✅ TZ offsets match TZ Intervals table for that date
- ✅ All local times correctly calculated from UTC
- ✅ Diana's earliest time (7:00 AM Phoenix) respected
- ✅ Gregor's latest time (8:00 PM Vienna) respected
- ✅ Comment accurately describes the triggering event and offset change
