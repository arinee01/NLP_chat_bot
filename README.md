# NLP_chat_bot
Готово! Вот идеальный **README.md** для твоего UniBo FAQ Assistant — структурированный, профессиональный, и полностью соответствующий тому, что ты реально построила.
Ты можешь положить это в GitHub, PDF, в отчёт — куда угодно.

---

# 🎓 UniBo FAQ Assistant — README

## Overview

UniBo FAQ Assistant is a task-oriented chatbot built using **DialogFlow CX**.
The system provides fast and structured access to essential information for UniBo students, including class schedules, exam timetables, canteen locations, transport options, scholarships, and more.

# Features

### **Smart Welcome Menu**

On startup, the assistant displays suggestion chips for the main intents:

* Class timetable
* Exam timetable
* Office hours
* Contacts
* Canteen
* Transport
* Scholarships
* Admission
* Help

### **Name Personalisation**

The bot can capture the user's name through the intent **capture.name**
(e.g., “I’m Marco”, “My name is Arina”, “Kate”).
The name is extracted using **@sys.person** and stored in:

```
$session.params.user_name
```

Then reused in greetings:

> “Nice to meet you, Arina!”

### **Time-Aware Greetings**

Depending on the system time:

* Good morning
* Good afternoon
* Good evening

### **Campus-Aware Canteen Information**

A custom entity **@campus** handles values:
`Bologna, Forlì, Cesena, Rimini, Ravenna`.

Slot-filling prompts the user when the campus is missing:

> “Which campus are you at?”

Different canteen descriptions are given per campus.

### **Follow-up Suggestions**

After answering a question, the bot proposes related topics using chips.
Example: after canteen info →

* Transport
* Student Online
* Scholarships

### **Error Handling and Fallback Logic**

If the bot cannot interpret an input:

> “I didn’t understand, can you rephrase?”
> It also reprints the main menu.

---

# Architecture

### **Intents**

Core intents:

* class-timetable
* exam-timetable
* office-hours
* contacts
* canteen-info
* transport
* scholarships
* admission
* help
* capture.name


### **Entities**

**System entities**

* @sys.person (user name)
* @sys.geo-city (detects campuses when written as cities)
* @sys.date (optional)

**Custom entity**

* `@campus` = Bologna | Forlì | Cesena | Rimini | Ravenna

---

### **DialogFlow CX Components**

* **Flows** — 1 main flow
* **Pages** — Welcome + internal pages
* **Routes** — Intent routes + parameter-based conditional routes
* **Session Parameters**:




