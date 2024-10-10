import requests

def send_sms(phone_number, message):
    url = "https://api.sms-service.com/send"
    data = {
        "phone": phone_number,
        "message": message
    }
    response = requests.post(url, data=data)
    return response.status_code

phone = input("Enter phone number: ")
msg = input("Enter message: ")

for i in range(10):  # ১০ বার মেসেজ পাঠানোর জন্য লুপ
    status = send_sms(phone, msg)
    print(f"Message {i+1} sent, status code: {status}")
