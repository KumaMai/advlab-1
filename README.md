# pip install yt_dlp
เป็นคำสั่งสำหรับติดตั้ง yt_dlp
ต้องรันใน Command Prompt / Terminal ก่อน (ไม่ใช่ในไฟล์ .py)

import yt_dlp
นำไลบรารี yt_dlp เข้ามาใช้งานในโปรแกรม

def download_youtube_video(url, save_path="."):
สร้างฟังก์ชันชื่อ download_youtube_video
รับพารามิเตอร์: url → ลิงก์ YouTube
save_path → โฟลเดอร์ที่ใช้บันทึกไฟล์ (ค่าเริ่มต้นคือ "." = โฟลเดอร์ปัจจุบัน)

    ydl_opts = {
        'outtmpl': f'{save_path}/%(title)s.%(ext)s',
        'format': 'best'
    }
รูปแบบชื่อไฟล์ที่บันทึก
%(title)s → ชื่อวิดีโอ
%(ext)s → นามสกุลไฟล์ (เช่น mp4, webm)

with yt_dlp.YoutubeDL(ydl_opts) as ydl:
   ydl.download([url])
สร้างอ็อบเจ็กต์ YoutubeDL พร้อมตัวเลือกที่ตั้งไว้
with ช่วยจัดการ resource ให้อัตโนมัติ
ydl.download([url])
ดาวน์โหลดวิดีโอจาก URL
ใช้เป็น list แม้จะมีแค่ลิงก์เดียว

video_url = input("Enter the YouTube video URL: ")
ให้ผู้ใช้พิมพ์ลิงก์ YouTube ผ่านคีย์บอร์ด

download_youtube_video(video_url, save_path=".")
เรียกฟังก์ชันเพื่อดาวน์โหลดวิดีโอ
บันทึกไฟล์ไว้ในโฟลเดอร์ปัจจุบัน

สรุป
โค้ดนี้ทำงานตามลำดับดังนี้:
1.รับลิงก์ YouTube จากผู้ใช้
2.ตั้งค่าชื่อไฟล์และคุณภาพ
3.ดาวน์โหลดวิดีโอคุณภาพสูงสุด
4.บันทึกลงเครื่อง
