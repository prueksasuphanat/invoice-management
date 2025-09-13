![Google Sheet: Invoice Maker 2020](https://firebasestorage.googleapis.com/v0/b/peerasak-website.appspot.com/o/note%2FScreen%20Shot%202020-01-28%20at%2010.05.39%20PM.png?alt=media&token=8e36d0d7-1d56-424c-bd6b-f02ad05df435)

## Google Sheet: Invoice Maker 2020

จากบทความ 👉 **[สร้างเอกสารการเงินอัตโนมัติด้วย Google Sheets โดยไม่ต้องเขียนสคริปต์ (เพราะผมเขียนให้แล้ว)](https://peerasak.com/post/how-to-use-invoice-maker-sheets/)** 👈 คุณสามารถแก้ไขและนำไปใช้กับ Google Sheets ของคุณได้ตามอัธยาศัย

## การติดตั้ง 🚀

ก่อนอื่นต้องติดตั้ง Node.js และ NPM package manager ให้เรียบร้อย

### :package: เริ่มต้น

1\. Clone repository นี้และ install npm dependencies

```
git clone https://github.com/clonezer/gas-invoice-maker.git my-invoice-maker
cd my-invoice-maker
npm install
```

2\. Log in to Google clasp ด้วย Google Account ของคุณ

```
npx clasp login
```

3\. Make a copy ตัว Sheets ออกมา(ตามบทความ) แล้วทดลองสร้างเอกสารให้เรียบร้อบ แล้วเข้าไปที่ [Google Apps Script](https://script.google.com) เลือก project ที่ตรงกับ sheets ที่ copy ออกมาใหม่

4\. หลังจากคลิกเลือก project ไปแล้ว ให้สังเกตที่ url ด้านบนแล้วทำการ copy หมายเลข id ดังนี้

```
https://script.google.com/home/projects/COPY_ID_ตรงนี้
```

5\. แก้ไขไฟล์ `.clasp.json` ใน folder ของ project โดยนำ `ID` จากข้อ `4` มาวางที่ `scriptId`

```json
{
    "scriptId": "YOUR_GOOGLE_SCRIPT_ID",
    "rootDir": "./dist"
}
```

6\. ทดลองทำการ Deploy ตัว project เพื่อให้ script ใช้งานได้กับ sheet ใหม่ของเรา

```
npm run deploy
```