# Cryptocurrency66
from PIL import Image, ImageDraw, ImageFont
import os

# สร้างภาพพื้นหลังสีขาว
width, height = 600, 1000
image = Image.new("RGB", (width, height), "white")
draw = ImageDraw.Draw(image)

# โหลดฟอนต์ (ถ้าไม่มีฟอนต์ในเครื่อง ให้ดาวน์โหลดฟอนต์ที่คล้ายกัน เช่น "THSarabunNew")
try:
    font_large = ImageFont.truetype("THSarabunNew.ttf", 60)  # สำหรับตัวเลขใหญ่
    font_medium = ImageFont.truetype("THSarabunNew.ttf", 40)  # สำหรับข้อความทั่วไป
    font_small = ImageFont.truetype("THSarabunNew.ttf", 30)  # สำหรับข้อความเล็ก
except:
    font_large = ImageFont.load_default()
    font_medium = ImageFont.load_default()
    font_small = ImageFont.load_default()

# เพิ่มขอบสีแดง
draw.rectangle([0, 0, width-1, height-1], outline="#FF3366", width=20)

# วาดวงกลมสีเขียว (เลียนแบบเครื่องหมายถูก)
draw.ellipse([width-100, 20, width-60, 60], fill="#00CC00", outline="#00CC00")

# วาดข้อความ (เลียนแบบสลิป)
# หัวข้อ
draw.text((50, 50), "การโอนเงินสำเร็จ", fill="black", font=font_medium)
draw.text((50, 100), "โอนเงินสำเร็จ", fill="black", font=font_medium)

# จำนวนเงิน (เปลี่ยนเป็น 100,000.00)
draw.text((50, 150), "100,000.00", fill="black", font=font_large)

# ค่าธรรมเนียม
draw.text((50, 220), "0.00 บาท (ค่าธรรมเนียม)", fill="black", font=font_small)

# รหัสอ้างอิง
draw.text((50, 260), "รหัสอ้างอิง: 2025040714111534757830509714534757", fill="black", font=font_small)

# วันที่และเวลา
draw.text((50, 300), "7 พ.ย. 2568 14:41", fill="black", font=font_small)

# ผู้ส่ง
draw.text((50, 350), "ผู้ส่ง", fill="black", font=font_medium)
draw.text((50, 390), "ธนาคาร ธกส", fill="black", font=font_medium)
draw.text((50, 430), "สาขา พระนครศรีอยุธยา", fill="black", font=font_small)
draw.text((50, 470), "0204xxxx2900", fill="black", font=font_small)

# ผู้รับ
draw.text((50, 520), "ถึง", fill="black", font=font_medium)
draw.text((50, 560), "คุณนาง (ธนาคารกรุงไทย)", fill="black", font=font_medium)
draw.text((50, 600), "เลขที่บัญชี: VC593069MIO006384H2", fill="black", font=font_small)
draw.text((50, 640), "ชื่อบัญชี: TUNGERN", fill="black", font=font_small)

# QR Code (จำลองข้อความ)
draw.text((50, 700), "QR Code", fill="black", font=font_medium)
draw.text((50, 740), "สแกน QR เพื่อดูรายละเอียดเพิ่มเติม", fill="black", font=font_small)
draw.rectangle([200, 780, 400, 980], outline="black", width=2)  # จำลอง QR Code

# โลโก้ mymo
draw.text((50, 940), "mymo by GSB", fill="#FF3366", font=font_medium)

# บันทึกภาพ
image.save("fake_slip_100000.png")
print("สร้างสลิปใหม่สำเร็จ! บันทึกเป็น fake_slip_100000.png")