```markdown
# 🔥 Free Fire 1000 Visit Sender API

This is a Flask-based API that simulates **1000 successful visits** to a Free Fire player's profile using valid access tokens. It decrypts the response using **Protobuf** and returns detailed player information such as UID, nickname, level, likes, region, and visit success/failure stats.

---

## 🚀 Features

- ✅ Sends **1000 successful visits** using multiple tokens.
- 🔐 Uses AES-encrypted payloads to match Free Fire's request format.
- 📦 Parses **protobuf** response from Free Fire servers to extract player info.
- 📊 Returns player details: UID, nickname, likes, region, level, success, and fail counts.
- 🔁 Automatically retries until 1000 successful visits are completed.
- 🧠 Token management by region.
- 📄 Clean and JSON-formatted API output.

---

## 📦 Requirements

- Python 3.8+
- Required Python packages:
  ```bash
  pip install flask aiohttp protobuf pycryptodome
  ```

---

## 📁 Folder Structure

```
project/
│
├── app.py                  # Main Flask server
├── byte.py                 # Encryption and ID generator module
├── visit_count.proto       # Protobuf schema
├── visit_count_pb2.py      # Generated protobuf file
├── token_ind.json          # Token list for IND server
├── token_br.json           # Token list for BR/US/NA/SAC
├── token_bd.json           # Token list for other regions
├── README.md               # This documentation
```

---

## 🧪 How to Use

1. **Start the Flask server:**
   ```bash
   python app.py
   ```

2. **Make a GET request:**
   ```
   https://your-api/visit?region={region}&uid={uid}
   ```

   Replace:
   - `<server>` with one of: `IND`, `BR`, `US`, `SAC`, `NA`, `BD`, etc.
   - `<uid>` with the player UID you want to visit.

---

## 📤 Example Request

```
GET https://your-api/visit?region={region}&uid={uid}
```

---

## 📥 Example Response

```json
{
  "fail": 0,
  "level": 64,
  "likes": 10294,
  "nickname": "—͞ᏟᎢᏀㅤDʜʀᴜʙᴏ",
  "region": "BD",
  "success": 1000,
  "token_rotation": "active",
  "tokens_used": 20,
  "uid": 2887682120
}
```

---

## ⚙️ Token Format

Each `token_*.json` file should contain a list of tokens in this format:

```json
[
  {"token": "YOUR_ACCESS_TOKEN_1"},
  {"token": "YOUR_ACCESS_TOKEN_2"},
  ...
]
```

---

## 📌 Notes

- The system will **keep retrying** until 1000 successful visits are sent.
- If likes or level are not available in the response, they default to `0`.
- If no valid tokens are found, the API will return an error.
- Response is parsed using `.proto` schema and extracted using the `visit_count_pb2.py` module.

---

## 🛠 Dependencies Summary

- **Flask** – for HTTP API.
- **aiohttp** – for asynchronous POST requests.
- **protobuf** – for decoding Free Fire’s binary response.
- **pycryptodome** – for AES encryption of request payloads.

---

## 👨‍💻 Author

Made by [DHRUBO](https://t.me/DHRUBO_X_TCP) for Free Fire automation.

---

## 📞 Support

For help or custom development, message on Telegram: [@DHRUBO_X_TCP](https://t.me/DHRUBO_X_TCP)

---

## 🔐 Disclaimer

This tool is for **educational and research purposes only**. Use responsibly. We are not affiliated with Garena or Free Fire in any way.
```
