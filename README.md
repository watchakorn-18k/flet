# Flet

<img src="media/logo/flet-logo.svg" width="50%"/>

[![Build status](https://ci.appveyor.com/api/projects/status/xwablctxslvey576/branch/main?svg=true)](https://ci.appveyor.com/project/flet-dev/flet/branch/main)

Flet เป็นเฟรมเวิร์กที่ช่วยให้คุณสร้างแอปแบบเรียลไทม์สำหรับเว็บ มือถือ และเดสก์ท็อป ในภาษาที่คุณชื่นชอบได้อย่างง่ายดาย และแบ่งปันกับทีมของคุณได้อย่างปลอดภัย ไม่จำเป็นต้องมีประสบการณ์เกี่ยวกับ frontend มาก่อน

### ⚡จากไอเดียสู่แอพในไม่กี่นาที

เครื่องมือภายในหรือแดชบอร์ดสำหรับทีมของคุณ โปรเจ็กต์ช่วงสุดสัปดาห์ , แบบฟอร์มการป้อนข้อมูล , แอปคีออสก์ หรือ แบบที่มีความแม่นยำสูง 
- Flet เป็นเฟรมเวิร์กในอุดมคติ แฮ็กแอปทำการการโต้ตอบที่ดูดีได้ อย่างรวดเร็วเพื่อให้บริการกับกลุ่มผู้ใช้งาน

### 📐 สถาปัตยกรรมที่เรียบง่าย

ไม่มีสถาปัตยกรรมที่ซับซ้อนอีกต่อไปกับ Front End ที่เป็น JavaScript, Front End REST API, ฐานข้อมูล, แคช ฯลฯ ด้วย Flet คุณเพียงแค่เขียนแอปเก็บสถานะแบบชั้นเดียวใน Python เท่านั้น และสมารถรับแอปพลิเคชัน หน้าเดียวแบบเรียลไทม์สำหรับผู้ใช้หลายคนแบบเรียลไทม์ได้ (SPA)

### 🔋รวมมาอยู่เป็นแบตเตอรี่

ในการเริ่มต้นพัฒนาด้วย Flet คุณเพียงแค่ต้องมี IDE หรือโปรแกรมแก้ไขข้อความที่คุณชื่นชอบ ไม่มีต้อง SDK ไม่ต้องการ dependencies มากมายก่ายกอง ไม่มีเครื่องมือที่ซับซ้อน 
- Flet มีเว็บเซิร์ฟเวอร์ในตัวพร้อมในการโฮสต์ assets และไคลเอนต์เดสก์ท็อป

### &nbsp;<img src="media/flutter/icon_flutter.svg" height="20px" />&nbsp;&nbsp;ขับเคลื่อนโดย Flutter

Flet UI สร้างขึ้นด้วย [Flutter](https://flutter.dev/) ดังนั้นแอปของคุณจึงดูเป็นมืออาชีพและสามารถส่งไปยังแพลตฟอร์มใดก็ได้ Flet ช่วยลดความซับซ้อนของโมเดล Flutter โดยการรวม "วิดเจ็ต" ที่เล็กกว่าเข้ากับ "การควบคุม" ที่พร้อมใช้งานกับโมเดลเพื่อเขียนโปรแกรมในส่วนที่จำเป็นจริงๆ

### 🌐 ใช้ได้ในภาษาของคุณ

Flet เป็นภาษา  language-agnostic ดังนั้นทุกคนในทีมของคุณสามารถพัฒนาแอป Flet ในภาษาที่พวกเขาชื่นชอบได้ [Python](https://flet.dev/docs/getting-started/python) ได้รับการสนับสนุนแล้ว Go, C # และอื่น ๆ ตอนนี้ [กำลังมาในอนาคต](https://flet.dev/docs/roadmap).

### 📱 ส่งไปยังอุปกรณ์อื่นๆ

การ Deploy แอป Flet ให้เป็นเว็บแอปและดูในเบราว์เซอร์ได้ และยังบรรจุเป็นแอปเดสก์ท็อปแบบสแตนด์อโลนสำหรับ Windows, macOS และ Linux ติดตั้งบนมือถือเป็น [PWA](https://web.dev/what-are-pwas/) หรือดูผ่านแอพ Flet สำหรับ iOS และ Android

## ตัวอย่างแอพ Flet

ในขณะนี้ คุณสามารถเขียนแอพ Flet ใน Python และภาษาอื่นๆ จะถูกเพิ่มในไม่ช้า

นี่คือตัวอย่างแอป "Counter":

```python title="counter.py"
import flet
from flet import IconButton, Page, Row, TextField, icons

def main(page: Page):
    page.title = "Flet counter example"
    page.vertical_alignment = "center"

    txt_number = TextField(value="0", text_align="right", width=100)

    def minus_click(e):
        txt_number.value = int(txt_number.value) - 1
        page.update()

    def plus_click(e):
        txt_number.value = int(txt_number.value) + 1
        page.update()

    page.add(
        Row(
            [
                IconButton(icons.REMOVE, on_click=minus_click),
                txt_number,
                IconButton(icons.ADD, on_click=plus_click),
            ],
            alignment="center",
        )
    )

flet.app(target=main)
```

เพื่อให้มันทำงานต้องติดตั้งโมดูล `flet` ก่อน:

```bash
pip install flet
```

จากนั้นเรียกใช้งานโปรแกรมได้เลย:

```bash
python counter.py
```

แอพจะเริ่มต้นใน หน้าต่างระบบปฏิบัติการเดิม - เป็นทางเลือกที่ดีเหมือน Electron

<img src="https://flet.dev/img/docs/getting-started/flet-counter-macos.png" width="45%" />


ตอนนี้ ถ้าคุณต้องการเรียกใช้แอปเป็นแบบเว็บแอป เพียงแทนแค่ที่บรรทัดสุดท้ายด้วย:

```python
flet.app(target=main, view=flet.WEB_BROWSER)
```

เรียกใช้อีกครั้งและตอนนี้คุณจะได้รับเว็บแอปทันที:

<img src="https://flet.dev/img/docs/getting-started/flet-counter-safari.png" width="60%" />

## เริ่มต้นกัน

* [การสร้างแอพ Flet ใน Python](https://flet.dev/docs/getting-started/python)
* [การอ้างอิงการ Controls ](https://flet.dev/docs/controls)

## แอพตัวอย่างใน Python

* [ทักทาย](https://github.com/flet-dev/examples/blob/main/python/apps/greeter/greeter.py)
* [ตัวนับ](https://github.com/flet-dev/examples/blob/main/python/apps/counter/counter.py)
* [แอพ To-Do](https://github.com/flet-dev/examples/blob/main/python/apps/todo/todo.py)
* [เบราว์เซอร์ ไอคอน](https://github.com/flet-dev/examples/blob/main/python/apps/icons-browser/main.py) ([ดูตัวอย่างออนไลน์](https://flet-icons-browser.fly.dev/))

## ชุมชน

* [พูดคุย](https://github.com/flet-dev/flet/discussions)
* [ดิสคอร์ด](https://discord.gg/dzWXP8SHG8)
* [ทวิตเตอร์](https://twitter.com/fletdev)
* [อีเมล์](mailto:hello@flet.dev)