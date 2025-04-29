# 🕵️‍♂️ Hiding a Text File with Steghide in Kali Linux
- **Here we only learn how to hide text file in image(jpg,jpeg)**
## ✅ Step 1: Install Steghide

Open your terminal and run:

```bash
sudo apt update
sudo apt install steghide
```
## ✅ Step 2: Prepare Your Files
### Cover File: Must be an image (.jpg, .jpeg, .bmp) or audio (.wav) file.

- ### Example: cover.jpg
- ### Secret File: The text file you want to hide.
- ### Example: secret.txt
- ### Place both files in the same directory.

## ✅ Step 3: Embed the Secret File
```bash
steghide embed -cf cover.jpg -ef secret.txt
```
## ✅ Step 4: Verify the Hidden Data (Optional)
```bash
steghide info cover.jpg
```
## ✅ Step 5: Extract the Hidden File

```bash
steghide extract -sf cover.jpg
```

# ✅ Notes
- Steghide does not work with PNG or MP3 files.
- remember the password when you are hiding the text file 