# Basic user manual Web UI
    Hướng dẫn sử dụng Web UI cơ bản.
## Used:

1. Cài đặt các module cần thiết:

```bash
pip install -r requirements.txt
```

2. Thiết đặt plugins:

```bash
cd plugins
python setup.py install
```

3. Web UI:

```bash
python app.py --displaywave
```

3. Hoặc chạy API Server:

```bash
python app.py --api
```
## **Models:**
- Đây là nơi bạn sẽ chọn models cho mình. Hãy lựu chọn models bạn thích mà đã lưu trong `models`.

## **Audio setting:**
    Đây là nơi để bạn cài đặt các thiết đặt liên quan đến âm thanh.
    
- **Using symbols** : Có sử dụng symbols hay không, nếu chọn, `symbols` sẽ được sử dụng. **`Tuy nhiên`**, trong phần `Text` ở bên dưới, bạn phải dùng `symbols`, nếu không âm thanh sẽ bị lỗi, các symbols có thể lấy từ phía trên. Mặc định là `False`.
- **Choices speaker** : Lựa chọn `speaker` trong danh sách. Mặc định là `speaker đầu tiên`.
- **Audio speed** : Tốc độ nói của `speaker`. Mặc định là `1`.

## **Using Auto translate:**
    Đây là phần để bạn sử dụng dịch ngay tại trang web. Bật nó nếu bạn cần phiên dịch.
- **Choices language**: Lựa chọn ngôn ngữ cần dịch thuật. Văn bản sau khi dịch thuật sẽ ở phần `Text`.
- **Translate**: Nhập văn bản cần dịch, văn bản sau khi dịch theo `Choices language` sẽ hiện ở phần `Text`.
## **Text:**
- Đây là nơi bạn nhập văn bản. **`Lưu ý`**, khi nhập văn bản, bạn phải nhập văn bản đúng ngôn ngữ của `speaker`. Để thuận tiện, hãy sử dụng `Auto translate`.
## **Generation:**
- Nhấn vào đây để bắt đầu quá trình chuyển văn bản thành giọng nói.
## **Output message:**
- Trả về lời nhắn `thành công` hay `thất bại`.
## **Output audio:**
- Trả về âm thanh.
## **Output Wave:**
- Hiện thị sóng âm.
## **Download audio:**
- Tải âm thanh về.
# API server

## **post : /loadmodel**
- Load a TTS model.
- - @param index (int): chỉ mục của model trong danh sách, có thể lấy bằng cách `"/listmodels"`.
## **post : /generation**
- Chuyển văn bản thành giọng nói
- - @param request: Là một GenerationRequest.
- <font color='red'>Quan trọng</font> : Model cần phải được load trước. Sử dụng `"/loadmodel"`.
## **get : /listmodels**
- Lấy danh sách các model hiện tại.