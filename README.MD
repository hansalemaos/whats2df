# Finding certain messages in your WhatsApp message is sometimes hard, but Pandas makes it easier. Doesn't require root access!

#### Tested against Google Pixel 6 / Windows 10 / Python 3.10

### Tutorial (Brazilian Portuguese)

[![YT](https://i.ytimg.com/vi/KG_xC2TmbDo/maxresdefault.jpg)](https://www.youtube.com/watch?v=KG_xC2TmbDo)
[https://www.youtube.com/watch?v=KG_xC2TmbDo]()

```python
pip install whats2df

# This is the updated version of https://github.com/hansalemaos/a_pandas_ex_whatsapp_to_df
```

## Follow these steps if you want to avoid rooting your cell phone:

* Open WhatsApp on your Android device.
* Tap the three-dot overflow menu button and navigate to "Settings > Chats > Chat backup".
* Tap End-to-end encrypted backup, then tap "Turn on".
* Create a 64-digit key and save it! You will need it! DON'T CREATE a password!
* Tap Create and wait for WhatsApp to create an encrypted backup.
* Copy the backup from your Android device to your computer (File path on my device: storage/emulated/0/Android/media/com.whatsapp/WhatsApp/Databases/msgstore.db.crypt15  - You can localize the file using https://pypi.org/project/a-pandas-ex-adb-to-df )


## Function - Python 

```python
from whats2df import convert_whatsapp2pandas

convert_whatsapp2pandas(
    decryptkey="e2c412cea3b0a662e47a2062fffa0db7cf7cca093636abf5bca6e701a6fae3bc",
    encrypted_db=r"C:\Users\hansc\Desktop\msgstore.db.crypt15",
    decrypted_db=r"C:\Users\hansc\Desktop\msgstore.db", # doesn't exist yet
    output_df=r"C:\Users\hansc\Desktop\msgstore.plk", # doesn't exist yet
    download_sql_dll = True, # downloads "https://www.sqlite.org/2023/sqlite-dll-win64-x64-3420000.zip" and extracts it to ./DLLs
)
```

## CLI 

```
# adjust the path to "whats2df.py"

python C:\ProgramData\anaconda3\envs\nu\Lib\site-packages\whats2df\whats2df.py --decryptkey e2c412cea3b0a662e47a2062fffa0db7cf7cca093636abf5bca6e701a6fae3bc --encrypted_db C:\Users\hansc\Desktop\msgstore.db.crypt15 --decrypted_db C:\Users\hansc\Desktop\msgstore.db --output_df C:\Users\hansc\Desktop\msgstore.pkl --download_sql_dll 1
```
